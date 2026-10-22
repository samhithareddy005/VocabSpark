# VocabSpark — Vocabulary Flashcard App

A beginner-friendly cloud computing project built with HTML, CSS, JavaScript, and Firebase Firestore.

## Features
- Flip vocabulary cards to reveal meanings
- Previous/next navigation
- Search words and meanings
- Add vocabulary words
- Multiple-choice quiz
- Firebase Firestore cloud database integration
- Firebase Hosting deployment
- Local demo mode before Firebase is configured

## Files
- `index.html` — complete app source code
- `README.md` — setup and deployment instructions

## A. Run the app locally (demo mode)
1. Extract the ZIP file.
2. Open `index.html` in a modern browser.
3. The app runs with 10 sample words and saves added words in that browser's local storage.

This mode is for trying the interface. It does not use cloud storage.

## B. Connect Firebase Firestore
1. Visit https://console.firebase.google.com/ and sign in with a Google account.
2. Click **Create a project** and choose a project name such as `vocabspark-demo`.
3. In the project overview, click the Web icon (`</>`) to register a web app.
4. Copy the Firebase configuration object shown by Firebase.
5. Open `index.html` in a code editor such as Visual Studio Code.
6. In the JavaScript section, replace the placeholder values in `firebaseConfig` with your real values:
   - `apiKey`
   - `authDomain`
   - `projectId`
   - `storageBucket`
   - `messagingSenderId`
   - `appId`
7. In Firebase Console, open **Build → Firestore Database** and create a database.
8. For a classroom demo, configure Firestore rules so only authenticated/authorized users can read or write. Do not publish a database with unrestricted public write access.
9. Serve the project through a local development server (recommended) or Firebase Hosting. ES module imports can fail if you open the file in some browser/file contexts.
10. Reload the page. The status badge should say `Firebase connected`. On first connection, the app seeds its starter words into the `vocabulary` collection.

### Important security note
This starter project does not implement user authentication. Before a public deployment, add Firebase Authentication and restrictive Firestore security rules. Never use unrestricted public read/write rules for a real app. Firebase web configuration is not a substitute for database security rules.

## C. Deploy using Firebase Hosting
1. Install Node.js from https://nodejs.org/ .
2. Open a terminal in the extracted project folder.
3. Install the Firebase CLI:
   `npm install -g firebase-tools`
4. Sign in:
   `firebase login`
5. Initialize hosting:
   `firebase init hosting`
6. Choose your Firebase project.
7. Set the public directory to `.` if using this folder directly.
8. If asked to configure as a single-page app, choose `No`.
9. If asked to overwrite `index.html`, choose `No`.
10. Deploy:
    `firebase deploy`

Firebase will show a hosted URL after deployment.

## Suggested project explanation for viva
**Problem:** Students need a simple way to revise English vocabulary.

**Solution:** A web app displays words and meanings as flashcards, lets users search and add vocabulary, and provides a quiz.

**Cloud component:** Firebase Firestore stores vocabulary in the cloud, and Firebase Hosting publishes the application online.

**Future enhancements:** User login, personal decks, pronunciation audio, spaced repetition, daily goals, and progress reports.
