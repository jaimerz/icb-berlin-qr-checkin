# IBC Berlin QR Check-In

A web app for managing school or church years and tracking student movements via QR code scanning. Designed for real-time check-ins and class management, this app helps school or church leaders and admins efficiently monitor where students are throughout the year.

[View the App](https://icb-berlin-qr-checkin.web.app)

## Features

- 📅 Multi-year school or church year management
- 📋 Student import, management, and QR code generation
- 📍 Real-time student location tracking
- 🔄 QR code scanning for class check-ins and returns
- 🛠️ Admin and Leader role-based access
- 🖨️ Customizable QR badge downloads (PDF & ZIP)
- 📝 Class management with live updates
- 🔒 Firebase authentication and security rules
- ☁️ Hosted on Firebase Hosting with GitHub Actions for deployment

---

## Technologies Used

- **Frontend:** React (Vite)
- **Backend:** Firebase Firestore
- **Authentication:** Firebase Auth
- **Hosting:** Firebase Hosting (Production and Preview channels)
- **Deployment:** GitHub Actions
- **QR Code Generation:** `qrcode` package
- **PDF Generation:** `pdf-lib`

---

## Project Structure

```text
├── public/            # Static assets
├── src/
│   ├── components/    # UI components
│   ├── pages/         # Page views
│   ├── utils/         # Firebase and helper functions
│   ├── contexts/      # Global state providers (Auth, User)
│   └── App.tsx        # Main app routing
├── .github/           # GitHub workflows
├── firebase.json      # Firebase hosting config
├── package.json
└── README.md
```

---

## Setup Instructions

### Prerequisites
- Node.js
- Firebase CLI
- GitHub account (for GitHub Actions deployment)

### Installation
1. Clone the repo:
   ```bash
   git clone https://github.com/jaimerz/icb-berlin-qr-checkin.git
   cd icb-berlin-qr-checkin
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Configure Firebase:
   - Set up Firebase project with Authentication and Firestore.
   - Update `firebaseConfig` in `src/utils/firebase.ts` with your project credentials.

4. Run locally:
   ```bash
   npm run dev
   ```

---

## Deployment

The app is deployed via GitHub Actions to **Firebase Hosting**:
- **Main branch:** deployed to the production site (`live` channel)
- **Feature branches:** automatically deployed to Firebase preview channels for testing

Firebase is used for hosting, database, and authentication. Separate preview and production Firestore databases can be configured if needed.

---

## Roles and Access

- **Admins** can:
  - Manage years, classes, and students
  - Import students via CSV
  - Generate QR badges (PDF/ZIP)
  - Monitor live student status
- **Leaders** can:
  - Scan students to track movement
  - View student locations

---

## Key Workflows

- **Student Management:** Add individually or import via CSV. Each student has a deterministic QR code based on their name, church, and year ID.
- **Scanning Flow:** Leaders scan students when they leave or return. Scans update the student’s current location in real time.
- **Class Logs:** Each movement is logged, including who performed the scan.
- **Badge Export:** QR codes can be exported as printable PDFs or ZIP files with individual QR images.

---

## Roadmap

- [x] Admin and Leader role separation
- [x] Class management page
- [x] Bulk import students
- [x] PDF and ZIP QR code export with customization
- [x] Real-time student location dashboard
- [ ] Multi-database support (preview vs. production)
- [ ] Enhanced error handling and confirmation flows
- [ ] UI/UX improvements for mobile

---

## Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

### Branching Model
- `main`: Production
- `feature/*`: Development branches for new features or fixes

---

## License

[MIT License](LICENSE)

---

## Special Thanks

Built with love for school and church communities ❤️ Special thanks to all leaders, admins, and testers who contributed to shaping this project.
