# DUEFORCE V24

Free/Spark-compatible UPI plan activation and admin verification.

- Starter ₹199/month
- Business ₹499/month
- Pro ₹999/month

Flow: Plan → Pay Now → plan-specific UPI URI/QR → customer pays → UTR submit → Pending Verification → Admin verifies → Approve/Reject.

The first authenticated account that uses **Make this account Admin** creates `admin/config`. Firestore rules then restrict admin actions to that UID. No Cloud Functions or Blaze plan is required.

QRs contain the plan amount, but some UPI apps may still permit amount editing. Verify the received amount and UTR before approval.
