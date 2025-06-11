# Data-Source-API-Analyst-Test  
Homework project – GitHub REST API extraction

## Overview
This repository contains my submission for the **Data Source API Analyst** homework assignment. The project demonstrates proficiency in working with REST APIs, specifically the GitHub API, including data extraction, error handling, and documentation.

##  Assignment Objectives
- Research and implement GitHub API integration
- Test API endpoints using Google Colab (bonus points approach)
- Handle authentication, pagination, and rate limiting
- Create comprehensive documentation and troubleshooting guides

## 📁 Repository Structure
```
Data-Source-API-Analyst-Test/
├── README.md                          # This file
├── Content/                           # Documentation and guides
│   ├── api_documentation.md           # GitHub API endpoint documentation
│   ├── troubleshooting.md             # Common issues and solutions
└── Postman_Collection/                # Google Colab notebook
    └── GitHub_API_Data_Extraction.ipynb  # Main implementation
```

### API Endpoints Covered
1. **Repository Search** (`/search/repositories`)

2. **Commit History** (`/repos/{owner}/{repo}/commits`)

3. **Repository Contents** (`/repos/{owner}/{repo}/contents/{path}`)

### Key Features Implemented
- ✅ **Authentication**: Personal Access Token integration
- ✅ **Rate Limiting**: Retry logic
- ✅ **Pagination**: Automatic handling
- ✅ **Error Handling**: 401, 403, 404, and network error recovery
- ✅ **Data Processing**: Pandas integration for analysis

### Prerequisites
- Google account (for Colab access)
- GitHub Personal Access Token

### Setup Instructions

1. **Open Google Colab**
   - Go to [colab.research.google.com](https://colab.research.google.com)
   - Upload the notebook from `/Postman_Collection/GitHub_API_Data_Extraction.ipynb`

2. **Configure Authentication**
   - Create GitHub Personal Access Token (Settings → Developer settings → Personal access tokens)
   - Create `GH_TOKEN` in the notebook with your actual token

4. **Run the Analysis**
   - Execute cells sequentially
   - Review generated analysis reports

##  Sample Results

- Check /sample_data directory to view the output files  

