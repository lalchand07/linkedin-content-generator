# LinkedIn Content Generator - Fixed CORS Version

## What Was Fixed

The original version was making direct API calls to Anthropic from the browser, which is blocked by CORS. This version uses a Vercel serverless function as a proxy to handle API calls securely.

## Project Structure

```
linkedin-content-generator/
├── index.html           # Frontend application
├── api/
│   └── claude.js       # Serverless API proxy
├── vercel.json         # Vercel configuration
└── README.md          # This file
```

## How to Deploy to Vercel

### Option 1: Deploy via Vercel CLI

1. Install Vercel CLI (if not already installed):
```bash
npm install -g vercel
```

2. Navigate to the project directory:
```bash
cd linkedin-content-generator
```

3. Deploy:
```bash
vercel
```

4. Follow the prompts and your app will be deployed!

### Option 2: Deploy via Vercel Dashboard

1. Push this folder to a GitHub repository
2. Go to https://vercel.com/new
3. Import your repository
4. Vercel will automatically detect the configuration
5. Click "Deploy"

### Option 3: Deploy via Drag & Drop

1. Zip the entire `linkedin-content-generator` folder
2. Go to https://vercel.com/new
3. Drag and drop the zip file
4. Click "Deploy"

## How It Works

1. **Frontend** (`index.html`): User interface where users configure and generate LinkedIn posts
2. **Backend** (`api/claude.js`): Serverless function that:
   - Receives API key and prompt from frontend
   - Makes the actual API call to Anthropic
   - Returns the response to frontend
   - Handles CORS properly

## Features

- Generate LinkedIn posts optimized for engagement
- Create visual flow diagrams automatically
- Multiple content types (tools, hacks, tutorials, case studies, concepts)
- Target different audiences (developers, business owners, marketers, beginners)
- Quick examples to get started

## Usage

1. Open your deployed app
2. Enter your Claude API key (get from console.anthropic.com)
3. Select content type and target audience
4. Describe your topic
5. Click "Generate LinkedIn Post + Visual"
6. Copy the post and download the diagram

## Security Note

The API key is sent to your serverless function (not stored anywhere) and used only for that request. Since this is your own Vercel deployment, the serverless function runs in your account and is secure.

## Troubleshooting

If you still see CORS errors after deploying:
1. Make sure you deployed the entire folder including the `api` directory
2. Clear your browser cache
3. Check Vercel deployment logs for any errors
4. Ensure the serverless function deployed correctly (check Vercel dashboard → Functions tab)
