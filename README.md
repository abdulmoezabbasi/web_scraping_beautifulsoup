# Web Scraping with BeautifulSoup, Books to Scrape

An end-to-end web scraping project built in Python that collects, cleans and analyses data from [books.toscrape.com](http://books.toscrape.com).

📓 **Kaggle Notebook:**  https://www.kaggle.com/code/abdulmoezabbasi/web_scraping_beautifulsoup_books



## Project Overview

The project scrapes all 1,000 books across 50 pages, visits each book's individual page to extract genre and description, and produces a clean dataset ready for analysis. The full pipeline covers data collection, error handling, data cleaning, export and exploratory analysis.



## What's Covered

**Scraping**
- Multi-page scraping across 50 listing pages
- Two-pass approach — listing pages for surface data, individual book pages for genre and description (~1,050 requests total)
- Retry logic with exponential backoff to handle failed requests
- Polite request delays to avoid overloading the server
- UTF-8 encoding handled explicitly to avoid currency symbol parsing issues

**Data & EDA**
- 1,000 books with 6 features: title, price, rating, availability, genre, description
- Null checks, outlier detection via IQR, genre summary table
- Price distribution, average price by genre, rating distribution
- Correlation analysis between price and star rating

**Visualisations**
- Top 15 genres by book count
- Average price by genre
- Price distribution by star rating (box plot)
- Overall price distribution with median marker
- Correlation heatmap



## Tech Stack

| Library | Purpose |
|---|---|
| `requests` | HTTP requests |
| `BeautifulSoup4` | HTML parsing |
| `pandas` | Data manipulation and analysis |
| `matplotlib` | Plotting |
| `seaborn` | Statistical visualisations |



## How to Run

**On Kaggle:** Open the notebook link above and click Run All, no dataset needed.

**Locally:**
```bash
pip install requests beautifulsoup4 pandas matplotlib seaborn
jupyter notebook web-scraping-beautifulsoup-books.ipynb
```



## Output

Running the notebook produces `books_data.csv`, a clean 1,000 row dataset with the following columns:

| Column | Description |
|---|---|
| `title` | Book title |
| `price_gbp` | Price in GBP |
| `rating` | Star rating (1–5) |
| `availability` | In Stock / Out of Stock |
| `genre` | Book genre |
| `description` | Book description |
