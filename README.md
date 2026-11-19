# Little Elsewhere 🌿
A mobile-first travel journal with trips, day-by-day stops, notes, and photo galleries.

## Preview
Open `index.html` in a browser. Without Supabase it runs in local demo mode (trip/stop editing is saved to this browser; photo uploads require Supabase). The sample Dieng trip is demo data and is not automatically uploaded to the cloud.

## Connect Supabase
1. Create a Supabase project. Open **SQL Editor**, paste `supabase.sql`, and run it once on a new project.
2. In **Authentication > Providers > Email**, enable email sign-in. For testing, you may disable email confirmation or confirm your signup email.
3. In **Project Settings > API**, copy the **Project URL** and **publishable key** (or legacy anon key). **Never use a service_role key** in a browser.
4. Host `index.html` on Netlify, Vercel, GitHub Pages, or another static host (or run `python -m http.server 8000` locally). In Supabase **Authentication > URL Configuration**, add your hosted URL to allowed redirect URLs if needed.
5. Tap the gear icon, enter the URL/key, save, then sign up/sign in. New cloud trips and photos will be private in the database to the signed-in user.

## Privacy and caveats
- The storage bucket is **public**, so anyone with a photo URL can view that photo. For private images, use a private bucket with signed URLs and modify the app.
- Deleting a photo or trip removes database records, but uploaded image objects may remain in Storage. Remove unused files through Supabase Storage or add a server-side cleanup function.
- Local demo data is separate from cloud data. Copy your Dieng itinerary into a new cloud trip if you want it synced.
- For a public visitor gallery, add a deliberate publication feature and read-only policies; this starter app is owner-only.
- This is a lightweight starter, not a production-hardened application. Test permissions and auth before sharing publicly.
