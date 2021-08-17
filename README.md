## coingecko (Resources)

<p>Main idea behind this code is to extract information off from internet about all the existing crypto currency and their relevant information like 
price, 24h Volume, Market Cap etc.

following the link below will lead you to the website from which data has been scraped out <br/>
[visit website](https://www.coingecko.com/en/coins "coingecko")

Link to the API used in code is as follows: <br/>
[visit website](https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=250&page=1&sparkline=false "coingecko API")
</p>

<br/><br/><br/>

## ABOUT main.py

There are two sections to this code :<br/>
**- Scraping data from API**<br/>
**- Scraping community links from website**<br/>
<br/>

_1. Scraping data from API_

<p> In the following section of the code, while loop has been used so as to get link of all pages containing data and storing it in **ur**.
After the request has been made, the contents of the JSON file will be loaded into coins from which all the relevant data will be extracted.
Lopp stops as soon as the content of page gets over.</p>  

``` use python
u = "https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=250&page="

c = 0
us = []
ur = []
while y:
    coins = []
    c = c + 1
    ur = u + str(c)
    response = requests.get(ur)
    coins = json.loads(response.text)
    for coin in coins:
    
    if (coins == []):
       y = 0
    else:
       us.append(ur)

```
------
------

<p> After successfully extraction of all the information form JSON file, we will move on towards scraping data from <br/>

[visit website](https://www.coingecko.com/en/coins "coingecko").
This website contains information like link to  community, wallets, explores etc. for every single coin that exists.
</p>

<p> In the below mentioned code, webdriver is first installed in the cache for your mentioned version of chrome.
To get link of all pages for retrieving coin information, 'id' is fetched from list and appended at the end of url to get information of that specific coin.
All the id's of coin are fetched and then the link to information page is appended to the list **pages**
</p>

``` use python
driver = webdriver.Chrome(ChromeDriverManager(version="92.0.4515.107").install())

page_link = "https://www.coingecko.com/en/coins/"
pages = []
for pg in range(len(c_id)):
    endID = ''
    endID = c_id[pg]
    p_link = page_link + endID
    pages.append(p_link)

```

------








