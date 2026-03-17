# Webscraping-Book-Site


### Table of Contents
- [Project Overview](#project-overview)
- [Objective](#objective)
- [Tools and Technologies](#tools-and-technologies)
- [Project Features](#project-features)
- [Key Learnings](#key-learnings)
- [Use Cases](#use-cases)
- [Acknowledgement](#acknowledgement)



### Project Overview
This project is a Python-based web scraping pipeline that extracts book data from a [Book website]( https://books.toscrape.com/)
The scraper collects structured data across multiple pages (1–50) and exports it into clean, analysis-ready formats.


### Objective
To build an end-to-end data extraction workflow that:
- Scrapes book information from a real website
- Handles pagination (multiple pages)
- Structures the data for analysis
- Exports results for further use


### Tools and Technologies
- Python
- Requests – for sending HTTP requests
- BeautifulSoup – for parsing HTML content
- Pandas – for data manipulation and export
- Jupyter Notebook


### Project Features
1. Send Request
   - The script sends a GET request to the website to retrieve HTML content.
  
2. Parse HTML
   - BeautifulSoup is used to parse and navigate the HTML structure.
  
3. Extract Data
   - For each book, the following fields are extracted:
     - Title (from <h3> tag)
     - Rating (from class attribute)
     - Price (from price class)
     - Availability (stock status)
    
4. Handle Pagination
   - A loop iterates through 50 pages:
  
     ``` python
     for page_num in range(1, 51):
     ```

5. Store Data
   - Extracted data is stored in a list:
  
     ``` python
     books_data.append([title, rating, price, availability])
     ```


6. Convert to DataFrame

   ``` python
   df = pd.DataFrame(books_data, columns=["Title", "Rating", "Price", "Availability"])
   ```


7. Export Data

   ``` python
   df.to_csv("books_data.csv", index=False)
   df.to_excel("books_data.xlsx", index=False)
   ```


### Key Learnings
- Building a complete web scraping workflow
- Understanding HTML structure and tags
- Handling pagination efficiently
- Structuring raw data for analysis
- Exporting data into usable formats


### Use Cases
This project demonstrates how data can be collected from websites and prepared for:
- Data analysis
- Market research
- Pricing insights
- Inventory monitoring


### Acknowledgement
This was a guided project from the YouTube channnel [Her Data Project](https://www.youtube.com/watch?v=yoE5pmotmjU)





