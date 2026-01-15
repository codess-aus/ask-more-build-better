# Ask More, Build Better

A workshop website on using GitHub Copilot effectively - featuring Ask Mode for learning and Agent Mode for building.

## About

This workshop teaches developers how to leverage GitHub Copilot's two powerful modes:

- **Ask Mode**: Empowers learners to ask questions without fear, building confidence and understanding
- **Agent Mode**: Helps senior developers accelerate delivery, refactor legacy code, and surface security flaws

## Features

- 📱 Fully responsive design
- ♿ Accessible for all users
- 🎨 Beautiful gradient design
- 🚀 Fast static site generation with MkDocs
- 📖 Comprehensive workshop content

## Local Development

### Prerequisites

- Python 3.x
- pip

### Setup

1. Clone the repository:
```bash
git clone https://github.com/codess-aus/ask-more-build-better.git
cd ask-more-build-better
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the development server:
```bash
mkdocs serve
```

4. Open your browser to `http://127.0.0.1:8000`

### Building the Site

To build the static site:

```bash
mkdocs build
```

The site will be generated in the `site/` directory.

## Deployment

### GitHub Pages

The site automatically deploys to GitHub Pages when changes are pushed to the `main` branch via GitHub Actions.

### Azure Static Web Apps

To deploy to Azure Static Web Apps:

1. Build the site: `mkdocs build`
2. Deploy the `site/` directory to Azure Static Web Apps
3. Configure your Azure Static Web App to serve the built site

## Project Structure

```
.
├── docs/                  # Markdown content
│   ├── index.md          # Home page
│   ├── ask-mode.md       # Ask Mode guide
│   ├── agent-mode.md     # Agent Mode guide
│   ├── best-practices.md # Best practices
│   ├── stylesheets/      # Custom CSS
│   └── images/           # Images and assets
├── .github/
│   └── workflows/
│       └── deploy.yml    # GitHub Actions deployment
├── mkdocs.yml            # MkDocs configuration
├── requirements.txt      # Python dependencies
└── README.md            # This file
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is part of the NDC Sydney Talk series.

## Author

Codess Australia
# Ask More. Build Better. Burn Out Less- Real Talk on AI, Devs & GitHub Copilot
NDC Sydney 2026 Talk

The pace of tech is relentless. AI is everywhere. And developers, especially juniors are overwhelmed, confused, and afraid to ask for help. Seniors are expected to pick up the slack, but there is no slack. Burnout is real. Layoffs are brutal. And hope feels scarce. But what if AI wasn’t the threat? What if it was the lifeline?

In this talk, I'll share a raw and honest take on how GitHub Copilot can be used right. I’ll show how Ask Mode empowers learners to ask the “million questions” they’re afraid to ask and get answers that build confidence, not dependence. And how Agent Mode helps senior devs accelerate delivery, refactor legacy code, and surface security flaws without losing control of their architecture.

This isn’t a hype session. It’s a call to action: to use AI as a tool for growth, not replacement. To build better software, support each other, and stop burning out. Whether you’re early in career or leading the charge, this talk will challenge your assumptions and leave you with practical ways to thrive in the age of AI.


