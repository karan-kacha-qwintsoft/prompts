# 💳 Razorpay Website Verification & Mandatory Legal Suite

> **Best for:** Preparing an existing production website for Razorpay payment activation and website verification by implementing compliant, customer-facing legal and business pages.

---

## Prompt

```markdown
Act as a Lead Full-Stack Engineer & Compliance Specialist. Prepare this website for Razorpay payment activation and website verification by implementing all required customer-facing legal and business information pages.

### Phase 1: Repository & Architecture Audit (Do this first)
Before altering any code:
1. Identify the framework, routing system, styling, layout components (Header, Footer), typography, and theme.
2. Check existing business/contact info across components, configuration, and environment files.
3. Inspect existing payment, checkout, pricing, order, shipping, and refund flows.
4. **Preserve Integrity**: Do NOT duplicate existing pages/components. Do NOT remove or break existing functionality, auth, cart, or payment logic. Preserve visual design and branding.

---

### Phase 2: Create/Update the 5 Required Public Pages
Implement these 5 publicly accessible pages (no login, payment, or permissions required):

#### A. Contact Us (`/contact`)
- Business / Company legal or brand name.
- Registered business address.
- Customer support email and phone number.
- Customer support operating hours / availability.
- (Optional) Working contact form if supported by the project.

#### B. Privacy Policy (`/privacy-policy`)
- Information collected (personal, contact, device, cookies, order info).
- Payment processing: Clearly state payments are securely processed via Razorpay. **Crucial**: Do NOT claim the website stores card/UPI/banking credentials if processed externally.
- Third-party service providers, data retention, security safeguards, user rights (access/deletion), and children's privacy.
- Contact details for privacy concerns & a visible "Last Updated" date.

#### C. Terms & Conditions (`/terms-and-conditions`)
- Acceptance of terms, user eligibility, account responsibilities.
- Product/service descriptions, transparent pricing, applicable taxes.
- Payment processing, order confirmation, and delivery/fulfillment terms.
- Intellectual property, prohibited activities, limitation of liability, disclaimers, suspension/termination, governing law & jurisdiction.

#### D. Refund & Cancellation Policy (`/refund-cancellation`)
- Cancellation eligibility, request window, and submission steps.
- Refund eligibility, non-refundable items/services, and processing timelines (e.g., 5-7 business days for gateway credit).
- Policy for failed, duplicate, or incorrect payments.
- Support contact channel for refund disputes.
- **Match Business Model**: Accurately reflect physical returns or digital service cancellation rules. Do not make unsupported promises.

#### E. Shipping & Delivery Policy (`/shipping-delivery`)
- **For Physical Goods**: Delivery zones, shipping charges, estimated processing/delivery timelines, courier partners, tracking, damaged package protocols.
- **For Digital Goods / Services**: Clearly state digital delivery mechanism (instant account access, email delivery, download link), fulfillment turnaround, and resolution steps if access fails.
- **Rule**: DO NOT add physical shipping terms to a digital-only service.

---

### Phase 3: Footer Integration
- Integrate all 5 links prominently into the **existing footer** (do not create a secondary footer):
  `Contact Us` (`/contact`), `Privacy Policy` (`/privacy-policy`), `Terms & Conditions` (`/terms-and-conditions`), `Refund / Cancellation Policy` (`/refund-cancellation`), `Shipping / Delivery Policy` (`/shipping-delivery`).
- Must be accessible across all pages, working seamlessly on mobile and desktop without requiring authentication.

---

### Phase 4: Business Data Integrity & Design
1. **Real Data Only**: Extract business name, address, email, and phone from existing project config/env. Never fabricate addresses, phones, or GSTNs. If missing, create clear placeholder variables in config.
2. **Consistent Design**: Reuse existing layout, header, footer, colors, font hierarchy, and card/button styles.
3. **Readable Layout**: Use a readable max-width, clean typography, clear section spacing, and a "Last Updated" timestamp.
4. **SEO Metadata**: Provide accurate page titles (e.g., `Terms & Conditions | [Business Name]`), meta descriptions, and canonical tags.

---

### Phase 5: Verification & Audit Report
1. Verify responsiveness across desktop, tablet, and mobile (no horizontal scroll).
2. Ensure zero console errors, hydration mismatches, broken routes, or TypeScript/lint issues.
3. Provide a final summary report containing:
   - Existing pages found vs created/updated.
   - Exact routes and footer integration status.
   - Source of business information used & any missing fields needed from the user.
   - Verification checklist results.
```
