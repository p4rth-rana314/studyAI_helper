# AI Study Helper 🎓

A comprehensive AI-powered study assistant built with Streamlit that helps students learn more effectively through various interactive tools and features.

## Features ✨

### 📚 Document Processing
- **PDF Reader**: Extract and analyze text from PDF documents
- **Word Document Support**: Process DOCX files for study material
- **Text Summarization**: Get concise summaries of long documents
- **Key Point Extraction**: Identify important concepts and ideas

### 🎥 Video Learning
- **YouTube Transcript Extraction**: Get transcripts from educational videos
- **Video Summary**: Summarize video content for quick review
- **Study Notes Generation**: Convert video content into structured notes

### 🔊 Audio Features
- **Text-to-Speech**: Convert study materials to audio for auditory learning
- **Multiple Language Support**: Generate speech in different languages
- **Audio Notes**: Create audio summaries of your study materials

### 🌐 Web Research
- **Web Content Scraping**: Extract information from educational websites
- **Wikipedia Integration**: Quick access to encyclopedia entries
- **URL Validation**: Ensure reliable source verification

### 🤖 AI-Powered Tools
- **Study Plan Generator**: Create personalized study schedules
- **Quiz Generator**: Generate practice questions from study materials
- **Concept Explanation**: Get detailed explanations of complex topics
- **Study Tips**: Receive personalized learning recommendations

### 📊 Study Analytics
- **Progress Tracking**: Monitor your learning progress
- **Time Management**: Track study sessions and productivity
- **Performance Insights**: Analyze your strengths and areas for improvement

## Installation 🚀

### Local Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ai-study-helper.git
   cd ai-study-helper
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application**
   ```bash
   streamlit run ai_study_helper.py
   ```

### Google Colab Installation

1. **Install required packages**
   ```python
   !pip install streamlit youtube-transcript-api gtts pydub python-multipart validators wikipedia anthropic openai requests beautifulsoup4 PyPDF2 python-docx pyngrok -q
   ```

2. **Create application files**
   ```python
   # Copy the provided setup code for Colab
   # See detailed instructions in the Colab Setup section below
   ```

3. **Launch the app**
   ```python
   # Use ngrok tunnel to access the app publicly
   # Follow the Colab setup instructions
   ```

## Dependencies 📦

```
streamlit >= 1.28.0
youtube-transcript-api >= 0.6.0
gtts >= 2.3.0
pydub >= 0.25.0
python-multipart >= 0.0.6
validators >= 0.22.0
wikipedia >= 1.4.0
requests >= 2.31.0
beautifulsoup4 >= 4.12.0
PyPDF2 >= 3.0.0
python-docx >= 0.8.11
pyngrok >= 7.0.0 (for Colab)
```

## Google Colab Setup 🔧

### Quick Setup Script
```python
# 1. Install all dependencies
!pip install streamlit youtube-transcript-api gtts pydub python-multipart validators wikipedia anthropic openai requests beautifulsoup4 PyPDF2 python-docx pyngrok -q

# 2. Create Streamlit config for Colab
!mkdir -p .streamlit
with open('.streamlit/config.toml', 'w') as f:
    f.write('''[server]
headless = true
enableCORS = false
enableXsrfProtection = false
port = 8501
[browser]
gatherUsageStats = false''')

# 3. Create your app files (copy your code here)
app_code = '''
# Your complete Streamlit app code
'''
with open('ai_study_helper.py', 'w') as f:
    f.write(app_code)

helper_code = '''
# Your helper functions code
'''
with open('helper_functions.py', 'w') as f:
    f.write(helper_code)

# 4. Launch the application
import threading
import time
from pyngrok import ngrok

def run_streamlit():
    !streamlit run ai_study_helper.py --server.port 8501

thread = threading.Thread(target=run_streamlit)
thread.daemon = True
thread.start()

time.sleep(10)
public_url = ngrok.connect(8501)
print(f"🚀 Your app is running at: {public_url}")
```

## Usage Guide 📖

### Getting Started
1. **Launch the application** using one of the installation methods above
2. **Choose a study tool** from the sidebar menu
3. **Upload your study materials** (PDFs, documents, or paste text)
4. **Select the desired feature** (summarize, generate quiz, etc.)
5. **Review and download** your processed study materials

### Main Features Overview

#### Document Analysis
- Upload PDF or DOCX files
- Get instant summaries and key points
- Generate study notes and outlines

#### Video Learning
- Paste YouTube URLs to extract transcripts
- Convert video content to text notes
- Generate quizzes from video content

#### Audio Study
- Convert any text to speech
- Support for multiple languages
- Download audio files for offline study

#### Web Research
- Extract content from educational websites
- Quick Wikipedia lookups
- Validate and process web sources

## File Structure 📁

```
ai-study-helper/
├── ai_study_helper.py          # Main Streamlit application
├── helper_functions.py         # Utility functions
├── requirements.txt            # Python dependencies
├── README.md                   # Project documentation
├── .streamlit/
│   └── config.toml            # Streamlit configuration
└── assets/                    # Static assets (if any)
```

## Configuration ⚙️

### API Keys (Optional)
If using AI features that require API access:

```python
# Set environment variables
import os
os.environ["OPENAI_API_KEY"] = "your-api-key"
os.environ["ANTHROPIC_API_KEY"] = "your-api-key"
```

### Streamlit Configuration
The app includes optimized settings for both local and Colab environments.

## Troubleshooting 🛠️

### Common Issues

**1. Import Errors**
```bash
# Reinstall dependencies
pip install --upgrade -r requirements.txt
```

**2. Streamlit Won't Start**
```bash
# Kill existing processes
pkill -f streamlit
# Restart the application
streamlit run ai_study_helper.py
```

**3. Colab Connection Issues**
```python
# Reset ngrok connection
ngrok.disconnect_all()
# Restart the tunnel
public_url = ngrok.connect(8501)
```

**4. File Upload Problems**
- Ensure file formats are supported (PDF, DOCX, TXT)
- Check file size limits
- Verify file permissions

### Performance Tips
- Use smaller files for faster processing
- Close unused browser tabs
- Restart the app if memory usage is high

## Contributing 🤝

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/new-feature
   ```
3. **Make your changes**
4. **Test thoroughly**
5. **Submit a pull request**

### Development Guidelines
- Follow PEP 8 style guidelines
- Add docstrings to all functions
- Include error handling
- Test with various file formats
- Update README for new features

## License 📄

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments 🙏

- **Streamlit** - For the amazing web app framework
- **Google Colab** - For providing free computational resources
- **OpenAI/Anthropic** - For AI capabilities
- **YouTube Transcript API** - For video transcript extraction
- **gTTS** - For text-to-speech functionality

## Support 💬

If you encounter any issues or have questions:

1. **Check the troubleshooting section** above
2. **Search existing issues** on GitHub
3. **Create a new issue** with detailed information
4. **Join our community discussions**

## Roadmap 🗺️

- [ ] Advanced AI integration
- [ ] Mobile app version
- [ ] Collaborative study features
- [ ] Integration with learning management systems
- [ ] Advanced analytics and insights
- [ ] Multi-language interface support

## Version History 📝

- **v1.0.0** - Initial release with core features
- **v1.1.0** - Added video transcript support
- **v1.2.0** - Enhanced audio features
- **v1.3.0** - Web scraping capabilities
- **v2.0.0** - Google Colab optimization

---

**Made with ❤️ for students everywhere**

*Happy studying! 🎓*
