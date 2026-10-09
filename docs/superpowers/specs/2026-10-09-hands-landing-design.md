# hands landing page design

## Purpose

Build a premium, minimalist landing page for hands, a UK-based physical AI data collection startup at the validation stage. The primary outcome is conversations with robotics data buyers. The secondary outcome is contributor and partner-business interest. Do not imply an established operation, existing customers, available datasets, or proven capacity.

## Visual direction

Use an editorial, industrial aesthetic: near-white background, charcoal text, deep navy actions, fine neutral rules, generous whitespace, and crisp geometric sans-serif typography. Use a restrained wordmark and the supplied circular two-hands symbol once the actual asset is provided. The current attachment contains only text; do not create a replacement symbol.

The desktop hero uses a large left-aligned headline, short supporting copy, and two clear actions. A quiet diagram on the right shows task demonstration → review and structure → training data. Label it as the proposed collection approach. Use no animated illustrations, gradients, glow, fake dashboards, or excessive rounded cards. Photography is sparse and depicts relevant physical tasks; captions explicitly identify examples, not hands operations.

Motion is limited to short color changes on hover and focus. No entrance animations, parallax, autoplay media, or animated counters. Respect reduced-motion preferences. On mobile, preserve the same hierarchy in a single column and provide a simple accessible navigation disclosure.

## Page structure and copy

1. Navigation: hands; How it works; For robotics teams; For contributors; Contact; primary action “Discuss your data needs”. All destinations are real page anchors.
2. Hero: “REAL-WORLD DATA FOR PHYSICAL AI”; “Human skills. Robot intelligence.”; the brief's supporting copy. Primary action opens the buyer section; secondary action opens the contributor section.
3. Challenge: “Teaching robots starts with real-world experience.” Explain the need for diverse demonstrations without unsupported figures.
4. Proposed workflow: tell us what you need; source the right people; receive quality-checked data. Present three numbered columns separated by fine rules, stacked on mobile. Explicitly describe the intended service.
5. Potential collection areas: assembly and manufacturing; sorting and manipulation; maintenance and repair; skilled trades and tool use. Use short, concrete descriptions and a restrained photographic grid.
6. Why hands / robotics teams: “The right demonstrations, from the right people.” Explain demand-led collection, relevant skills, varied environments, and the ambition to improve accessibility and affordability. Include the intended Ukraine starting point as a plan, not existing capacity.
7. Contributors: “Your skills have value beyond the job.” Use the brief's exploratory wording and link to the separate waitlist form.
8. Buyer inquiry: “What skills are you trying to teach your robots?” Fields: name, work email, company, tasks/data required, optional requirements/volume/timeline, additional details. Additional details are optional to reduce friction.
9. Contributor waitlist: name, email, country/region, relevant trade/skills, optional business affiliation. Consent covers being contacted about potential collection opportunities; no recordings or sensitive information requested.
10. Footer: hands; “Real-world data for physical AI.”; “UK-based. Exploring global collection.”; privacy notice; copyright. Until an actual contact email is supplied, use the inquiry form as the contact destination instead of inventing an address.

## Implementation approach

Recommended: a single Next.js application with TypeScript, semantic components, and plain CSS design tokens. Server-render the landing content; use client JavaScript only for the mobile menu and form feedback. This keeps the frontend and actual submission backend in one maintainable project.

Alternative: a static frontend with a hosted form provider reduces server maintenance but needs a configured external account. A separate frontend/API deployment adds operational complexity with no initial benefit.

Use a server-side SQLite submission store for the initial runnable application. Store buyer and contributor submissions separately and await a successful database transaction before returning success. Configure the database path with an environment variable and keep the database out of Git. A production deployment must provide durable storage; an ephemeral/serverless deployment requires a configured persistent database adapter before accepting submissions. Document this constraint explicitly.

Do not expose a public submissions dashboard. Provide an operator export command for authorized local access. Avoid logging submitted personal data. Maintain server-side validation, bounded field lengths and request size, basic spam protection, origin checks, and explicit errors. Consent is recorded with each submission. A failed or unavailable storage write returns an error, never a success message.

## Forms and privacy

Use visible labels, native input types, autocomplete attributes, required-field indicators, and accessible inline validation. Keep entered values when submission fails. Disable duplicate submissions during a pending request. Announce outcomes through a live region. Do not include analytics or tracking at launch.

Include a plain-language privacy page describing the actual fields stored, the inquiry/waitlist purpose, storage, and no recording collection at this stage. The owner must provide a real privacy contact and decide retention before public launch. Do not invent controller registration details, contact addresses, or claim regulatory certification.

## Verification

- Check type safety, lint, and production build.
- Test successful persistence and rejection of invalid submissions for both forms, including storage failure handling.
- Verify desktop and mobile layouts, keyboard navigation, focus visibility, and absence of horizontal overflow.
- Verify all anchors, calls to action, mobile menu, form pending/success/error states, and privacy navigation in a browser.
- Check metadata, semantic headings, descriptive image alternatives, image dimensions, and reduced motion.
- Request code review before completion and address actionable findings.

## Commit and push checkpoints

Commit and push the design, initial functioning page, validated submission backend, and final verification/refinement as separate meaningful checkpoints. Never commit credentials, submission data, local databases, dependencies, or build output. The repository is currently empty and its configured remote is git@github.com:vbshuliar/hands.git.

## Inputs still needed

The original circular two-hands logo is missing from the supplied attachment. Public deployment details, the real contact/privacy email, and the production retention decision are also not supplied. These do not prevent building the page and a real local persistence backend, but must be resolved before public launch.
