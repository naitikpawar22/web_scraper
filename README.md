# web_scraper
Build a web scraper using libraries like BeautifulSoup and requests to extract data from a website. For example, scrape news headlines from a news website.
#Develop a simple web scraper that extracts information from a website.
       
       pip install requests beautifulsoup4
      
import requests
from bs4 import BeautifulSoup

  # URL of the website to scrape
url = 'https://www.moneycontrol.com/news/india/'

  # Send a GET request to the website
response = requests.get(url)

  # Check if the request was successful
if response.status_code == 200:
    # Parse the HTML content of the page
     soup = BeautifulSoup(response.content, 'html.parser')

# Find all article titles (assuming they are in <h2> tags)
titles = soup.find_all('h2')

# Print the titles of the articles
for title in titles:
    print(title.get_text())
else:
     print(f"Failed to retrieve the webpage. Status code: {response.status_code}")
