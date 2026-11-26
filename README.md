# BizMate AI — Complete project starter

This project is based on your uploaded BizMate AI Phase 1 HTML prototype. The existing interface, navigation, palette, demo pages and interactions have been moved into a Vite + React frontend. A separate Node.js/Express + MongoDB backend starter is included.

## Project folders
- `frontend/` — Vite + React app containing the existing prototype UI.
- `backend/` — Express API, MongoDB models, password hashing, JWT authentication, business workspaces and generic CRUD endpoints.
- `backend/.env.example` — environment variable template.

## Run the frontend
1. Install Node.js (LTS).
2. Open a terminal in `frontend`.
3. Run `npm install`.
4. Run `npm run dev`.
5. Open the local URL printed by Vite (usually `http://localhost:5173`).

## Run the backend
1. Start MongoDB locally or create a MongoDB Atlas database.
2. Open a second terminal in `backend`.
3. Copy `.env.example` to `.env`.
4. Set `MONGODB_URI` and replace `JWT_SECRET` with a long random secret.
5. Run `npm install`.
6. Run `npm run dev`.
7. Test `http://localhost:5000/api/health`.

## API routes
- `POST /api/auth/register` — create account.
- `POST /api/auth/login` — sign in.
- `GET /api/businesses` — list the signed-in user's businesses.
- `POST /api/businesses` — create a business.
- `PATCH /api/businesses/:id` — update a business.
- `DELETE /api/businesses/:id` — delete a business.
- `/api/records/:kind` — list/create records; supported kinds: `products`, `orders`, `invoices`, `quotes`, `payments`.
- `/api/records/:kind/:id` — update/delete a record.

Protected routes require `Authorization: Bearer <token>`. Record requests require a `businessId` query parameter (GET/DELETE) or request body (POST/PATCH).

## Important current limitations
- The frontend preserves the uploaded prototype's local demo behaviour and LocalStorage data. It has **not yet been wired to the new backend API**; the backend is a separate working starter.
- The current AI assistant is rule-based demo logic, not a live AI model connection.
- Tailwind is loaded through its CDN in `frontend/index.html`; an internet connection is needed for those utility classes.
- Do not deploy this as-is with real customer or financial data. Add production validation, rate limiting, secure cookie/token handling, backups, audit logs, tests and deployment configuration first.
