SRI GAYATHRI — TWO-PANEL WEBSITE

FILES
- index.html: public customer storefront
- admin.html: separate private owner dashboard
- config.js: Supabase project URL, publishable/anon key, WhatsApp number

IMPORTANT
1. This version has NO sample/demo products and NO demo login.
2. The admin dashboard uses Supabase Auth and checks the is_store_owner() database function.
3. Product records and uploaded images are shared through your Supabase project.
4. Never put the Supabase service_role/secret key in config.js or any browser code.

SETUP
A. Open config.js and replace:
   PASTE_YOUR_SUPABASE_PROJECT_URL
   PASTE_YOUR_SUPABASE_PUBLISHABLE_OR_ANON_KEY
   Use Supabase Project Settings > API for the Project URL and publishable key (or legacy anon key).
B. Keep the existing database table, RLS policies, is_store_owner() function, and product-images bucket policies configured in Supabase.
C. Upload all four files to the same website folder:
   index.html
   admin.html
   config.js
   (README.txt is just these instructions)
D. Customer website: open index.html (or your domain homepage).
E. Owner dashboard: open admin.html directly. Sign in with the owner user created in Supabase Authentication.
F. Confirm the signed-in user UUID is present in public.store_owners. Never share the password or keys.

EXPECTED DATABASE COLUMNS in public.products:
id, name, category, description, price, image_url, published, created_at, updated_at

STORAGE
Bucket name: product-images (public read; authenticated owner insert/update/delete only).

NOTE
This code is prepared for your previously configured Supabase project but is not connected until you fill in config.js and deploy the files. Test on a staging copy first. The admin UI is separate, but real protection is enforced by Supabase Auth + RLS.
