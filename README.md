# Chamber AI Assistant

A comprehensive AI-powered Telegram Agent for the Chamber Toastmasters Club in Kyiv, Ukraine. This bot provides intelligent assistance about Toastmasters International, club operations, educational programs, and membership information with advanced memory management and Google Sheets integration.

## 🌟 Features

- **AI-Powered Conversations**: Intelligent responses using OpenRouter API with ChatGPT-4
- **Memory Management**: Persistent conversation history with configurable memory limits
- **Google Sheets Integration**: Automatic logging of user interactions and inquiries
- **Comprehensive Knowledge Base**: Detailed information about Toastmasters International and Chamber Club
- **Robust Error Handling**: Comprehensive error management and recovery mechanisms
- **Auto-Scaling**: Built-in keep-alive system for cloud deployment (Render.com optimized)
- **Health Monitoring**: Real-time bot status and performance metrics
- **Markdown Support**: Rich text formatting in responses
- **Ukrainian Time Zone**: Automatically formats timestamps for Kyiv time zone (EEST)

## 🚀 Quick Start

### Prerequisites

- Node.js 14+
- Telegram Bot Token (from [@BotFather](https://t.me/BotFather))
- OpenRouter API Key
- Google Service Account with Sheets API access

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd telegram-toastmasters-bot

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env
# Edit .env with your credentials
```

### Environment Variables

Create a `.env` file with the following variables:

```env
# Telegram Bot Configuration
TELEGRAM_BOT_TOKEN=your_telegram_bot_token_here

# OpenRouter AI Configuration
OPENROUTER_API_KEY=your_openrouter_api_key_here

# Google Sheets Integration
GOOGLE_SERVICE_ACCOUNT_EMAIL=your-service-account@project.iam.gserviceaccount.com
GOOGLE_PRIVATE_KEY="-----BEGIN PRIVATE KEY-----\nYOUR_PRIVATE_KEY_HERE\n-----END PRIVATE KEY-----\n"
GOOGLE_SHEET_ID=your_google_sheet_id_here

# Server Configuration
PORT=3000
RENDER_EXTERNAL_URL=https://your-render-app.onrender.com
```

### Running the Bot

```bash
# Development mode
npm run dev

# Production mode
npm start
```

## 📚 Bot Knowledge Base

The bot is equipped with comprehensive knowledge about:

### Toastmasters International
- Organization history and structure
- Global presence (16,800+ clubs in 145+ countries)
- Mission, vision, and values
- Leadership opportunities

### Educational Programs
- **Pathways Learning Experience**: 11 learning paths with 5 levels each
- Speech types and evaluation systems
- Club roles and meeting structure
- Contest information and requirements

### Chamber Toastmasters Club (Kyiv)
- Meeting schedule: 1st & 3rd Wednesday, 19:15 Kyiv time
- Membership options (Global Track: $60/6 months, Local Track: ~$2.50/month)
- Club-specific rules and procedures
- Officer team and contact information

### Resources Library
- Evaluation forms and speech timers
- Meeting agenda templates and role guides
- Educational videos and tutorials
- Contest resources and preparation materials

## 🔧 Technical Architecture

### Core Components

1. **Memory Management System**
   - Stores conversation history per user
   - Configurable memory limit (default: 10 messages)
   - Automatic cleanup of old messages

2. **Google Sheets Logger**
   - Automatic logging of all user interactions
   - Captures username, message, timestamp, and user details
   - Uses service account authentication

3. **AI Integration**
   - OpenRouter API with ChatGPT-4
   - Context-aware responses with conversation history
   - Specialized system prompt for Toastmasters knowledge

4. **Health Monitoring**
   - `/` - Health check endpoint
   - `/wake` - Bot revival endpoint
   - `/stats` - Performance metrics

### API Endpoints

- `GET /` - Health check and bot status
- `GET /wake` - Wake up sleeping bot and restart if needed
- `GET /stats` - Bot statistics and performance metrics

## 🚀 Deployment

### Render.com Deployment

This bot is optimized for Render.com deployment:

1. **Web Service Configuration**:
   - Build Command: `npm install`
   - Start Command: `npm start`
   - Environment: Node.js

2. **Environment Variables**: Add all required variables in Render dashboard

3. **Keep-Alive System**: Automatic ping every 14 minutes to prevent sleeping

### Manual Deployment

```bash
# Build for production
npm install --production

# Start the application
npm start
```

## 🛠️ Configuration

### Memory Management

```javascript
const MEMORY_LIMIT = 10 // Number of message pairs to remember
```

### Google Sheets Setup

1. Create a Google Service Account
2. Enable Google Sheets API
3. Create a spreadsheet with "Users" sheet
4. Add columns: username, text, date, first_name, last_name
5. Share spreadsheet with service account email

### Bot Customization

The bot behavior can be customized by modifying the `systemPrompt` variable in the code. Key customization areas:

- Response style and tone
- Additional knowledge areas
- Club-specific information
- Language preferences

## 📊 Features Overview

### Conversation Flow
1. User sends message to bot
2. Bot retrieves conversation history
3. AI generates contextual response
4. Interaction logged to Google Sheets
5. Response sent to user with markdown formatting

### Error Handling
- Automatic bot restart on failures
- Graceful error messages to users
- Comprehensive logging for debugging
- Webhook cleanup and polling management

### Performance Monitoring
- Real-time bot status tracking
- Memory usage monitoring
- User interaction statistics
- Uptime tracking

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📞 Support

For Chamber Toastmasters Club inquiries:
- **Website**: https://www.chambertoastmasters.club/
- **Email**: chamber.vp.edu@gmail.com
- **Phone**: +380672206710
- **Telegram Group**: https://t.me/ChamberToastmastersKyivEnglish

## 🔗 Related Resources

- [Toastmasters International](https://www.toastmasters.org/)
- [OpenRouter API Documentation](https://openrouter.ai/docs)
- [Google Sheets API Guide](https://developers.google.com/sheets/api)
- [Telegram Bot API](https://core.telegram.org/bots/api)

---

**Note**: This bot is designed specifically for the Chamber Toastmasters Club in Kyiv, Ukraine, and contains club-specific information and rules. For general Toastmasters bot implementation, review and modify the system prompt accordingly.
