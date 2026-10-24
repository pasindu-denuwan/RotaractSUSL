[README.md](https://github.com/user-attachments/files/33900898/README.md)
Rotaract SUSL

The official website and digital platform for the Rotaract Club of Sabaragamuwa University of Sri Lanka. The project brings the club's public information, projects, events, gallery, membership-related pages, and administrative tools together in one place.

🌐 Website: https://www.rotaractsusl.org

Features

- Club information — learn about the club, its leadership, and development team.
- Projects and events — browse club activities and project information.
- Gallery — view photos and highlights from club activities.
- Magazine — access the club's magazine content.
- Membership and applications — pages for joining the club and applying for projects.
- Event registration — registration-related page and workflows.
- User authentication — login, registration/authentication, email verification, and password recovery pages.
- User profile — profile and membership-related pages.
- Relief support workflows — relief request and relief management pages.
- Administration — administrative pages for managing selected platform content.
- Responsive interface and animations — built with reusable UI components and Framer Motion.

> Available features and access may depend on Firebase configuration, environment variables, and the permissions configured for the deployment.

Technology Stack

- Framework: Next.js (App Router)
- Frontend: React
- Language: JavaScript and TypeScript
- Styling: CSS and Tailwind CSS tooling
- Authentication and database: Firebase Authentication and Cloud Firestore
- File storage: Firebase Storage
- Media management: Cloudinary
- Email integrations: Resend and other configured email services
- UI and animation: Framer Motion, Lucide React, React Icons, Sonner
- QR functionality: `react-qr-code` and `html5-qrcode`

Project Structure

```text
RotaractSUSL/
├── app/
│   ├── about/              # About the club
│   ├── admin/              # Administrative pages
│   ├── api/                # API routes
│   ├── apply-projects/     # Project applications
│   ├── auth/               # Authentication page
│   ├── components/         # Shared UI components
│   ├── contact/            # Contact page
│   ├── developers/         # Development team
│   ├── event_register/     # Event registration
│   ├── gallery/            # Gallery
│   ├── join/               # Membership-related page
│   ├── leadership/         # Club leadership
│   ├── login/              # Login
│   ├── magazine/           # Magazine
│   ├── manage-relief/      # Relief management
│   ├── profile/            # User profile
│   ├── projects/           # Projects
│   ├── relief-request/     # Submit a relief request
│   ├── relief-requests/    # Relief requests
│   ├── users/              # User-related pages
│   ├── verify-email/       # Email verification
│   ├── verify-membership/  # Membership verification
│   ├── globals.css         # Global styles
│   ├── layout.jsx          # Root layout
│   └── page.tsx            # Home page
├── assets/                 # Shared asset references
├── lib/                    # Firebase and utility modules
├── public/                 # Static assets
├── .env.example            # Environment variable template
├── firestore.rules         # Firestore security rules
├── storage.rules           # Firebase Storage security rules
└── package.json
```

Getting Started

Prerequisites

- Node.js (use a current LTS release compatible with the installed Next.js version)
- npm
- A Firebase project configured for the application
- Additional service accounts/API keys for any integrations you plan to use, such as Cloudinary or email delivery

1. Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd RotaractSUSL
```

Replace `<YOUR_REPOSITORY_URL>` with the Git repository URL.

2. Install dependencies

```bash
npm install
```

3. Configure environment variables

Create a local `.env.local` file based on `.env.example`.

```bash
cp .env.example .env.local
```

On Windows PowerShell, you can use:

```powershell
Copy-Item .env.example .env.local
```

Add the credentials for the services you have configured. The template includes variables for:

- Firebase client configuration
- Firebase Admin SDK
- Resend and Gmail/email configuration
- Cloudinary
- Application secret configuration

Only fill in variables required by the features you intend to run. Check the code for the exact variables used by each integration.

Security notes
- Never commit `.env.local` or real API keys, private keys, passwords, or service-account credentials.
- Do not expose private credentials through `NEXT_PUBLIC_` variables. Values prefixed with `NEXT_PUBLIC_` are available to browser-side code.
- Review `firestore.rules` and `storage.rules` before deploying. Configure least-privilege access and protect administrative operations.
- Use a strong, appropriately managed secret for any application secret variable.

4. Run the development server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

5. Build for production

```bash
npm run build
npm run start
```

Run the production server only after a successful build and after setting the required production environment variables.

6. Run linting

```bash
npm run lint
```

Firebase Setup

1. Create or select a project in the [Firebase Console](https://console.firebase.google.com/).
2. Enable the authentication providers required by the application.
3. Configure Cloud Firestore and Firebase Storage.
4. Add the Firebase client configuration to `.env.local`.
5. Configure Firebase Admin credentials securely if server-side routes require them.
6. Review and deploy the rules in `firestore.rules` and `storage.rules`.
7. Confirm that the required collections, documents, and storage paths match the data structures expected by the application.

The home page reads project/event data from the Firestore `events` collection and requests gallery content through an API route. Your Firebase data and API integrations must be configured for those sections to populate correctly.

Available Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the local development server |
| `npm run build` | Create a production build |
| `npm run start` | Start the production server |
| `npm run lint` | Run ESLint |

Deployment

Deploy to a platform that supports Next.js, such as [Vercel](https://vercel.com/), or another compatible hosting environment.

Before deployment:

1. Add the required environment variables to the hosting provider.
2. Configure Firebase authorized domains and authentication settings.
3. Verify Firestore and Storage security rules.
4. Check server-side email, media, and Firebase Admin integrations.
5. Test login, verification, forms, gallery loading, and administrative permissions.
6. Run `npm run build` and resolve any build errors.
7. Confirm that no credentials or local environment files are committed.

Contributing

Contributions and improvements are welcome. A typical workflow is:

1. Create a feature branch.
2. Make a focused change.
3. Test the affected functionality.
4. Run linting and a production build where possible.
5. Open a pull request with a clear summary of the change.

Development Team

Visit the website's Developers page for project team information.

License

No license information is specified in this repository. Unless a license is added, the code should not be assumed to be open source or available for unrestricted reuse.
