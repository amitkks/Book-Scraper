---

# Book Scraper

This project is a web scraper built using the Scrapy framework. It extracts the titles, prices, and availability status of books from the website [Books to Scrape](http://books.toscrape.com/). The scraped data is saved in a JSON file for further analysis or processing.

## Prerequisites

- Python 3.x
- Scrapy

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/book-scraper.git
   cd book-scraper
   ```

2. **Create a virtual environment** (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install the required packages**:
   ```bash
   pip install scrapy
   ```

## Usage

1. **Navigate to the project directory**:
   ```bash
   cd book-scraper
   ```

2. **Run the Scrapy spider**:
   ```bash
   scrapy crawl longlegs -o books.json
   ```

   This command will start the scraper and output the results to `books.json`.

## Project Structure

- `CrawlingSpider`: The main Scrapy spider class, which contains the logic for crawling and scraping data from the site.
- `rules`: Defines the rules for following links and extracting data.
  - The first rule follows links to categories.
  - The second rule extracts book details, avoiding category links.
- `parse_item`: A callback function that processes the book details page to extract the title, price, and availability.

## Output

The output of the scraper is a JSON file (`books.json`) with the following structure for each book:

```json
{
    "title": "Book Title",
    "price": "£51.77",
    "availability": "In stock (22 available)"
}
```

## Troubleshooting

- **Connection Issues**: Ensure you have a stable internet connection.
- **Dependencies**: Make sure all necessary packages are installed.
- **Website Structure Changes**: The scraper relies on the current HTML structure of the site. If the site changes, the CSS selectors may need updating.

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- This project is inspired by the Scrapy framework and the [Books to Scrape](http://books.toscrape.com/) website.

---
