## Overview
This Jupyter notebook is designed to scrape product information from Amazon using Python. It extracts details such as the product title, price, rating, review count, and availability status. The extracted data is saved in a structured format, making it easy to analyze or export for further use.

## What is Web Scraping?
Web scraping is the automated process of extracting data from websites. Using code, you can retrieve specific pieces of information from a webpage's HTML structure, such as product names, prices, or user reviews. Web scraping is commonly used for data collection in research, market analysis, and price monitoring. It is important to ensure compliance with website terms of service when scraping data.

## About Beautiful Soup
[Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/) is a Python library that simplifies the process of web scraping. It parses the HTML content of web pages, allowing us to easily search for, navigate, and manipulate elements in the HTML structure. Combined with the `requests` library, which sends HTTP requests to retrieve web pages, Beautiful Soup provides an effective toolset for scraping.

## Code Summary
The notebook is structured as follows:

1. **Imports and Setup**:  
   It imports essential libraries—`BeautifulSoup` from `bs4` for HTML parsing, `requests` for HTTP requests, and `pandas` and `numpy` for data handling and cleaning.

2. **Helper Functions**:  
   Several functions are defined to extract specific pieces of information from each product page:
   - `get_title()`: Extracts the product title.
   - `get_price()`: Extracts the product price.
   - `get_rating()`: Extracts the product rating.
   - `get_review_count()`: Extracts the number of user reviews.
   - `get_availability()`: Checks the product's availability status.

3. **Main Execution Block**:
   - A user-agent header is defined to simulate a browser request.
   - An Amazon search URL (for PlayStation 4 products) is accessed to fetch the HTML content.
   - Using Beautiful Soup, the main page is parsed to find product links, which are then stored in a list.
   - For each product link, the code opens the individual product page, scrapes product details, and appends them to a dictionary.

4. **Data Storage**:  
   The extracted information is saved into a Pandas DataFrame. Empty titles are replaced with `NaN`, and rows with missing titles are dropped. Finally, the data is saved to a CSV file named `amazon_data.csv`.

## Dependencies
- Python 3.x
- BeautifulSoup (`bs4`)
- Requests
- Pandas
- NumPy