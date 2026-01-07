# 🏥 MediNotes Pro

> Transform your consultation notes into professional summaries, action items, and patient communications with AI-powered assistance.

MediNotes Pro is a modern SaaS application that helps healthcare professionals streamline their workflow by automatically generating:
- 📋 **Professional Summaries** - Comprehensive medical record summaries from consultation notes
- ✅ **Action Items** - Clear next steps and follow-up actions for every consultation
- 📧 **Patient Emails** - Draft clear, patient-friendly email communications automatically

## ✨ Features

- 🔐 **Secure Authentication** - Powered by Clerk for secure user management
- 🤖 **AI-Powered Processing** - Leverages OpenAI to generate intelligent summaries
- 🎨 **Modern UI** - Beautiful, responsive interface built with Next.js and Tailwind CSS
- ⚡ **Real-time Streaming** - Get instant results with streaming responses
- 🌙 **Dark Mode Support** - Comfortable viewing in any lighting condition

## 🛠️ Tech Stack

- **Frontend**: Next.js 16 (Pages Router), React 19, TypeScript, Tailwind CSS
- **Backend**: FastAPI (Python)
- **Authentication**: Clerk
- **AI**: OpenAI API
- **Deployment**: Vercel

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v18 or higher)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- [Python](https://www.python.org/) (v3.8 or higher)
- [pip](https://pip.pypa.io/) (Python package manager)
- [Git](https://git-scm.com/)
- A [Clerk](https://clerk.com/) account (for authentication)
- An [OpenAI](https://openai.com/) API key

## 🚀 Getting Started

### 1. Clone the Repository

```powershell
git clone <your-repo-url>
cd saas
```

### 2. Install Dependencies

#### Frontend Dependencies

```powershell
npm install
```

#### Backend Dependencies

```powershell
pip install -r requirements.txt
```

### 3. Set Up Environment Variables

Create a `.env.local` file in the root directory with the following variables:

```env
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
CLERK_JWKS_URL=your_clerk_jwks_url

# OpenAI API
OPENAI_API_KEY=your_openai_api_key

# API Configuration (if running backend separately)
API_URL=http://localhost:8000
```

> 💡 **Note**: You can get your Clerk keys from the [Clerk Dashboard](https://dashboard.clerk.com/), and your OpenAI API key from the [OpenAI Platform](https://platform.openai.com/api-keys).

### 4. Run the Development Server

#### Start the Frontend (Next.js)

```powershell
npm run dev
```

The application will be available at [http://localhost:3000](http://localhost:3000).

#### Start the Backend (FastAPI) - Optional

If you're running the backend separately:

```powershell
cd api
uvicorn index:app --reload --port 8000
```

The API will be available at [http://localhost:8000](http://localhost:8000).

> 📝 **Note**: The backend can also be deployed separately (e.g., on Railway, Render, or another service) and the frontend can connect to it via the `API_URL` environment variable.

### 5. Open Your Browser

Navigate to [http://localhost:3000](http://localhost:3000) and start using MediNotes Pro!

## 🚢 Deploying to Vercel

Deploying your application to Vercel is straightforward. Follow these steps using PowerShell:

### Step 1: Install Vercel CLI

```powershell
npm install -g vercel
```

### Step 2: Login to Vercel

```powershell
vercel login
```

This will open your browser to authenticate with Vercel. Once authenticated, you'll be logged in.

### Step 3: Deploy Your Project

Navigate to your project directory and run:

```powershell
vercel
```

Follow the prompts:
- **Set up and deploy?** → Type `Y` and press Enter
- **Which scope?** → Select your account
- **Link to existing project?** → Type `N` for a new project (or `Y` if you have an existing one)
- **Project name?** → Press Enter to use the default or type a custom name
- **Directory?** → Press Enter to use the current directory (`.`)
- **Override settings?** → Type `N` unless you need custom settings

### Step 4: Configure Environment Variables

After the initial deployment, you need to add your environment variables:

```powershell
vercel env add NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY
vercel env add CLERK_SECRET_KEY
vercel env add CLERK_JWKS_URL
vercel env add OPENAI_API_KEY
```

For each variable, you'll be prompted to:
- Enter the value
- Select the environment (Production, Preview, Development) - select all that apply

Alternatively, you can add all environment variables at once through the [Vercel Dashboard](https://vercel.com/dashboard):
1. Go to your project settings
2. Navigate to **Environment Variables**
3. Add each variable with its corresponding value

### Step 5: Redeploy with Environment Variables

After adding environment variables, redeploy your application:

```powershell
vercel --prod
```

This will deploy to your production domain (e.g., `your-project.vercel.app`).

### Step 6: Verify Deployment

Visit your deployment URL (shown in the terminal output) to verify everything is working correctly.

## 📝 Additional Vercel Commands

### Preview Deployments

Create a preview deployment (useful for testing):

```powershell
vercel
```

### View Deployment Logs

```powershell
vercel logs
```

### List All Deployments

```powershell
vercel ls
```

### Remove a Deployment

```powershell
vercel remove <deployment-url>
```

## 🔧 Project Structure

```
saas/
├── api/                 # FastAPI backend
│   └── index.py        # Main API endpoint
├── pages/              # Next.js pages
│   ├── index.tsx       # Landing page
│   ├── product.tsx     # Main application page
│   └── _app.tsx        # App wrapper
├── public/             # Static assets
├── styles/             # Global styles
└── package.json        # Frontend dependencies
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is private and proprietary.

## 🆘 Troubleshooting

### Common Issues

**Issue**: `npm install` fails
- **Solution**: Make sure you're using Node.js v18 or higher. Check with `node --version`

**Issue**: Clerk authentication not working
- **Solution**: Verify your Clerk keys are correct in `.env.local` and match your Clerk dashboard

**Issue**: OpenAI API errors
- **Solution**: Ensure your OpenAI API key is valid and has sufficient credits

**Issue**: Vercel deployment fails
- **Solution**: Check that all required environment variables are set in Vercel dashboard

## 📞 Support

If you encounter any issues or have questions, please open an issue on GitHub.

---

Made with ❤️ for healthcare professionals
