# Rugby AI (ラグビーAI)

A specialized chat AI application that provides expert knowledge about Rugby rules and gameplay. Built with Node.js, Express, and OpenAI's GPT-4o-mini model, this application offers an interactive Japanese interface for asking and receiving detailed answers about Rugby.

## Features

- 🤖 **AI-Powered Rugby Knowledge**: Specialized AI trained on comprehensive Rugby rules and regulations
- 💬 **Interactive Chat Interface**: Clean, user-friendly chat interface with typing animation
- 📚 **Knowledge Base**: Uses a detailed knowledge base (`knowledge.txt`) covering Rugby rules, penalties, gameplay, and more
- 🔄 **Conversation Management**: Maintains conversation history and includes a reset functionality
- ⚡ **Real-time Responses**: Fast AI responses with smooth typing animations

## Tech Stack

- **Backend**: Node.js, Express.js
- **Frontend**: HTML5, CSS3 (SASS), Vanilla JavaScript
- **AI**: OpenAI API (GPT-4o-mini)
- **Dependencies**:
  - `express`: Web server framework
  - `openai`: OpenAI API client
  - `cors`: Cross-origin resource sharing
  - `dotenv`: Environment variable management

## Project Structure

```
RUGBY-EXPRESS/
├── assets/                 # Favicons and icons
│   ├── favicon.ico
│   ├── favicon-16x16.png
│   ├── favicon-32x32.png
│   ├── apple-touch-icon.png
│   ├── android-chrome-192x192.png
│   └── android-chrome-512x512.png
├── css/                    # Compiled CSS styles
│   └── style.css
├── sass/                   # SASS source files
│   └── style.scss
├── index.html              # Main HTML file (Japanese interface)
├── script.js               # Frontend JavaScript (chat functionality)
├── server.js               # Express server with OpenAI integration
├── knowledge.txt           # Rugby knowledge base for AI
├── package.json            # Node.js dependencies and scripts
├── .gitignore              # Git ignore rules
└── README.md               # This file
```

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd RUGBY-EXPRESS
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   
   Create a `.env` file in the root directory:
   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   PORT=10000
   ```

   > **Note**: You'll need an OpenAI API key. Sign up at [OpenAI](https://platform.openai.com/) to get your API key.

## Usage

1. **Start the server**
   ```bash
   npm start
   ```

2. **Access the application**
   
   Open your browser and navigate to:
   ```
   http://localhost:10000
   ```

3. **Ask questions**
   
   Type your Rugby-related questions in Japanese in the input box and click "送信" (Send) or press Enter.

## API Endpoints

### `GET /`
Serves the main HTML page.

### `POST /ask`
Sends a question to the AI and receives an answer.

**Request Body:**
```json
{
  "question": "ラグビーのルールについて教えてください"
}
```

**Response:**
```json
{
  "answer": "ラグビーは15人制が基本で..."
}
```

### `POST /reset`
Resets the conversation history.

**Response:**
```json
{
  "message": "会話履歴をリセットしました。"
}
```

## Configuration

The AI is configured to:
- Provide answers in approximately 300 characters (or 500+ when detailed explanation is requested)
- Use the knowledge base in `knowledge.txt` as the source of truth
- Format responses with proper line breaks (30 characters per line)
- Include rule references for technical questions

## Development

### Scripts

- `npm start`: Starts the Express server
- `npm test`: Placeholder for test scripts

### Key Files

- **`server.js`**: Main server file handling API routes and OpenAI integration
- **`script.js`**: Frontend JavaScript managing chat UI and API calls
- **`knowledge.txt`**: Comprehensive Rugby knowledge base used to train the AI responses
- **`index.html`**: Main HTML structure with Japanese interface

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `OPENAI_API_KEY` | Your OpenAI API key | Yes |
| `PORT` | Server port number (default: 10000) | No |

---

**Note**: This application is designed for Japanese users and provides Rugby knowledge in Japanese. The AI responses are based on the comprehensive knowledge base in `knowledge.txt`, which includes Rugby rules, penalties, gameplay mechanics, and terminology updates (e.g., "ノックオン" → "ノックフォワード" as of April 1, 2025).
