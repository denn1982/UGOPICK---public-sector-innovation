# Frontend

### React + Vite — single-page application, fast HMR, modern build pipeline.

### Tailwind CSS — token-based design system (see src/index.css + tailwind.config.js).

### Framer Motion — animations and transitions.

### Bunny Fonts — EU-hosted, privacy-friendly alternative to Google Fonts (no IP sent to US servers, no cookies, no tracking).

### Responsive — designed for mobile, tablet, laptop, and desktop; safe-area aware for iOS notches.

### Session storage only — the app stores no persistent data in the browser. Only the voting streak, last vote choice, last topic ID, and last slot are kept temporarily in session storage and are cleared when the browser closes.

# Backend

#### Built entirely on Base44 (backend-as-a-service: auth, database, integrations, hosting).

### Entities (data model):

### Entity	Purpose

### Topic	A poll question with question, context, order, government_level, and yes_count / no_count counters. Publicly readable; only admins can create/update/delete.

### VoteCheck	Deduplication record: a pseudonymous fingerprint + topic_id + 15-minute slot. Used only to prevent double voting. Admin-only access. Auto-deleted within 24 hours.

### Contact	Contact-form submissions (name, email, message) plus a pseudonymous ip_hash for rate-limiting. Admin-only access.

### Backend functions (base44/functions/):

### Function	Responsibility

### cast_vote	Validates the vote, computes the fingerprint, checks for duplicates, atomically increments the topic counter.

### generate_question	Invokes the LLM, applies the Article 1 discrimination filter, and persists a new Topic.

### submit_contact	Validates the contact form, enforces privacy consent, rate-limits by IP hash, and stores the message.

### cleanup_old_votes	Periodically purges stale VoteCheck (≤24h) and Contact (≤90 days) records.
