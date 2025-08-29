# Dilbert Comics Transcription Project

[![GitHub](https://img.shields.io/github/license/yayiji/Dilbert-Transcripts)](LICENSE)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-green)](https://nodejs.org/)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](CONTRIBUTING.md)

**A collaborative project to create accurate, searchable transcripts of Dilbert comic strips with complete character attribution and dialogue.**

## 🎯 Project Mission

**The primary goal of this project is to create the most accurate and complete transcription dataset of Dilbert comics through community collaboration.** While we use AI to generate initial transcripts, **the real value comes from human contributors who review, correct, and enhance these transcripts to achieve perfect accuracy.**

### Why This Matters
- 🔍 **Searchability**: Make decades of Dilbert wisdom easily searchable
- ♿ **Accessibility**: Provide text versions for screen readers and accessibility tools  
- 📊 **Analysis**: Enable research into themes, character development, and corporate satire
- 🏛️ **Preservation**: Create a permanent, structured archive of comic dialogue
- 👥 **Character Attribution**: Know exactly who said what in each strip

## 🚀 How You Can Help

**We need your help to make these transcripts perfect!** Here's how the project works:

### 1. 🤖 AI Provides the Starting Point
- Initial transcripts are generated using AI (Gemini models)
- These serve as a foundation but contain errors and missing information

### 2. 👥 Community Makes It Perfect
- **Review transcripts** against original comics
- **Add character names** to dialogue  
- **Fix transcription errors** and missing text
- **Include visual elements** like signs, charts, etc.

### 3. 📈 Continuous Improvement
- Each contribution makes the dataset more valuable
- Quality improvements benefit everyone using the data

## 📖 Overview

This is a **community-driven project** to create perfect transcripts of Dilbert comics from 1989 to 2023. 

**Current Status**: We have AI-generated initial transcripts for all comics, but **we need human contributors to review and perfect them**.

### What Makes a Perfect Transcript?
- ✅ **100% Accurate Dialogue**: Every word correctly transcribed
- 👤 **Character Attribution**: Each line tagged with the speaker
- 📝 **Complete Text**: All readable text including signs, labels, charts
- 🎭 **Context**: Visual elements and situational details when relevant

### The Process
1. **AI Foundation**: AI generates initial transcripts (DONE ✅)
2. **Community Review**: Contributors improve accuracy and add character info (IN PROGRESS 🔄)
3. **Quality Validation**: Peer review ensures accuracy (PLANNED 📋)
4. **Perfect Dataset**: Comprehensive, searchable comic archive (GOAL 🎯)

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

## 🎯 Quick Start: Improving Transcripts

**Ready to contribute? Here's how to start improving transcripts right away:**

### Option 1: Quick Fix (No Setup Required)
1. **Browse the repository** online at [github.com/yayiji/Dilbert-Transcripts](https://github.com/yayiji/Dilbert-Transcripts)
2. **Find a comic** in `dilbert-transcripts/YYYY/YYYY-MM-DD.json`
3. **Click "Edit"** and compare with the source comic in `dilbert-comics/YYYY/YYYY-MM-DD.gif`
4. **Fix errors** and add character names
5. **Submit a Pull Request** with your improvements

### Option 2: Local Development
1. **Fork and clone** the repository
2. **Choose a comic date** to work on
3. **Compare** the JSON transcript with the GIF comic
4. **Edit the JSON** to add missing dialogue, fix errors, add character names
5. **Submit your improvements** via Pull Request

### What to Look For
- ❌ **Transcription errors**: Words that don't match the comic
- ❓ **Missing dialogue**: Text the AI didn't detect
- 👤 **Anonymous speakers**: Add character names to dialogue
- 📝 **Missing text**: Signs, labels, computer screens, etc.

## 🛠️ Technical Setup (For AI Transcription)

*Note: Most contributors won't need this - it's only for generating new AI transcripts*

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

## 📄 Transcript Format

### Current AI-Generated Format
```json
{
  "date": "2023-01-01",
  "panels": [
    {
      "panel": 1,
      "dialogue": [
        "I created an advisory council of people who have wildly divergent views."
      ]
    }
  ]
}
```

### Target Perfect Format (What We're Working Toward)
```json
{
  "date": "2023-01-01",
  "panels": [
    {
      "panel": 1,
      "dialogue": [
        {
          "speaker": "Pointy-Haired Boss",
          "text": "I created an advisory council of people who have wildly divergent views."
        }
      ],
      "visual_elements": ["Whiteboard with organizational chart"]
    }
  ],
  "characters": ["Pointy-Haired Boss", "Dilbert"],
  "setting": "Conference room",
  "quality_status": "human_verified"
}
```

## 🎯 Contributing: Making Transcripts Perfect

**This is the heart of the project!** Every contribution makes the dataset more valuable.

### Step-by-Step Improvement Guide

#### 1. Choose a Comic to Improve
```bash
# Find comics that need work
ls dilbert-transcripts/1989/  # Start with early comics
ls dilbert-transcripts/2023/  # Or recent ones
```

#### 2. Compare Original vs Transcript
- **Open the comic**: `dilbert-comics/1989/1989-04-16.gif`
- **Open the transcript**: `dilbert-transcripts/1989/1989-04-16.json`
- **Look for differences**: Missing text, wrong words, unclear speakers

#### 3. Make Improvements
```json
// Before (AI-generated)
{
  "panel": 1,
  "dialogue": ["Im the new guy"]
}

// After (Your improvement)
{
  "panel": 1,
  "dialogue": [
    {
      "speaker": "Dilbert",
      "text": "I'm the new guy."
    }
  ]
}
```

#### 4. Quality Checklist
- ✅ All dialogue accurately transcribed
- ✅ Character names identified where possible
- ✅ Punctuation and capitalization corrected
- ✅ Sound effects included if relevant
- ✅ Visual text (signs, computer screens) captured

#### 5. Submit Your Improvement
- **Create Pull Request** with clear description
- **Reference the comic date** in your commit message
- **Explain what you fixed** or improved

### Common Character Names
- **Dilbert** - The main character, engineer
- **Pointy-Haired Boss (PHB)** - Dilbert's clueless manager
- **Alice** - Aggressive engineer
- **Wally** - Lazy engineer
- **Asok** - Intern
- **Dogbert** - Dilbert's cynical dog
- **Carol** - Secretary
- **Catbert** - Evil HR cat

### Improvement Priorities

| Priority | Focus Area | Impact |
|----------|------------|---------|
| 🔥 **High** | Character attribution for main characters | Makes comics searchable by speaker |
| 🔥 **High** | Fix obvious transcription errors | Improves basic accuracy |
| 📖 **Medium** | Add missing dialogue | Completeness |
| 📝 **Medium** | Include visual text (signs, screens) | Context and completeness |
| 🎨 **Low** | Visual element descriptions | Enhanced metadata |

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

## 📊 Project Status & Progress

### Current Dataset
- **Total Comics**: ~12,000+ strips (1989-2023)
- **AI Transcripts**: ✅ Complete (all comics have initial transcripts)
- **Human Verified**: 🔄 **0%** - This is where YOU come in!
- **Character Attribution**: 🔄 **0%** - Major improvement opportunity

### Quality Improvement Status

| Year Range | Comics | AI Complete | Human Review | Character Tags | Priority |
|------------|--------|-------------|--------------|----------------|----------|
| 1989-1995  | ~2,000 | ✅ Done | ❌ **Needed** | ❌ **Needed** | 🔥 **High** |
| 1996-2005  | ~3,500 | ✅ Done | ❌ **Needed** | ❌ **Needed** | 📖 Medium |
| 2006-2015  | ~3,500 | ✅ Done | ❌ **Needed** | ❌ **Needed** | 📖 Medium |
| 2016-2023  | ~3,000 | ✅ Done | ❌ **Needed** | ❌ **Needed** | 📝 Low |

### Impact of Your Contributions

Every transcript you improve helps:
- 🔍 **Researchers** studying workplace culture and corporate satire
- ♿ **Accessibility** users who rely on screen readers
- 📱 **App developers** building Dilbert search and analysis tools
- 🎓 **Students** analyzing comic evolution and character development
- 👥 **Fans** searching for specific quotes or storylines

### Community Goals

- **Phase 1** (Current): Get 100 human-verified transcripts
- **Phase 2**: Add character attribution to most popular comics
- **Phase 3**: Complete character tagging for all main characters
- **Phase 4**: Full metadata with visual elements and themes

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

## 📈 Roadmap: Building the Perfect Dataset

### 🎯 Immediate Priorities (Help Needed!)
- [ ] **First 100 Verified Transcripts**: Establish quality baseline
- [ ] **Character Attribution Guide**: Document how to identify speakers
- [ ] **Quality Metrics**: Track improvement progress
- [ ] **Contributor Recognition**: Acknowledge community efforts

### 🔄 Ongoing Improvement Goals
- [ ] **Main Character Attribution**: Dilbert, PHB, Alice, Wally, Asok, Dogbert
- [ ] **Historical Comics**: Focus on early strips (1989-1995)
- [ ] **Popular Storylines**: Office politics, technology satire, management humor
- [ ] **Visual Elements**: Include signs, charts, computer screens

### 🚀 Future Enhancements
- [ ] **Search Interface**: Web-based transcript search
- [ ] **API Access**: Programmatic access to transcript data
- [ ] **Analysis Tools**: Character frequency, theme analysis
- [ ] **Mobile App**: Browse comics with enhanced accessibility

### 🛠️ Technical Infrastructure
- [ ] **Validation Tools**: Automated transcript quality checking
- [ ] **Batch Processing**: Tools for mass improvements
- [ ] **Contributor Dashboard**: Track progress and contributions
- [ ] **Integration Tests**: Ensure data consistency

**🎯 Success Metric**: Create the most accurate and complete Dilbert transcript dataset in existence, with every comic properly attributed and verified by the community.

## 🤝 Join the Community Effort

**This project succeeds through community collaboration!** Every contribution, no matter how small, makes the dataset better for everyone.

### Ways to Contribute

1. **🎯 Primary Goal: Improve Transcripts**
   - Fix dialogue transcription errors
   - Add character names to dialogue
   - Include missing text (signs, labels, etc.)
   - Verify accuracy against original comics

2. **📝 Documentation & Guides**
   - Improve this README
   - Create character identification guides
   - Write tutorials for new contributors

3. **💻 Technical Improvements**
   - Enhance AI transcription scripts
   - Build validation tools
   - Create quality checking utilities

### Getting Started (Choose Your Path)

#### 🚀 **Quick Contributor** (5 minutes)
1. Browse transcripts online
2. Find obvious errors
3. Submit quick fixes via GitHub web interface

#### 👨‍💻 **Regular Contributor** (Setup once, contribute often)
1. Fork and clone repository
2. Set up local development environment
3. Batch process multiple improvements

#### 🏆 **Power Contributor** (Lead improvement efforts)
1. Adopt specific year ranges
2. Develop systematic improvement workflows
3. Help review other contributors' work

### Pull Request Guidelines

**For Transcript Improvements:**
- Title: `Fix transcripts for [date range or specific comic]`
- Description: Brief summary of what you improved
- Reference: Mention you verified against original comics

**Example PR Description:**
```
Fixed transcription errors in 1989-04-16 to 1989-04-20:
- Added character names (Dilbert, PHB)
- Corrected 3 dialogue transcription errors
- Added missing text from computer screen in 1989-04-18
- Verified all changes against original GIF files
```

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
