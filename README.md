# Riley Xu - Portfolio Website

Personal portfolio website for Riley Xu, a Software Engineer based in New York specializing in data systems and intelligent applications.

## Tech Stack

- **Frontend**: React 19.2.0 + Vite 7.2.4
- **Styling**: Tailwind CSS v4.1.18
- **Icons**: Lucide React
- **AI**: Google Gemini API (gemini-2.0-flash-exp)
- **Markdown**: Marked.js for rendering AI responses
- **Deployment**: GitHub Pages with GitHub Actions

## Setup Instructions

### Prerequisites

- Node.js (v20 or higher)
- npm
- Google Gemini API key ([Get one here](https://ai.google.dev/))

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/yxu399/yxu399.github.io.git
   cd yxu399.github.io
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure environment variables**
   ```bash
   cp .env.example .env
   ```

   Edit `.env` and add your Gemini API key:
   ```
   VITE_GEMINI_API_KEY=your_actual_api_key_here
   ```

4. **Start development server**
   ```bash
   npm run dev
   ```

   Open [http://localhost:5173](http://localhost:5173) in your browser.

### Building for Production

```bash
npm run build
```

The build output will be in the `dist/` directory.

## Deployment

This project uses **GitHub Actions** for automated deployment to GitHub Pages.

### GitHub Actions Setup (Recommended)

1. **Add GitHub Secret**:
   - Go to your repository on GitHub
   - Navigate to **Settings** → **Secrets and variables** → **Actions**
   - Click **New repository secret**
   - Name: `VITE_GEMINI_API_KEY`
   - Value: Your Gemini API key
   - Click **Add secret**

2. **Enable GitHub Pages**:
   - Go to **Settings** → **Pages**
   - Source: **GitHub Actions**
   - Save

3. **Deploy**:
   - Push to the `main` branch
   - GitHub Actions will automatically build and deploy
   - Your site will be live at `https://yxu399.github.io`

The workflow file is located at [.github/workflows/deploy.yml](.github/workflows/deploy.yml).

### Manual Deployment (Alternative)

If you prefer manual deployment:

```bash
npm run build
npm run deploy
```

**Note**: Manual deployment won't inject the API key, so AI features won't work on the deployed site.

## Project Structure

```
riley-portfolio/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions workflow
├── src/
│   ├── components/
│   │   └── AIChatWidget.jsx   # AI chatbot component
│   ├── App.jsx                 # Main app component
│   ├── main.jsx                # React entry point
│   └── index.css               # Global styles
├── .env.example                # Environment variable template
├── .gitignore
├── package.json
├── vite.config.js
├── tailwind.config.js
└── postcss.config.js
```

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `VITE_GEMINI_API_KEY` | Google Gemini API key for AI features | Yes |

## Features in Detail

### AI Chatbot
- Click "Chat with AI Riley" button in the bottom right
- Ask questions about Riley's experience, skills, and projects
- Powered by Gemini 2.0 Flash model
- Supports markdown formatting in responses

### Project Analysis
- Click "Analyze Stack" on any project card
- Get AI-generated insights about the technology stack
- Explains design decisions and implementation details

## Troubleshooting

### AI Features Not Working

1. **Check API Key**: Ensure `VITE_GEMINI_API_KEY` is set correctly
2. **Restart Dev Server**: After changing `.env`, restart with `npm run dev`
3. **Check Console**: Open browser DevTools to see error messages
4. **Verify GitHub Secret**: For production, ensure the secret is set in GitHub

### Deployment Issues

- Ensure the repository name is `yxu399.github.io` (must match username)
- Check GitHub Actions tab for build logs
- Verify GitHub Pages is enabled in repository settings

## License

MIT

## Contact

Riley Yingjuan Xu - [GitHub](https://github.com/yxu399)
