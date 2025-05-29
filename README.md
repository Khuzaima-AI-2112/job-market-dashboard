# 🔄 Real-time Job Market Dashboard

A comprehensive, real-time job market analysis dashboard built with Streamlit that automatically scrapes job postings from multiple sources and provides live insights and analytics.

[![Dashboard Preview](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://jon-analyzer.streamlit.app/)



## 🚀 Features

### Real-time Data Collection
- **Automated Scraping**: Automatically scrapes job postings from LinkedIn and RemoteOK
- **Manual Refresh**: On-demand data updates with single-click refresh
- **Scheduled Updates**: Configurable auto-refresh intervals (5-120 minutes)
- **Background Processing**: Non-blocking scraper execution using threading
- **Progress Tracking**: Real-time status updates and countdown timers

### Interactive Analytics Dashboard
- **Live Metrics**: Total jobs, companies, cities, and date ranges
- **Top Job Titles**: Most in-demand positions with frequency analysis
- **Skills Analysis**: Required skills breakdown with visual charts
- **Location Insights**: Geographic distribution of job opportunities
- **Trend Analysis**: Job posting trends over time
- **Company Analytics**: Top hiring companies and their job counts

### Advanced Features
- **Smart Filtering**: Filter by source, date range, and other criteria
- **Data Export**: Download filtered data as CSV
- **Activity Logging**: Track all scraper runs and errors
- **Cache Management**: Optimized data loading with intelligent caching
- **Error Handling**: Robust error management with detailed logging
- **Responsive Design**: Mobile-friendly interface with modern styling

## 📋 Prerequisites

- Python 3.8 or higher
- Internet connection for web scraping
- Modern web browser

## 🛠 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/realtime-job-dashboard.git
   cd realtime-job-dashboard
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

4. **Create requirements.txt** (if not exists)
   ```bash
   streamlit>=1.28.0
   pandas>=1.5.0
   plotly>=5.15.0
   numpy>=1.24.0
   requests>=2.31.0
   beautifulsoup4>=4.12.0
   selenium>=4.11.0
   ```

## 🚀 Quick Start

1. **Ensure you have the scraper file**
   Make sure `enhanced_job_scraper.py` is in the same directory as the dashboard

2. **Run the dashboard**
   ```bash
   streamlit run realtime_job_dashboard.py
   ```

3. **Access the dashboard**
   Open your browser and navigate to `http://localhost:8501`

4. **Start collecting data**
   - Click "🔄 Refresh Now" for manual data collection
   - Enable "Auto-refresh" for scheduled updates
   - Upload your own CSV file if you have existing data

## 📁 Project Structure

```
realtime-job-dashboard/
├── realtime_job_dashboard.py    # Main dashboard application
├── enhanced_job_scraper.py      # Web scraper for job data
├── requirements.txt             # Python dependencies
├── README.md                   # This file
├── linkedin_remoteok_jobs.csv  # Data file (created after first run)
└── .gitignore                  # Git ignore file
```

## 🎯 Usage Guide

### Dashboard Navigation

#### 1. **Real-time Controls**
- **Auto-refresh Toggle**: Enable/disable automatic data updates
- **Refresh Interval**: Set update frequency (5-120 minutes)
- **Manual Refresh**: Instantly trigger data collection
- **Clear Cache**: Reset cached data for fresh analysis

#### 2. **Status Monitoring**
- **Live Status**: Current scraper and auto-refresh status
- **Countdown Timer**: Time until next scheduled refresh
- **Activity Log**: Recent scraper runs with timestamps
- **File Information**: Data file size and last modification time

#### 3. **Data Filtering**
- **Source Filter**: Filter by job board (LinkedIn, RemoteOK, etc.)
- **Date Range**: Analyze jobs from specific time periods
- **Real-time Updates**: Filters update automatically with new data

#### 4. **Analytics Sections**
- **Key Metrics**: Overview statistics with real-time updates
- **Job Titles**: Most in-demand positions
- **Skills Analysis**: Required skills frequency
- **Location Insights**: Geographic job distribution
- **Trend Analysis**: Posting patterns over time
- **Company Analytics**: Top hiring organizations

### Configuration Options

#### Auto-refresh Settings
```python
# Modify these in the sidebar
refresh_interval = 30  # minutes
auto_refresh = True    # enable/disable
```

#### Data Sources
- Default: `linkedin_remoteok_jobs.csv`
- Custom: Upload via sidebar file uploader
- Multiple sources supported

## 🔧 Configuration

### Environment Variables
You can customize the dashboard behavior using these settings:

```python
# Session state defaults (in initialize_session_state())
'refresh_interval': 30,          # Default refresh interval in minutes
'data_file_path': 'linkedin_remoteok_jobs.csv',  # Default data file
'auto_refresh': False,           # Auto-refresh disabled by default
```

### Scraper Configuration
Ensure your `enhanced_job_scraper.py` outputs data in this CSV format:
```csv
title,company,location,source,skills,date_posted
Software Engineer,Tech Corp,San Francisco CA,LinkedIn,"Python,JavaScript",2024-01-15
```

## 📊 Data Format

The dashboard expects CSV data with these columns:

| Column | Description | Example |
|--------|-------------|---------|
| `title` | Job title | "Software Engineer" |
| `company` | Company name | "Tech Corp" |
| `location` | Job location | "San Francisco, CA" |
| `source` | Data source | "LinkedIn" |
| `skills` | Required skills (comma-separated) | "Python,JavaScript,React" |
| `date_posted` | Job posting date | "2024-01-15" |

## 🚨 Troubleshooting

### Common Issues

1. **Scraper Not Found**
   ```
   Error: Scraper file not found
   ```
   **Solution**: Ensure `enhanced_job_scraper.py` is in the same directory

2. **Data File Missing**
   ```
   Warning: Data File: Not found
   ```
   **Solution**: Run the scraper first or upload a CSV file

3. **Scraper Timeout**
   ```
   Error: Scraper timed out after 10 minutes
   ```
   **Solution**: Check internet connection and website accessibility

4. **Permission Errors**
   ```
   Error: Permission denied
   ```
   **Solution**: Ensure write permissions in the project directory

### Performance Tips

- **Large Datasets**: Enable caching and use date filters for better performance
- **Memory Usage**: Clear cache periodically for large datasets
- **Auto-refresh**: Use longer intervals (60+ minutes) for production
- **Network**: Ensure stable internet for reliable scraping

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes**
4. **Commit your changes**
   ```bash
   git commit -m 'Add amazing feature'
   ```
5. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
6. **Open a Pull Request**

### Development Guidelines

- Follow PEP 8 style guidelines
- Add docstrings to all functions
- Include error handling for external APIs
- Test with different data sizes
- Update README for new features

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Streamlit** - For the amazing web app framework
- **Plotly** - For interactive visualizations
- **Pandas** - For data manipulation
- **Job Boards** - LinkedIn, RemoteOK for providing job data

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/yourusername/realtime-job-dashboard/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/realtime-job-dashboard/discussions)
- **Email**: your.email@example.com

## 🗺 Roadmap

### Upcoming Features
- [ ] **Additional Job Boards**: Indeed, Glassdoor integration
- [ ] **Email Notifications**: Alerts for new matching jobs
- [ ] **Advanced Filtering**: Salary range, experience level
- [ ] **Job Recommendations**: AI-powered job matching
- [ ] **API Integration**: REST API for external access
- [ ] **Database Support**: PostgreSQL, MongoDB integration
- [ ] **Docker Support**: Containerized deployment
- [ ] **Cloud Deployment**: AWS, GCP, Azure guides

### Version History
- **v1.0.0** - Initial release with basic scraping and analytics
- **v1.1.0** - Added real-time features and auto-refresh
- **v1.2.0** - Enhanced UI and error handling
- **v2.0.0** - Major refactor with threading and improved performance

---

**⭐ Star this repository if you find it helpful!**

Made with ❤️ by [Khuzaima Ahmed](https://www.linkedin.com/in/khuzaima-ahmed/)
