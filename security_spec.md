# Security Specification for SAMS Attendance Management

## 1. Data Invariants
- Each user profile (`/users/{userId}`) can only be read, created, and updated by the authenticated owner (`request.auth.uid == userId`).
- Subcollections (`sessions`, `students`, `attendance_records`) belong strictly to their parent user document (`/users/{userId}/...`).
- Any mutation requires authentication (`request.auth != null`) and ownership (`request.auth.uid == userId`).
- Strict key and type validation ensures no orphan writes, ghost fields, or oversized payloads.
- Default deny matches all undefined paths.

## 2. The Dirty Dozen Payloads
1. Unauthorized User Profile read by unauthenticated caller.
2. Cross-user Profile mutation (Alice trying to modify Bob's profile).
3. Session creation with mismatched `userId != request.auth.uid`.
4. Session creation with junk/oversized payload (> 100KB string).
5. Deletion of another user's session record.
6. Insertion of student with malicious script injection in `id`.
7. Student update by unauthenticated attacker.
8. Attendance record creation under unauthenticated session.
9. Cross-user reading of another teacher's attendance logs.
10. Attempt to update read-only immutable fields (`userId`, `createdAt`).
11. Arbitrary injection of extra unlisted administrator rights.
12. Shadow update adding arbitrary un-schema'd data fields to student documents.
