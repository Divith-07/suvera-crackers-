
# Suvera Crackers — storefront + admin starter

A responsive storefront with editable product catalogue, cart, checkout without online payment, admin login, order review, offers, and optional Google Sheets logging.

## Important honest limitation
The public AKS homepage is accessible, but its full product catalogue and product image URLs were not exposed by the web inspection available in this session. This project therefore includes the seven invoice-confirmed products plus clearly-labelled sample products and image placeholders. Replace/import the final AKS catalogue in `data/products.json` when it is collected. Do not hotlink AKS images without permission; use images you are authorised to use.

## Run locally
This is a static prototype intended for quick preview:
1. Extract the ZIP.
2. Open `index.html` in a browser (or serve the folder with `python -m http.server 8080`).
3. Open `admin.html` for the admin panel.

## Default demo admin
- Username: `admin`
- Password: `SuveraDemo!2026`
- Change these immediately in `app.js` for local demonstration.
- This demo auth uses browser-side storage and is **not production-secure**. Do not deploy the admin page publicly as-is.

## Google Sheets
See `google-apps-script/Code.gs`. Create a Google Sheet, open Extensions → Apps Script, paste the script, set `SHEET_ID` and a long random `ADMIN_SECRET`, deploy as a Web App, and set access to the intended deployment mode. Copy the deployment URL into `app.js` as `SHEETS_WEB_APP_URL`. For production, use server-side auth and validate every request; never embed a privileged secret in public frontend code. This static starter intentionally does not pretend client-side secrets are secure.

## Production recommendation
Move the frontend to a hosted app (e.g. Vercel) with server-side API routes, Supabase Auth/Postgres/Storage, server-side Sheets integration, environment variables, rate limiting, and server-validated prices/totals. Before launch, test orders, delivery/packing rules, admin permissions, data retention, and legal/safety notices.

## Initial business settings
- Name: Suvera Crackers
- Address: 12/495/6, Rathinapuri Nagar, Meenampatti, Sivakasi, Tamil Nadu 626189, India
- Phone: +91 90803 58429
- Email: suveracrackers@gmail.com
- Free delivery threshold: ₹2,500
- Packing charge: 1.5%
- No online payment: customer places an order for manual confirmation
