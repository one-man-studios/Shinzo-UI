# Shinzo-UI
A robust, single standalone html file AI interface for Ollama and OpenAI. Features local RAG with vector search, real-time voice/video calls, document analysis (PDF/DOCX), and project workspaces. Runs entirely in the browser using IndexedDB for privacy and speed—no external backend required.

## ✨ Key Features

### 🎯 Core Functionality
- **Chat Interface**: Conversational UI with markdown rendering, code syntax highlighting, and LaTeX support
- **Knowledge Base**: Document upload & vector storage (PDF, DOCX, TXT, etc.)
- **Workspace Management**: Containerized project spaces with custom instructions
- **Model Builder**: Create custom models using Modelfile syntax
- **Live Web Search**: Real-time internet search integration

### 🎨 User Experience
- Dark mode UI with modern design
- Responsive layout (mobile & desktop)
- Voice/Video call capabilities
- Real-time speech recognition (STT) and synthesis (TTS)
- Concurrent model conversations
- Citation and source tracking

### 🛠️ Technical Features
- **Browser-based Vector Database**: IndexedDB storage for documents and conversations
- **Multiple Embedding Providers**: Ollama, Local (Transformers.js), OpenAI
- **File Processing**: PDF, DOCX, images, audio, and text files
- **Export/Import**: Chat history backup and restore
- **Real-time Search**: Live search across chats and knowledge base

## 🚀 Quick Start

### Prerequisites
- Modern web browser (Chrome/Firefox/Edge)
- Ollama server (optional, for local AI models)
- Internet connection (for CDN dependencies)

### Installation
1. Download the `Shinzo UI.html` file
2. Open it directly in your browser
3. Configure your API settings (Settings tab)

### Basic Configuration
1. Set your API URL (default: `http://localhost:11434` for Ollama)
2. Configure embedding provider (Ollama recommended for local use)
3. Set up web search API key (optional, for live search)

## 📁 File Structure

The application is a single HTML file containing:
- **HTML5**: Structure and layout
- **CSS3**: Styling with CSS variables for theming
- **JavaScript**: Complete application logic
- **Embedded Libraries**:
  - Font Awesome (icons)
  - KaTeX (mathematical rendering)
  - Marked.js (markdown parsing)
  - DOMPurify (HTML sanitization)
  - PDF.js (PDF processing)
  - jsPDF (PDF generation)
  - Mammoth (DOCX processing)

## 🎮 Usage Guide

### Starting a Chat
1. Click "New Chat" in the sidebar
2. Select your primary model from the dropdown
3. Type your message or use voice input
4. Toggle web search for real-time information

### Managing Knowledge Base
1. Navigate to "Knowledge" tab
2. Upload documents using the upload button
3. Documents are automatically chunked and embedded
4. Use `#` symbol in chats to trigger RAG context

### Creating Workspaces
1. Go to "Spaces" tab
2. Click "Create Space"
3. Add custom instructions and files
4. Start space-specific chats

### Voice/Video Calls
1. Click phone or video icon in chat header
2. Grant microphone/camera permissions
3. Speak naturally - VAD (Voice Activity Detection) automatically detects speech
4. Toggle mute/video during calls

## ⚙️ Configuration Options

### API Settings
- **API URL**: Backend server address (Ollama, OpenAI, etc.)
- **API Key**: Authentication token
- **Embedding Provider**: Ollama, Local browser, or OpenAI
- **Chunk Size**: Document processing size (default: 1000)
- **Top K Results**: RAG retrieval count (default: 3)

### Web Search
- **Serper API Key**: For enhanced search results
- **Proxy Mode**: CORS or custom proxy for web scraping

### Voice Settings
- **STT Endpoint**: Speech-to-text API endpoint
- **TTS Endpoint**: Text-to-speech API endpoint
- **VAD Enabled**: Voice activity detection
- **Playback Speed**: Audio playback rate

## 🔧 Advanced Features

### Model Builder
Create custom AI models using Modelfile syntax:
1. Navigate to "Model Builder" tab
2. Select base model
3. Define system prompt and parameters
4. Click "Create Model"

### Concurrent Conversations
- Toggle concurrent mode to use two models simultaneously
- Each model responds independently for comparison

### Export/Import
- Export chat history as JSON
- Import previous conversations
- Archive chats for organization

## 🗂️ Data Storage

### IndexedDB Structure

```
superRAG_DB (v5)
├── documents (metadata)
├── chunks (vector embeddings)
├── conversations (chat history)
└── spaces (workspace configurations)
```

### Local Storage
- Application settings
- UI preferences
- Connection configurations

## 🔐 Security Notes

### Data Privacy
- All data stored locally in browser
- No external data transmission unless configured
- API keys stored in browser local storage

### File Processing
- Documents processed client-side
- Images converted to base64 for attachments
- TXT/PDF/DOCX parsing happens in browser

## 🌐 CDN Dependencies

The application loads these libraries from CDN:
- **Font Awesome 6.5.1** (icons)
- **KaTeX 0.16.9** (math rendering)
- **Marked.js** (markdown)
- **DOMPurify 3.0.6** (security)
- **PDF.js 3.11.174** (PDF processing)
- **jsPDF 2.5.1** (PDF generation)
- **Mammoth 1.6.0** (DOCX processing)
- **Transformers.js** (for local embeddings)

## 🐛 Troubleshooting

### Common Issues

1. **Connection Failed**
   - Verify Ollama server is running
   - Check API URL in settings
   - Disable browser CORS restrictions if needed

2. **File Upload Issues**
   - Check file size limits
   - Ensure supported file types
   - Try smaller chunks in settings

3. **Voice Features Not Working**
   - Grant microphone permissions
   - Check STT/TTS endpoint configuration
   - Verify browser supports WebRTC

### Browser Compatibility
- Chrome 90+ (recommended)
- Firefox 88+
- Edge 90+
- Safari 14.1+

## 📝 Development

### Customization
- Modify CSS variables in `:root` for theming
- Extend VectorDB class for different storage backends
- Add new file processors in `extractTextFromFile()`

### Adding Features
1. New view sections can be added to HTML
2. Extend `app` object with new methods
3. Update sidebar navigation accordingly

## 📄 License

Created by [One Man Studios](https://github.com/one-man-studios)

This project is provided as-is for educational and personal use. Commercial use is strictly prohibited.

## 🤝 Contributing

Feel free to:
1. Fork the repository
2. Give a star rating 🌟
3. Submit pull requests

**Note**: This is a client-side application. All processing happens in your browser. No data is sent to external servers unless explicitly configured in settings.
