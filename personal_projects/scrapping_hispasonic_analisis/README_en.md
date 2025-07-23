# Hispasonic Ads Scraper & Analyzer

This project scrapes and analyzes musical instrument advertisements from the second-hand market section of Hispasonic.com, with a specific focus on the "keyboards and synthesizers" category. The main goal is to gather, process, and structure the ad data for further analysis.

The entire process is documented in the `01_from_web_to_csv_togit.ipynb` Jupyter Notebook.

---

## Process

1.  **Web Scraping**: The script begins by determining the total number of pages in the "keyboards and synthesizers" category. It then iterates through each page to collect the URLs of all individual ads.
2.  **Local Download**: To avoid overloading the server and the risk of being banned, each ad's HTML content is downloaded and saved locally.
3.  **Data Extraction**: The script parses the local HTML files to extract key information from each ad, including:
    *   **Action**: Type of ad (e.g., sale, looking for, trade).
    *   **Brand**: The manufacturer of the instrument.
    *   **Price**: The listed price.
    *   **User**: The seller's username.
    *   **Location**: The seller's city.
    *   **Dates**: Publication and expiration dates.
    *   **Views**: The number of times the ad has been viewed.
4.  **Data Cleaning & Processing**: The extracted data is cleaned and processed. A key step is the conversion of relative dates (e.g., "3 days ago", "2 weeks ago") into a standard `YYYY/MM/DD` format.
5.  **Export to CSV**: The final, structured data is exported to a CSV file, ready for analysis.

## Technologies Used

*   **Python**
*   **Jupyter Notebook**
*   **Libraries**:
    *   `requests` for making HTTP requests.
    *   `BeautifulSoup4` for parsing HTML.
    *   `pandas` for data manipulation and creating the final DataFrame.
    *   `re` for regular expressions used in data extraction.
    *   `datetime` for handling date and time operations.

---
