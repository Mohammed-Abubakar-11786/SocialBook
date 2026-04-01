# SocialBook MERN App – Windows Local Setup

This guide covers the **exact Windows setup process from scratch** to run the SocialBook MERN application locally.

---

## Windows Setup

### 1) Install Git for Windows
Download and install Git:

https://git-scm.com/download/win

---

### 2) Install nvm-windows + Node.js
Install **nvm-windows** first, then run:

```bash
nvm install 20.10.0
nvm use 20.10.0
node -v
npm -v
```

---

### 3) Clone the Repository
```bash
git clone https://github.com/Mohammed-Abubakar-11786/SocialBook-MERN-App.git
cd SocialBook-MERN-App
```

---

### 4) Install MongoDB
You can use either:

- **MongoDB Community Server on Windows**
- **MongoDB Atlas cloud database**

---

### 5) Create a Cloudinary Account
You’ll need:

- `CLOUD_NAME`
- `CLOUD_API_KEY`
- `CLOUD_API_SECRET`

---

### 6) Create a Firebase Project
You’ll need:

- Firebase web app config for the React frontend
- Firebase service account JSON for the Node backend

---

## Install Project Dependencies
Run these in separate folders:

```bash
cd server
npm install

cd ..\\client
npm install
```

---

## Important Repo Note
The backend uses **nodemon**, but it is **not installed in the repo dependencies**.

So on Windows, do **one of these**:

```bash
npm install -g nodemon
```

or run backend with:

```bash
npx nodemon app.js
```

---

## Create `server\\.env`

```env
PORT=3030
FRONTEND_URL=http://localhost:5173
ATLASDB_URL=mongodb://127.0.0.1:27017/NetworkSite
SECRET=your-session-secret
JWT_SECREAT_KEY=your-jwt-secret
CLOUD_NAME=your-cloudinary-cloud-name
CLOUD_API_KEY=your-cloudinary-api-key
CLOUD_API_SECRET=your-cloudinary-api-secret
FIREBASE_SERVICE_ACCOUNT='{"type":"service_account","project_id":"...","private_key_id":"...","private_key":"-----BEGIN PRIVATE KEY-----\\n...\\n-----END PRIVATE KEY-----\\n","client_email":"...","client_id":"...","auth_uri":"https://accounts.google.com/o/oauth2/auth","token_uri":"https://oauth2.googleapis.com/token","auth_provider_x509_cert_url":"https://www.googleapis.com/oauth2/v1/certs","client_x509_cert_url":"...","universe_domain":"googleapis.com"}'
```

---

## Create `client\\.env`

```env
VITE_API_BACKEND_URL=http://localhost:3030/
VITE_API_SOCKET_BACKEND_URL=http://localhost:3030/
VITE_API_FIREBASE_CREDENTIALS='{"apiKey":"...","authDomain":"...","projectId":"...","storageBucket":"...","messagingSenderId":"...","appId":"...","measurementId":"..."}'
VITE_API_ADMIN_NAME=admin
VITE_API_ADMIN_PASS=admin123
```

---

## Run the App
Open **2 terminals**.

### Terminal 1
```bash
cd SocialBook-MERN-App\\server
npx nodemon app.js
```

### Terminal 2
```bash
cd SocialBook-MERN-App\\client
npm run dev
```

Then open:

```text
http://localhost:5173
```

---

## Also Keep in Mind

- If using local MongoDB, make sure the **MongoDB service is running first**.
- The frontend expects port **5173**.
- The backend expects port **3030**.
- Both frontend env URLs should **end with `/`**.
