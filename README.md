# RahiVerse × SAMIA'S CLOSET — mobile-first React + Firebase project

Owner display: **Md. Humaun Husen Rahi**. The real Samia's Closet logo is included at `public/assets/samias-closet-logo.png`.

## Included in this ZIP
- Redesigned cream / soft teal / muted champagne responsive UI with mobile-first layout.
- Homepage route with product inventory pulled from Firestore, product categories, play entry point, rewards/account entry point and weekly reward status messaging.
- Brain Zone with 30 original Bengali questions, one-at-a-time answers, explanations, progress, scoring, replay and native share/copy fallback.
- Existing React/Firebase store routes retained: products, product details, authentication, account, cart, checkout, customer orders, contact, story and protected admin routes.
- Existing admin screens retained for product image uploads, inventory, order status and website settings.
- Admin authorization continues to rely on Firebase custom claims and Cloud Functions, not a hidden URL.
- Real owner-supplied logo included; no fake product inventory or fake customer statistics are added.

## Important before production
This ZIP is a **source-code package**, not a published website. No deployment URL is claimed.

1. Install Node.js (for desktop) and run `npm install` then `npm run dev` to test locally. On Android, use a browser-based development environment or GitHub/Vercel import; a phone alone cannot run the full local Node toolchain in the same way as a computer.
2. The frontend Firebase config targets `last-sc-samia-s-closet`. Confirm that Authentication providers, Firestore, Storage, indexes/rules, and Cloud Functions are configured in that exact project.
3. The existing Cloud Functions in `functions/src/index.ts` were authored for the previous starter project and must be reviewed, configured and deployed to the target project before order creation, reward claims, or admin custom-claim checks can be considered operational. Do not assume those server features work merely because the UI loads.
4. Enable Email/Password and Google sign-in in Firebase Authentication and add the deployed domain to Authorized domains.
5. Review `firestore.rules` and `storage.rules` against your actual project before deployment. Never deploy permissive rules or put service-account secrets in frontend code.
6. In the admin panel, add real products and upload the actual product images. Product cards only use Firestore inventory; no demo products are seeded.
7. Secure admin access is expected to be granted through the deployed `ensureAdminClaim` server function. Verify that server function's owner-email allowlist and IAM setup before use.

## Run / build
```bash
npm install
npm run dev
npm run build
```

## Current scope / not yet complete
- The existing storefront, cart, checkout, account, orders, and admin UI are preserved, but their production readiness depends on Firebase rules, Cloud Functions, indexes, auth providers and storage being configured correctly in the target project.
- Brain Zone is functional and client-side. It does not yet persist scores or create persistent friend challenge IDs.
- Personality Quiz, persistent daily challenge/streak, full Friendship Challenge backend, Style Studio filters, analytics dashboard, referral system, and admin quiz editor are not implemented in this package yet.
- Rewards/weekly reward links lead to the existing account route. This package does not invent a reward balance or claim that a reward was granted; verify callable reward endpoints and build dedicated wallet UI before advertising full reward functionality.
- Payment collection is not an automated payment gateway. Orders must not be treated as paid unless verified by an official gateway or manual admin process.

## Logo / brand
The original logo is in `public/assets/samias-closet-logo.png`. Homepage uses the supplied logo rather than inventing a replacement. Products and the rewards/weekly reward entry points are emphasized; the theme remains light and premium.
