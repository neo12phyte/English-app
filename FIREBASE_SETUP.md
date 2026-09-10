# LinguaQuest Firebase setup

## 1. Add a Firebase Web App
Open Firebase Console, create/open your project, add a **Web App**, and copy its `firebaseConfig` object.

## 2. Enable family login
Go to **Authentication → Sign-in method** and enable **Email/Password**.

LinguaQuest uses one family Firebase account. Sign into the same account on each tablet/computer. The app keeps separate child profiles, XP, coins, chores, goals, and learning progress inside that family account.

## 3. Create Firestore
Open **Firestore Database**, create the database, then publish the rules from `firestore.rules`.

## 4. Enable Cloud Storage
Open **Storage**, enable it, then publish the rules from `storage.rules`.

Cloud Storage is used for:
- pronunciation/listening MP3 or WAV files uploaded by a parent
- optional child speaking recordings

## 5. Connect the app
Open `index.html` and search for:

`BUILT_IN_FIREBASE_CONFIG`

Paste your Firebase values there, for example:

```js
const BUILT_IN_FIREBASE_CONFIG={
  apiKey:"...",
  authDomain:"your-project.firebaseapp.com",
  projectId:"your-project",
  storageBucket:"your-project.firebasestorage.app",
  messagingSenderId:"...",
  appId:"..."
};
```

You can also paste the Firebase config JSON through the Parent Dashboard. Embedding it in `index.html` is easier when several devices use the app.

## 6. Upload to GitHub Pages
Put `index.html` in the repository root and enable GitHub Pages from the `main` branch/root folder.

## Default Parent PIN
`2468`

Change it from the Parent Dashboard.

## Speaking privacy
Speaking recording storage is optional and can be turned off in the Parent Dashboard. Microphone access always requires the browser/device permission prompt.
