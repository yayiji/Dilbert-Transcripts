# Transcription of Dilbert comics.

[![GitHub](https://img.shields.io/github/license/yayiji/Dilbert-Transcripts)](LICENSE)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-green)](https://nodejs.org/)

An automated transcription system for Dilbert comic strips using AI-powered text recognition. This project transcribes comic dialogue into structured JSON format for analysis, searchability, and preservation.

## 📖 Overview

This project automatically transcribes Dilbert comics from 1989 to 2023 using two different AI providers:
- **OpenRouter API** (Gemini 2.5 Flash Lite via proxy)
- **Official Google Gemini API** (Direct access)

The transcripts are generated in a structured JSON format with dialogue organized by comic panels, making the content searchable and accessible.

## 🏗️ Project Structure

```
VS-Dilbert-Transcripts/
├── dilbert-comics/          # Source comic images
│   ├── 1989/
│   │   ├── 1989-04-16.gif
│   │   └── ...
│   ├── 1990/
│   └── .../
├── dilbert-transcripts/     # Generated transcripts
│   ├── 1989/
│   │   ├── 1989-04-16.json
│   │   └── ...
│   ├── 2023/
│   └── .../
├── transcribe-comics.js     # OpenRouter API transcription script
├── transcribe-comics-gemini.js  # Google Gemini API transcription script
├── package.json
└── README.md
```

## 🚀 Quick Start

### Prerequisites

- Node.js 18 or higher
- API key from either:
  - [OpenRouter](https://openrouter.ai/keys) (for OpenRouter script)
  - [Google AI Studio](https://ai.google.dev/) (for Gemini script)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yayiji/Dilbert-Transcripts.git
cd Dilbert-Transcripts
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
# Create .env file
touch .env

# Add your API key(s)
echo "OPENROUTER_API_KEY=your_openrouter_key_here" >> .env
echo "GEMINI_API_KEY=your_gemini_key_here" >> .env
```

### Usage

#### OpenRouter API (Recommended)
```bash
# Transcribe a single year
npm run transcribe 1989

# Transcribe a range of years
npm run transcribe 1989 1995

# Or run directly
node transcribe-comics.js 1989
```

#### Google Gemini API
```bash
# Transcribe a single year
npm run transcribe-gemini 1989

# Transcribe a range of years
npm run transcribe-gemini 1989 1995

# Or run directly
node transcribe-comics-gemini.js 1989
```

## 📄 Output Format

Each comic is transcribed into a JSON file with the following structure:

```json
{
  "date": "2023-01-01",
  "panels": [
    {
      "panel": 1,
      "dialogue": [
        "I created an advisory council of people who have wildly divergent views."
      ]
    },
    {
      "panel": 2,
      "dialogue": [
        "Has an advisory council of people with wildly divergent views ever accomplished anything?"
      ]
    },
    {
      "panel": 3,
      "dialogue": [
        "I asked them the same thing.",
        "Opinions were mixed."
      ]
    }
  ]
}
```

## ⚙️ Features

### Common Features
- ✅ **Smart Skip Logic**: Automatically skips existing transcripts
- ✅ **Rate Limiting**: Respects API quotas with configurable delays
- ✅ **Error Handling**: Comprehensive retry logic with exponential backoff
- ✅ **Progress Tracking**: Real-time progress indicators
- ✅ **Multi-year Processing**: Batch process multiple years efficiently
- ✅ **Structured Output**: Clean JSON format for easy data manipulation

### OpenRouter Script Specific
- Uses Gemini 2.5 Flash Lite via OpenRouter proxy
- Simpler authentication flow
- Cost-effective pricing

### Google Gemini Script Specific
- Direct access to Google's official Gemini API
- Enhanced error handling with detailed API responses
- Schema validation for consistent output

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required For |
|----------|-------------|--------------|
| `OPENROUTER_API_KEY` | OpenRouter API key | OpenRouter script |
| `GEMINI_API_KEY` | Google Gemini API key | Gemini script |

### Script Configuration

You can modify these constants in the transcription scripts:

```javascript
const RATE_LIMIT_DELAY = 2000; // Delay between requests (ms)
const MAX_RETRIES = 3;         // Maximum retry attempts
const YEAR_DELAY = 5000;       // Delay between years (ms)
```

## 📊 Data Coverage

The project includes comics from:
- **Start Date**: April 16, 1989 (first Dilbert comic)
- **End Date**: December 31, 2023
- **Total Years**: 35 years
- **Estimated Comics**: ~12,000+ strips

### Available Years
1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023

## 🛠️ Troubleshooting

### Common Issues

1. **API Key Errors**
   ```
   ❌ Please set OPENROUTER_API_KEY environment variable
   ```
   - Solution: Ensure your `.env` file contains valid API keys

2. **Rate Limiting**
   ```
   ⏳ Rate limited, waiting 30 seconds...
   ```
   - Solution: The script automatically handles this, just wait

3. **Missing Comic Files**
   ```
   ⚠️ Missing comic file: 1989-04-16.gif
   ```
   - Solution: Ensure comic images are in the correct directory structure

4. **Permission Errors**
   ```
   Error: EACCES: permission denied
   ```
   - Solution: Check file permissions or run with appropriate privileges

### Performance Tips

- Use the OpenRouter script for cost-effective processing
- Process years individually for better control
- Monitor your API usage to avoid unexpected charges
- Consider running during off-peak hours for better rate limits

## 📈 Roadmap

- [ ] Add support for additional comic formats
- [ ] Implement OCR confidence scoring
- [ ] Add bulk analysis tools
- [ ] Create web interface for browsing transcripts
- [ ] Add character recognition and tagging
- [ ] Implement search functionality
- [ ] Export to different formats (CSV, XML, etc.)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

### Development Setup

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📜 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

This project is for educational and research purposes. The Dilbert comic strip is copyrighted material owned by Scott Adams and Andrews McMeel Syndication. This transcription project is intended to make the content more accessible and searchable, similar to how subtitles make video content accessible.

## 🙏 Acknowledgments

- Scott Adams for creating the Dilbert comic strip
- Google for providing the Gemini AI API
- OpenRouter for AI API access
- The open-source community for Node.js and related packages

---

**Happy Transcribing!** 🎨✨
