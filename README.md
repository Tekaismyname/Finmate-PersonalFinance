# FinMate - Personal Finance Management App

A comprehensive personal finance management application built with Expo, React Native, TypeScript, and Firebase.

## Features

- ✅ **Authentication**: Email/password signup, signin, forgot password
- ✅ **Dashboard**: Balance summary, income/expense tracking, recent transactions
- ✅ **Transactions**: Add, view, and manage income/expense/transfer transactions
- ✅ **Accounts**: Manage multiple accounts (cash, bank, e-wallet, credit)
- ✅ **Categories**: Default and custom categories for organizing transactions
- ✅ **Budgets**: Set monthly budgets and track spending (coming soon)
- ✅ **Goals**: Create savings goals and track progress (coming soon)
- ✅ **Bills**: Manage recurring bills and reminders (coming soon)
- ✅ **Reports**: View insights and analytics (coming soon)
- ✅ **Theme**: Light/dark/system theme support
- ✅ **Offline**: Firebase offline persistence enabled

## Tech Stack

- **Framework**: Expo (React Native)
- **Language**: TypeScript
- **Navigation**: expo-router
- **Backend**: Firebase (Auth + Firestore)
- **State Management**: Zustand
- **Forms**: react-hook-form + zod
- **Charts**: react-native-chart-kit
- **Icons**: @expo/vector-icons
- **Dates**: dayjs

## Prerequisites

- Node.js 18+ and npm
- Expo CLI
- Firebase project (see Firebase Setup below)
- iOS Simulator (Mac) or Android Emulator

## Installation

1. **Clone or navigate to the project directory**

```bash
cd CashFlowy_HKD
```

2. **Install dependencies**

```bash
npm install
```

3. **Set up Firebase** (see FIREBASE_SETUP.md for detailed instructions)

4. **Create `.env` file**

Copy `.env.example` to `.env` and fill in your Firebase credentials:

```bash
cp .env.example .env
```

Edit `.env` with your Firebase configuration:

```
EXPO_PUBLIC_FIREBASE_API_KEY=your_api_key_here
EXPO_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project_id.firebaseapp.com
EXPO_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
EXPO_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project_id.appspot.com
EXPO_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
EXPO_PUBLIC_FIREBASE_APP_ID=your_app_id
```

## Running the App

### Development Mode

```bash
# Start Expo dev server
npx expo start

# Run on iOS simulator (Mac only)
npx expo run:ios

# Run on Android emulator
npx expo run:android

# Run on web
npx expo start --web
```

### Production Build

```bash
# Build for iOS
npx expo build:ios

# Build for Android
npx expo build:android
```

## Project Structure

```
CashFlowy_HKD/
├── app/                          # Expo Router screens
│   ├── (auth)/                   # Authentication screens
│   │   ├── welcome.tsx
│   │   ├── signup.tsx
│   │   ├── signin.tsx
│   │   └── forgot-password.tsx
│   ├── (tabs)/                   # Main app tabs
│   │   ├── home.tsx
│   │   ├── transactions.tsx
│   │   ├── budgets.tsx
│   │   ├── reports.tsx
│   │   └── settings.tsx
│   ├── transactions/             # Transaction screens
│   │   └── add.tsx
│   ├── _layout.tsx               # Root layout
│   └── index.tsx                 # Entry point
├── src/
│   ├── components/               # Reusable components
│   │   ├── Button.tsx
│   │   ├── Input.tsx
│   │   ├── Card.tsx
│   │   ├── EmptyState.tsx
│   │   └── LoadingSpinner.tsx
│   ├── services/                 # Firebase services
│   │   ├── firebase.ts
│   │   ├── auth.service.ts
│   │   ├── firestore.service.ts
│   │   └── seed.service.ts
│   ├── store/                    # Zustand stores
│   │   ├── authStore.ts
│   │   └── appStore.ts
│   ├── theme/                    # Theme system
│   │   ├── tokens.ts
│   │   └── index.ts
│   ├── types/                    # TypeScript types
│   │   └── index.ts
│   └── utils/                    # Utility functions
│       ├── currency.ts
│       ├── date.ts
│       ├── analytics.ts
│       └── validation.ts
├── .env.example                  # Environment variables template
├── .gitignore
├── app.json                      # Expo configuration
├── package.json
├── tsconfig.json
└── README.md
```

## Firebase Setup

See [FIREBASE_SETUP.md](./FIREBASE_SETUP.md) for detailed instructions on:

- Creating a Firebase project
- Enabling Authentication
- Setting up Firestore
- Deploying security rules
- Getting configuration credentials

## Security Rules

Deploy the Firestore security rules from `firestore.rules`:

```bash
firebase deploy --only firestore:rules
```

## Default Categories

The app automatically seeds default income and expense categories for new users:

**Income Categories:**

- Salary, Freelance, Investment, Business, Gift, Other Income

**Expense Categories:**

- Food & Dining, Transportation, Shopping, Bills & Utilities, Entertainment, Healthcare, Education, Housing, Personal Care, Travel, Insurance, Other Expense

## Features Roadmap

- [x] Authentication (email/password)
- [x] User profile management
- [x] Dashboard with balance summary
- [x] Transaction management
- [x] Theme support (light/dark)
- [ ] Account management (CRUD)
- [ ] Budget tracking with alerts
- [ ] Savings goals
- [ ] Recurring bills
- [ ] Charts and reports
- [ ] Export to CSV
- [ ] Backup/restore
- [ ] Google Sign-In
- [ ] Push notifications

## Troubleshooting

### Firebase Connection Issues

If you see Firebase connection errors:

1. Verify `.env` file has correct credentials
2. Check Firebase project is active
3. Ensure Firestore database is created
4. Verify security rules are deployed

### Build Errors

If you encounter build errors:

```bash
# Clear cache and reinstall
rm -rf node_modules
npm install
npx expo start -c
```

## License

MIT

## Support

For issues and questions, please create an issue in the repository.
