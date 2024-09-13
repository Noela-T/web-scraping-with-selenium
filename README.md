# Grant Data Scraper

This project is a web scraping script designed to gather grant data from the Mott Foundation's website. The script uses Selenium to navigate through web pages and extract relevant information about grants.

## Requirements

- Python 3.x
- Selenium
- WebDriver Manager for Chrome
- Google Chrome browser

## Installation

1. **Clone the repository:**
    ```sh
    git clone https://github.com/yourusername/grant-data-scraper.git
    cd grant-data-scraper
    ```

2. **Create and activate a virtual environment:**
    ```sh
    python -m venv venv
    source venv/bin/activate   # On Windows, use `venv\Scripts\activate`
    ```

3. **Install the required packages:**
    ```sh
    pip install -r requirements.txt
    ```

## Script Details

The script does the following:

### Setup

- Initializes the Selenium WebDriver.
- Defines helper functions `safe_find_element_text` and `safe_find_element_attribute` to safely extract text and attributes from web elements, avoiding `NoSuchElementException`.

### Scraping Loop

- Iterates over a list of countries and their respective page numbers.
- Loads each page and extracts grant information.
- Clicks on each grant link to navigate to the detailed page and extract additional information.
- Handles potential exceptions and avoids `StaleElementReferenceException` by going back to the main page after each grant.

### Saving Data

- Writes the scraped data to a `.json` file.
