# Job Fit Analyzer 🎯

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Google Colab](https://img.shields.io/badge/Platform-Google%20Colab-orange.svg)](https://colab.research.google.com/)
[![Gemini API](https://img.shields.io/badge/AI-Google%20Gemini-4285F4.svg)](https://ai.google.dev/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> An AI-powered resume analysis tool that helps job seekers optimize their applications by comparing resumes against job descriptions and providing actionable recommendations.

![Job Fit Analyzer Demo](https://img.shields.io/badge/Status-Active-success)

---

## 📋 Table of Contents

- [Problem Statement](#-problem-statement)
- [Solution](#-solution)
- [Features](#-features)
- [Technical Architecture](#-technical-architecture)
- [Technology Stack](#-technology-stack)
- [Quick Start Guide](#-quick-start-guide)
- [Usage Examples](#-usage-examples)
- [Output Samples](#-output-samples)
- [Testing](#-testing-checklist)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [Support](#-support)
- [License](#-license)

---

## 🎯 Problem Statement

Job seekers and students face significant challenges when applying for positions: 

- ⏰ **Time-Consuming**: Manually comparing resumes against multiple job descriptions
- 🤖 **ATS Barriers**: Missing critical keywords that Applicant Tracking Systems filter for
- 🔍 **Skill Gaps**: Difficulty identifying which skills to highlight or acquire
- 💰 **Cost**: Professional resume reviews are expensive
- 📊 **No Metrics**:  Lack of quantifiable compatibility scores

**The Gap**: There's a need for an accessible, instant, AI-powered tool that provides specific, actionable recommendations for each job application.

---

## 💡 Solution

**Job Fit Analyzer** is an intelligent AI agent that bridges the gap between your resume and dream job by:

1. **Analyzing** resume text against job description requirements
2. **Calculating** a precise compatibility match score (0-100%)
3. **Identifying** matching skills and missing requirements
4. **Suggesting** ATS-optimized keywords to improve visibility
5. **Generating** tailored cover letter introductions
6. **Preparing** likely interview questions based on job requirements

### Key Benefits

| Benefit | Description |
|---------|-------------|
| ⚡ **Instant Analysis** | Results in 15-30 seconds |
| 🎯 **Actionable Insights** | Specific recommendations, not generic advice |
| 💰 **Free to Use** | No cost alternative to career coaches |
| 📊 **Data-Driven** | Quantified match scores for decision-making |
| 🔄 **Unlimited Comparisons** | Analyze as many jobs as you need |
| 📝 **Comprehensive Reports** | Exportable analysis reports |

---

## ✨ Features

### Core Functionality

- **Resume-Job Matching**: Intelligent comparison algorithm powered by Google Gemini AI
- **Match Score Calculation**: Percentage-based compatibility scoring (0-100%)
- **Skills Analysis**: 
  - Matching skills between resume and job description
  - Missing critical skills identification
  - Skill gap recommendations
- **ATS Optimization**:  Keyword suggestions for Applicant Tracking Systems
- **Cover Letter Generator**: Personalized introduction paragraphs
- **Interview Prep**: AI-generated likely interview questions

### Additional Features

- **Demo Mode**: Quick demonstration with sample data
- **Interactive Mode**: Analyze your own resume and job descriptions
- **General Resume Review**: Get improvement suggestions for any resume
- **Report Export**: Save analysis results to text files
- **Error Handling**: Robust validation and error messages

---

## 🏗️ Technical Architecture

### System Design

```
┌─────────────────────────────────────────────────┐
│              USER INTERFACE                     │
│  (Google Colab - Input cells + Display)        │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│         INPUT PROCESSING LAYER                  │
│  • Clean resume text                            │
│  • Clean job description                        │
│  • Validate inputs                              │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│           AI ANALYSIS ENGINE                    │
│  (Google Gemini API)                            │
│                                                 │
│  Components:                                    │
│  1. Prompt Constructor                          │
│  2. LLM API Call Handler                        │
│  3. Response Parser                             │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│         OUTPUT FORMATTING LAYER                 │
│  • Format match score                           │
│  • Display matching skills                      │
│  • Show missing skills                          │
│  • Present recommendations                      │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│            USER OUTPUT                          │
│  (Formatted display with colors + sections)    │
└─────────────────────────────────────────────────┘
```

### Data Flow

1. **Input**: User provides resume and job description text
2. **Processing**: Text cleaning and validation
3. **AI Analysis**: Gemini API processes the comparison
4. **Parsing**: JSON response extraction and validation
5. **Output**:  Formatted results with color-coded sections

---

## 🛠️ Technology Stack

| Component | Technology | Version |
|-----------|-----------|---------|
| **Language** | Python | 3.10+ |
| **Platform** | Google Colab | Latest |
| **AI Model** | Google Gemini | 1.5 Flash |
| **Libraries** | `google-generativeai` | Latest |
| | `re` (text processing) | Built-in |
| | `json` (response parsing) | Built-in |

### Why These Technologies?

- **Google Colab**: No local setup required, free GPU/TPU access, easy sharing
- **Gemini 1.5 Flash**: Fast, accurate, cost-effective generative AI model
- **Python**: Simple, readable, extensive library support

---

## 🚀 Quick Start Guide

### Prerequisites

- Google account (for Colab access)
- Google Gemini API key (free tier available)

### Step 1: Open in Google Colab

1. Clone or download this repository
2. Open the `.ipynb` file in [Google Colab](https://colab.research.google.com/)

### Step 2: Get Your Gemini API Key

1. Visit [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Sign in with your Google account
3. Click **"Create API Key"**
4. Copy the generated API key

### Step 3: Configure API Key in Colab

1. In Google Colab, click the **🔑 Secrets** icon in the left sidebar
2. Click **"Add a new secret"**
3. Set the name as:  `GOOGLE_API_KEY`
4. Paste your API key as the value
5. **Important**: Enable **"Notebook access"** toggle

### Step 4: Run the Notebook

1. Go to **Runtime** → **Run all** (or press `Ctrl+F9`)
2. Wait for all cells to execute
3. The main menu will appear at the bottom

### Step 5: Start Analyzing

```python
if __name__ == '__main__':
    main()
```

Choose from the menu: 
- **Option 1**: Run Demo Analysis
- **Option 2**: Run Interactive Analysis (paste your own resume/job)
- **Option 3**: Get General Resume Improvements
- **Option 4**: Exit

---

## 📚 Usage Examples

### Example 1: Demo Analysis

```python
# Run the demo with pre-loaded sample data
run_demo_analysis()
```

**Output**:  Complete analysis with sample resume vs.  sample job description

### Example 2: Interactive Analysis

```python
# Analyze your own resume and job posting
run_interactive_analysis()
```

**Steps**:
1. Paste your resume text when prompted
2. Paste the job description
3. Receive comprehensive analysis

### Example 3: General Resume Review

```python
# Get improvement suggestions for any resume
generate_resume_improvements(resume_text)
display_resume_improvements(improvements)
```

**Output**: General tips and recommendations

---

## 📊 Output Samples

### Match Score Analysis

```
╔════════════════════════════════════════╗
║        JOB FIT ANALYSIS REPORT         ║
╚════════════════════════════════════════╝

🎯 MATCH SCORE:  78%

✅ MATCHING SKILLS: 
  • Python Programming
  • Machine Learning
  • Data Analysis
  • TensorFlow
  • Git Version Control

❌ MISSING SKILLS: 
  • Docker
  • Kubernetes
  • AWS Cloud Services

💡 RECOMMENDATIONS:
  1. Add "Docker containerization" experience
  2. Highlight any cloud platform experience
  3. Include "Kubernetes" if you have basic knowledge
  ... 
```

### Exported Report

Analysis results are automatically saved to: 
- `demo_analysis_report.txt` (for demo mode)
- `interactive_analysis_report.txt` (for interactive mode)

---

## ✅ Testing Checklist

Before deployment, verify the following:

- [ ] **API Connection**: Gemini API key works correctly
- [ ] **Demo Mode**:  `run_demo_analysis()` produces complete output
- [ ] **Interactive Mode**:  `run_interactive_analysis()` handles user input
- [ ] **Error Handling**: 
  - [ ] Missing API key error message
  - [ ] Invalid JSON response handling
  - [ ] Short/invalid input validation
- [ ] **Report Export**: Text files are created successfully
- [ ] **General Improvements**: Resume suggestions are generated
- [ ] **Menu Navigation**: All options in `main()` function work

---

## 🔮 Future Enhancements

### Planned Features

- [ ] **PDF Upload**: Direct PDF resume parsing
- [ ] **ATS Score**:  Dedicated ATS compatibility scoring
- [ ] **Format Checker**: Resume formatting analysis
- [ ] **Multi-Language**: Support for non-English resumes
- [ ] **Browser Extension**: Chrome/Firefox extension for LinkedIn
- [ ] **Mobile App**:  iOS/Android application
- [ ] **Job Recommendations**: AI-powered job matching
- [ ] **Resume Builder**: Interactive resume creation tool
- [ ] **Skill Gap Courses**: Learning resource recommendations
- [ ] **Batch Processing**:  Analyze multiple jobs at once

### Contribute Your Ideas

Have a feature request?  [Open an issue](https://github.com/Umesh-chandra-2006/Job-Fit-Analyzer/issues) or submit a pull request! 

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a new branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Contribution Guidelines

- Follow Python PEP 8 style guidelines
- Add comments for complex logic
- Update documentation for new features
- Test your changes before submitting

---

## 📞 Support

### Common Issues

| Issue | Solution |
|-------|----------|
| **API Key Problems** | Ensure 'Notebook access' is enabled in Colab secrets |
| **Code Errors** | Run all cells in order from top to bottom |
| **JSON Parsing Errors** | Notebook includes markdown fence stripping code |
| **Rate Limits** | Gemini API has usage limits; wait between calls |

### Get Help

- 📧 **Email**: [Your contact email]
- 🐛 **Bug Reports**: [Open an issue](https://github.com/Umesh-chandra-2006/Job-Fit-Analyzer/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/Umesh-chandra-2006/Job-Fit-Analyzer/discussions)
- 📖 **Documentation**: Check the notebook comments

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🌟 Acknowledgments

- **Google Gemini API** for powerful AI capabilities
- **Google Colab** for free computing resources
- **Open Source Community** for inspiration and support

---

## 📈 Project Stats

![GitHub Stars](https://img.shields.io/github/stars/Umesh-chandra-2006/Job-Fit-Analyzer?style=social)
![GitHub Forks](https://img.shields.io/github/forks/Umesh-chandra-2006/Job-Fit-Analyzer?style=social)
![GitHub Issues](https://img.shields.io/github/issues/Umesh-chandra-2006/Job-Fit-Analyzer)
![GitHub Pull Requests](https://img.shields.io/github/issues-pr/Umesh-chandra-2006/Job-Fit-Analyzer)

---

## 🚀 Try It Now!

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Umesh-chandra-2006/Job-Fit-Analyzer/blob/main/Job_Fit_Analyzer.ipynb)

---

<div align="center">

**Made with ❤️ by [Umesh Chandra](https://github.com/Umesh-chandra-2006)**

If this project helped you land your dream job, consider giving it a ⭐! 

</div>
