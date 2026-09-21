# DUEFORCE — Real SaaS production starter

DUEFORCE is a receivables automation application for Indian businesses. This package is designed for Firebase Hosting/Firestore/Auth and Firebase Functions.

## Included
- Firebase Email/Password Auth
- One business account per Firebase UID
- Real Firestore customers, invoices, payments and reminders
- New accounts start with zero balances and no demo records
- Partial/full payment recording; full payment disables reminders
- Secure Firestore ownership rules
- Scheduled due engine (09:15 Asia/Kolkata) with 0/2/7/15-day reminder cadence
- WhatsApp Cloud API template sender scaffold
- Razorpay payment-link endpoint scaffold
- Razorpay webhook with signature verification and idempotency
- MRLB → DUEFORCE entry animation
- Agreement/notice drafting workspace

## Firebase project
`dueforce-926bb`

## Deploy
1. Install Firebase CLI.
2. Run `firebase login`.
3. From this directory run `firebase use dueforce-926bb`.
4. Run `firebase deploy --only firestore:rules,firestore:indexes,hosting,functions`.
5. Add Functions secrets with `firebase functions:secrets:set ...` before enabling WhatsApp/Razorpay.

Required optional secrets:
- WABA_TOKEN
- WABA_PHONE_ID
- WABA_TEMPLATE
- RAZORPAY_KEY_ID
- RAZORPAY_KEY_SECRET
- RAZORPAY_WEBHOOK_SECRET

Never put these secrets in `index.html`, GitHub source, or Firestore documents.

## Production checklist
- Verify Firebase Auth authorized domains for the final hosting domain.
- Configure WhatsApp Business templates and provider compliance.
- Configure Razorpay webhook URL to the deployed `razorpayWebhook` endpoint and subscribe only to required payment events.
- Test with Razorpay test mode before live mode.
- Add privacy policy, terms, data retention, support and consent/communication controls.
- Review legal notice/agreement templates with qualified counsel for the applicable transaction, jurisdiction and statutory eligibility.
