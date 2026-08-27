# 🍬 Uday & Veer Snack Shop

A candy ordering website for students! Place orders for your favorite snacks and choose a meetup spot to collect them.

## 🚀 Features

- **Product catalog** with real images, stock badges, and prices
- **Order modal** with name, quantity, meetup location selector, and optional message
- **Meetup spots**: 7th Grade Boys Bathroom, Pod 7-1/7-2/7-3/7-4, Main Entrance, 7th Grade Entrance, 6th Grade Entrance
- **Admin dashboard** (Gmail-locked) with:
  - Live pending orders view
  - Approve / Reject orders
  - Undo decisions
  - Full order history with filters
  - Stock management for each product

## 🛠️ Setup (Firebase)

> Do this once — it only takes ~5 minutes!

### 1. Create a Firebase project
1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Click **Add project** → name it (e.g. `snack-shop`) → click through
3. Once created, click **Web** (</>) icon to add a web app
4. Register the app and copy the `firebaseConfig` object

### 2. Add your Firebase config
In both `index.html` and `admin.html`, find this section:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  ...
};
```

Replace the placeholder values with the ones from your Firebase project.

### 3. Enable Firestore
1. In Firebase console → **Firestore Database** → **Create database**
2. Start in **test mode** (you'll add rules later)
3. Choose any region → Done

### 4. Enable Google Auth
1. Firebase console → **Authentication** → **Sign-in method**
2. Click **Google** → Enable → Save

### 5. Set admin emails
In `admin.html`, find:

```js
const ADMIN_EMAILS = [
  "uday@gmail.com",   // Replace with Uday's actual Gmail
  "veer@gmail.com"    // Replace with Veer's actual Gmail
];
```

Replace with the actual Gmail addresses.

### 6. Deploy Firestore rules
1. Install Firebase CLI: `npm install -g firebase-tools`
2. `firebase login`
3. `firebase init firestore` (select your project)
4. Copy the contents of `firestore.rules` into the rules file
5. `firebase deploy --only firestore:rules`

### 7. Host the site (optional)
To deploy for free with Firebase Hosting:
```bash
firebase init hosting
# set public directory to . (current folder)
# single-page app: No
firebase deploy --only hosting
```

Or just use **GitHub Pages**:
1. Repo → Settings → Pages
2. Source: Deploy from branch → `main` → `/ (root)` → Save

---

## 🍭 Products
| Product | Price | Default Stock |
|---------|-------|---------------|
| Sour Patch Kids | $3 | 20 |
| Watermelon Sour Patch | $3 | 20 |
| Snickers Bar | $5 | 15 |

---

Made with ❤️ by Uday & Veer
