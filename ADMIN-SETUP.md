# DUEFORCE V25 — Secure Free/Spark Admin Setup

This version does not use Cloud Functions and does not allow a website visitor to self-claim Admin.

## 1. Find the owner's Firebase Auth UID

Log in to DUEFORCE with the account that should be the administrator.

Open **Plans & Payment → Admin → Account** and tap **Copy UID**.

## 2. Create the Admin document in Firebase Console

Open the Firestore database for project `dueforce-926bb`.

Create:
- Collection: `admin`
- Document ID: `config`

Fields:
- `uid` — string — paste the exact Firebase Auth UID
- `email` — string — the admin email (informational)

Do this once. Do not let customers create this document.

## 3. Deploy Firestore Rules

Deploy `firestore.rules` before using Admin approval.

## 4. Admin workflow

Admin account:
Plans & Payment → **Open Admin Panel** → Refresh → verify UTR in the receiving UPI/bank account → **Approve** or **Reject**.

Approve adds:
- status = approved
- approvedBy = admin UID
- approvedAt
- expiresAt = 30 days

Reject adds:
- status = rejected
- reviewedBy = admin UID
- reviewedAt/reason as applicable

## 5. Important

This is manual UPI verification. UTR submission alone does not activate a plan.

No payment gateway, automatic UPI verification, webhook, or scheduled billing is included in Spark mode.
