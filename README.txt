FREE FIRE STUDIO — SETUP GUIDE
==============================

WHAT IS INCLUDED
- Responsive mobile-first website
- Email/password account creation and login
- Anonymous guest login (no email/password required)
- Public profile with gaming name, bio, profile picture
- Public image posts
- Edit/delete your own post caption and delete your own posts
- Likes with a per-user like record
- Canvas thumbnail maker and PNG download
- Admin moderation interface (secure configuration required)
- Firestore and Storage security rules

IMPORTANT
This is starter code. Public community features do NOT work until you connect a Firebase project and publish the security rules. Do not put service-account keys in browser code. Test rules before public launch. The admin interface alone does not grant secure admin rights: admin UID must match in BOTH index.html and firestore.rules.

FIREBASE SETUP
1. Go to https://console.firebase.google.com/ and create a project.
2. Add a Web App to the project and copy its Firebase config.
3. In index.html, replace each PASTE_... value in firebaseConfig with the values from Firebase.
4. In Firebase Authentication > Sign-in method, enable Email/Password and Anonymous.
5. In Firestore Database, create a database.
6. In Storage, create a storage bucket if your Firebase plan/project supports it. Review current pricing and quotas before public use.
7. Publish firestore.rules in Firestore > Rules.
8. Publish storage.rules in Storage > Rules.
9. Create your first account on the website. In Authentication > Users, copy your account UID.
10. Replace PASTE_ADMIN_UID_HERE in index.html's ADMIN_UIDS with your UID.
11. Replace REPLACE_WITH_YOUR_ADMIN_UID in firestore.rules with the same UID, then publish the rules again.
12. Host the files on a static host that serves index.html over HTTPS (for example GitHub Pages). Do not open index.html as file:// because browser module imports and Firebase require a web origin.

HOSTING
- Put index.html in a GitHub repository.
- Open repository Settings > Pages.
- Choose deploy from branch, select main and /(root), then Save.
- Wait for the Pages URL to become available.

GUEST LOGIN NOTE
- Guest users receive an anonymous Firebase UID and can post/like under that identity. Guest identity is tied to the browser/app session; clearing site data or switching devices may make it difficult to recover. For a lasting profile, create an email/password account. Guest login must be enabled in Firebase Authentication.

NOTES / LIMITATIONS
- The post editor currently edits the caption; image replacement is not included in this starter version.
- Deleting a Firestore post does not automatically delete its uploaded image from Storage, so images may need manual cleanup.
- This starter has no comments, password reset UI, email verification UI, reporting workflow, or rate limiting.
- Public image uploads can create moderation, privacy, and storage costs. Add reporting, rate limits, and abuse controls before promoting it publicly.
- Firebase quotas, pricing and storage availability change; check the current Firebase console/pricing page.
- Free Fire and Garena are trademarks of their respective owners. This fan-made project is not affiliated with them.
