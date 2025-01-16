# Financial Analysis Multi-Agent System

## Overview
This project implements a multi-agent system for comprehensive financial analysis of stocks. It combines web searching, stock data analysis, and report generation using three specialized AI agents working in collaboration.

## Features
- Real-time stock data analysis using Yahoo Finance
- Web search integration for latest company information
- Automated report generation and saving
- Technical analysis including moving averages and trend analysis
- Stock price visualization with charts

## Agents
1. **Google Search Agent**: Gathers recent information about companies
2. **Stock Analysis Agent**: Performs technical analysis on stock data
3. **Report Agent**: Compiles information into comprehensive reports

## Prerequisites
```bash
pip install yfinance matplotlib pytz numpy pandas python-dotenv requests bs4 autogen
```

## Environment Setup
Create a `.env` file in the project root with the following:
```
GOOGLE_SEARCH_ENGINE_ID=your_search_engine_id
GOOGLE_API_KEY=your_google_api_key
OPENAI_API_KEY=your_openai_api_key
```

## Directory Structure
```
project/
├── .env
├── stock_analyzer.py
├── coding/
│   ├── stock_plots/
│   └── reports/
└── README.md
```

## Usage
1. Ensure all environment variables are set in `.env`
2. Run the script:
```python
python main.py
```

## Functions

### google_search()
Searches Google for recent information about a company or topic.
- Parameters:
  - query (str): Search query
  - num_results (int): Number of results to return (default: 2)
  - max_chars (int): Maximum characters per result (default: 500)

### analyze_stock()
Performs technical analysis on a given stock ticker.
- Parameters:
  - ticker (str): Stock symbol (e.g., "AAL" for American Airlines)
- Returns:
  - Dictionary containing:
    - Current price
    - 52-week high/low
    - Moving averages
    - Trend analysis
    - Volatility metrics
    - Price chart (saved as PNG)

### save_txt_tool()
Saves generated reports to text files.
- Parameters:
  - text (str): Report content
  - filename (str): Name for the report file (default: "report.txt")

## Output
The system generates:
1. Stock analysis plots (saved in coding/stock_plots/)
2. Text reports (saved in coding/reports/)
3. Console output showing agent interactions

## Example
To analyze American Airlines:
```python
async def main():
    stream = team.run_stream(task="Write a financial report on American airlines")
    await Console(stream)

if __name__ == "__main__":
    asyncio.run(main())
```

## Notes
- The system uses GPT-4 for all agents
- Each agent has a specific role and tools
- The analysis includes both technical and fundamental data
- Reports are saved automatically in the coding directory

## Limitations
- Limited to publicly available stock data
- Requires valid API keys for all services
- Google search is limited to 2 results by default
- Plots are generated in non-interactive mode

## Error Handling
- Validates API keys before execution
- Handles missing stock data gracefully
- Provides error messages for failed API requests
- Ensures proper file saving with error reporting

## Contributing
Feel free to submit issues and enhancement requests!

## License
MIT License