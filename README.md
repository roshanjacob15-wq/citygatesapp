# CityGates Hub

Rotas, service planning, teams, people, group chat, bulletin board, events and check-in for CityGates Church Dubai.
Built with Next.js 14 and Supabase, phone first, in the CityGates brand colours and type.

## Try it now (demo mode)

    npm install
    npm run dev

Open http://localhost:3000. With no environment variables set, the app runs in **demo mode**: sample data lives in
your browser and a "View as" switcher in the sidebar (or More menu on a phone) lets you try the admin, leader and
member experiences. "Reset sample data" restores the original.

## Go live (real accounts, shared data, live chat)

1. Create a free project at supabase.com.
2. SQL editor: paste and run `supabase/schema.sql`. It creates every table, the access rules (row level
   security) and the trigger that links a sign-in to the person record an admin created.
3. Authentication, URL configuration: set Site URL to your deployed address (and http://localhost:3000 for testing).
4. Copy `.env.example` to `.env.local` and fill in the project URL and anon key (Project settings, API).
5. `npm run dev` to test, then deploy to Vercel with the same two environment variables.
6. Sign in with your own email first: the first person to sign in becomes the admin. After that, add everyone
   else under People (their email is what they sign in with) and set access levels on their profile.

## Access levels

- **Admin**: everything, including creating teams and setting access levels.
- **Leader**: builds rotas and services, manages team members, people, events, check-in and pinning posts.
- **Member**: their own profile and blocked dates, accept/decline/swap slots, claim open slots, chat in their groups,
  post on the board, sign up to events.

## Notes

- Team chats are created automatically with each team and kept in step with team membership.
- Rota warnings flag anyone assigned on a blocked date or already serving in the same service.
- Email reminders are not wired up yet (see next steps); the data is ready for them.
