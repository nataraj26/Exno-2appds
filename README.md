# Exno-2 Data Collection through web scraping using python
**AIM:**
    
    To Perform Data Collection through web scraping using python.

**ALGORITHM:**
	Step 1: Include the Necessary python libraries.
 
	Step 2: Use the requests library to send HTTP requests to a web page.
 
	Step 3: Retrieve the HTML content and use BeautifulSoup to parse it.
 
	Step 4: Navigate and extract the necessary data.
 
	Step 5: Handle the Java script content and retrieve the data using the html tags.
 
	Step 6: Check with the website permission and scrap the content.

**CODING & OUTPUT:**
```python
!pip install beautifulsoup4 requests

import requests 
from bs4 import BeautifulSoup
import pandas as pd

url='https://www.javatpoint.com/python-tutorial'
response = requests.get(url)
soup =  BeautifulSoup(response.content, 'html.parser')

headings= soup.find_all('h3') 
for heading in headings:
   print(heading.text)
df = heading.text
```
![image](https://github.com/user-attachments/assets/8389b9f1-5990-4c04-84e6-bf017666355e)
```python
data = []
for heading in headings:
   data.append(heading.text)
df=pd.DataFrame (data, columns=['Heading'])
df.to_csv('newdata.csv',index=False)
df.head()
```
![image](https://github.com/user-attachments/assets/0fb96152-521d-4dc5-8dd7-5739d3dc4dfd)


**RESULT:**

The above expriment Data Collection through web scraping using python excuted successfully.

