# LyzrCrew

**AI-Powered B2B Lead Generation SaaS** — Automate corporate research and outreach with CrewAI agents, delivering personalized cold emails at scale.

LyzrCrew is a full-stack SaaS platform that uses AI-driven research to automate company intelligence, identify sales opportunities, and craft outreach messages. Built with FastAPI, HTMX, and Google’s Gemini AI, it delivers a responsive web experience with real-time progress tracking, credit-based billing, and secure OTP authentication.

## 📋 Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Technologies](#technologies)
- [License](#license)

## Features

- **🤖 AI Agent Crew**: Multi-agent system using CrewAI for comprehensive company research and personalized email generation
- **📊 Real-Time Tracking**: Live progress updates for bulk research jobs with HTMX-powered dashboards
- **💳 Credit System**: Stripe-integrated billing with 50 credits per $10 pack
- **🔐 Secure Auth**: OTP email verification with Resend API integration
- **📈 Bulk Processing**: Handle multiple companies simultaneously with CSV export capabilities
- **🎨 Modern UI**: Glassmorphism design with Tailwind CSS and responsive HTMX interactions

## Prerequisites

- Python 3.11+
- Node.js 18+ (for Tailwind CSS, optional for development)
- SQLite (included with Python)
- API keys for:
  - Google Gemini AI
  - Stripe (for payments)
  - Resend (for email delivery)

## Installation

1. **Clone the repository:**
   \`\`\`bash
   git clone https://github.com/yourusername/lyzrcrew.git
   cd lyzrcrew
   \`\`\`

2. **Create virtual environment:**
   \`\`\`bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   \`\`\`

3. **Install dependencies:**
   \`\`\`bash
   pip install -r requirements.txt
   \`\`\`

4. **Configure environment:**
   \`\`\`bash
   cp .env.example .env
   # Edit .env with your API keys
   \`\`\`

5. **Run the application:**
   \`\`\`bash
   uvicorn api:app --reload
   \`\`\`

   Open [http://localhost:8000](http://localhost:8000) in your browser.

## Quick Start

### Single Company Research

1. Sign up with email verification
2. Purchase credits via Stripe checkout
3. Enter a company name and pitch goal
4. Get AI-generated research and personalized cold email

**Example API Usage:**
\`\`\`python
import requests

# Start research job
response = requests.post("http://localhost:8000/api/htmx/research", 
    data={"company_name": "Tesla", "pitch_goal": "EV charging solutions"})
print(response.json())
\`\`\`

### Bulk Research

Upload a CSV with multiple companies for batch processing:

\`\`\`csv
company_name,pitch_goal
Tesla,EV infrastructure
SpaceX,Satellite communications
\`\`\`

**Bulk API Example:**
\`\`\`python
files = {"file": open("companies.csv", "rb")}
response = requests.post("http://localhost:8000/api/htmx/bulk-research", files=files)
\`\`\`

## Technologies

- **Backend**: FastAPI, SQLAlchemy, SQLite
- **Frontend**: HTMX, Tailwind CSS, Jinja2 templates
- **AI**: CrewAI, Google Gemini AI (via LiteLLM)
- **Payments**: Stripe API
- **Email**: Resend API
- **Tools**: DuckDuckGo Search, Custom research tools

## 👨‍💻 Author & Contact

**Uziel Fassi** *Computer Science Undergraduate & Full-Stack / AI Engineer*
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/uziel-fassi-08840a287/) 
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit%20Site-black?style=for-the-badge&logo=framer&logoColor=white)](https://myportfoliouzielf.framer.website)
[![GitHub](https://img.shields.io/badge/GitHub-View%20Profile-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Uziel-Fassi)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
