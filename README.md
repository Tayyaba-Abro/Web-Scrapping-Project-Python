# Web Scrapping Project - List of Largest United State Companies by Revenue

![largest-companies-by-revenue-state](https://github.com/Tayyaba-Abro/Web-Scrapping-Project-Python/assets/47588244/22f2ce7f-c157-46f1-84f0-492427469c94)

Photo Credit: [Visual Capitalist](https://www.visualcapitalist.com/largest-company-every-state-revenue/) 

## Project Overview:
Welcome to my web scraping project that extracts data from the [List of Largest Companies in the United States by Revenue](https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue). The project utilizes Python, the Beautiful Soup library for web scraping, and the Pandas library for data manipulation. The scraped data is then saved to a CSV file.

The primary goal of this project is to demonstrate how web scraping can be used to gather valuable information from websites and present it in a structured format.

## Web Scrapping Step by Step:

Certainly, here are the steps to extract a table from a website using Python and Beautiful Soup:

**Step 1: Import Required Libraries**
```python
from bs4 import BeautifulSoup
import requests
```

**Step 2: Define the URL of the Website**
```python
url = "https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue"
```

**Step 3: Send a GET Request and Parse HTML**
```python
page = requests.get(url)
soup = BeautifulSoup(page.text, 'html.parser')
```

**Step 4: Locate the Table**
```python
table = soup.find('table', class_='wikitable sortable')
```

**Step 5: Extract Data from the Table**
```python
rows = table.find_all('table')[1]
     print(row)
```

**Step 6: Extract Header from the Table**
```python
world_titles = table.find_all('th')
   world_table_titles = [title.text.strip() for title in world_titles]
   print(world_table_titles)
```

**Step 7: Create a Pandas DataFrame**
```python
import pandas as pd
df = pd.DataFrame(columns=world_table_titles)
```

**Step 8: Extract Data from Rows**
```python
column_data = table.find_all('tr')
for row in column_data[1:]:
    row_data = row.find_all('td')
    individual_row_data = [data.text.strip() for data in row_data]
    print(individual_row_data)
    length = len(df)
    df.loc[length] = individual_row_data
```

**Step 9: Display the DataFrame**
```python
print(df)
```

**Step 10: Save Data to CSV**
```python
df.to_csv(r'C:\Users\Asad Ali\Desktop\Courses\Alex the Analyst\Python/Companies.csv', 
```

## Key Takeways:
- **Web Scraping Skills:** Gained valuable experience in web scraping, which is a powerful technique for extracting data from websites for various purposes.
- **Beautiful Soup:** Become familiar with Beautiful Soup, a Python library that simplifies web scraping by parsing HTML and XML documents.
- **Pandas for Data Manipulation:** Used Pandas to organize and manipulate the extracted data, demonstrating how versatile it is for data analysis tasks.


