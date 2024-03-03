# Stock Data Analysis with Python

This project involves extracting stock data and revenue information for two companies, Tesla and GameStop, and visualizing the data using Python. The data extraction is performed using Yahoo Finance API for stock data and web scraping techniques for revenue data.

## Requirements

- Python 3.x
- Libraries:
  - yfinance
  - requests
  - BeautifulSoup
  - pandas
  - plotly

## Installation

You can install the required libraries using pip:

```bash
pip install yfinance requests BeautifulSoup4 pandas plotly
```

## Usage

1. **Extracting Stock Data and Revenue Information:**

    - Use `yfinance` to extract stock data for Tesla and GameStop.
    - Use web scraping techniques with `requests` and `BeautifulSoup` to extract revenue data for Tesla and GameStop.

2. **Data Visualization:**

    - Use the provided `make_graph` function to plot historical stock prices and revenue data for both companies.
    - The graphs will show data up to June 2021.

3. **Running the Code:**

    - Execute the Python script containing the code.
    - Ensure you have an active internet connection for data extraction.

4. **Sample Code Execution:**

    ```python
    # Extracting Tesla Stock Data and Revenue
    tesla_data = tesla.history(period="max")
    tesla_data.reset_index(inplace=True)
    tesla_revenue = table[1]
    tesla_revenue.columns = ['Date', 'Revenue']
    tesla_revenue["Revenue"] = tesla_revenue['Revenue'].str.replace(',|\$',"")
    tesla_revenue.dropna(inplace=True)
    tesla_revenue = tesla_revenue[tesla_revenue['Revenue'] != ""]

    # Plotting Tesla Stock Graph
    make_graph(tesla_data, tesla_revenue, 'Tesla')

    # Extracting GameStop Stock Data and Revenue
    gme_data = GameStop.history(period = "max")
    gme_data.reset_index(inplace=True)
    gme_revenue = table[1]
    gme_revenue.columns = ["Date","Revenue"]
    gme_revenue["Revenue"] = gme_revenue['Revenue'].str.replace(',|\$',"")
    gme_revenue.dropna(inplace=True)
    gme_revenue = gme_revenue[gme_revenue['Revenue'] != ""]

    # Plotting GameStop Stock Graph
    make_graph(gme_data, gme_revenue, 'GameStop')
    ```

## Contributing

Contributions are welcome! If you have any suggestions, improvements, or bug fixes, feel free to open an issue or create a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
