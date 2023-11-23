# Amazon-Scraper: Find your perfect item!

![Amazon Scraper](https://imgur.com/8AaF4Vd.png)

Functionality: scraping multiple amazon web pages for your item, setting a price range for your item, csv/json output, and more!

## Technology Needed:

* Python (here is where you can install python: https://www.python.org/downloads/)
* A python package manager (e.g pip) (here is where you can install pip: https://pip.pypa.io/en/stable/installation/)
* git (here is where you can install git: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Python Dependencies Needed:

* bs4 (BeautifulSoup4)
* requests
* lxml
* rich

## How to use (NOTE: -item or --item and -num or --num are required fields):

### Get the repository: 

```
mkdir "Amazon Scraper"
cd "Amazon Scraper"
git clone https://github.com/Rohithsilent/AMAZON-SCRAPER.git
```

### Install the dependencies:

```
py -m pip install bs4 requests lxml rich
```

# If you encounter issues trying to run commands using "py", you may have to use "python" or "py3" instead. Your system environment PATH variable may also be the issue.

### Moving into the cloned repository:

```
cd Amazon-Scraper
```

### Usage: 

```
usage: scrape.py [-h] [-item ITEM [ITEM ...]] [-min LOWER] [-max UPPER] [-num NUM] [-save OUT] [-c]
Note: Adding -c to the arguments will cause the program to print the cheapest item at the end of scraping
```

#### Individual Commands:

**-item or --item:**

```
py scrape.py -item xbox 
```
OR
```
py scrape.py --item xbox 
```

Tells the program that the item you're looking for is a xbox.

**-min or --lower:**

```
py scrape.py -min 50
```
OR
```
py scrape.py --lower 50
```

Tells the program that the price minimum (lower bound) is 50.

**-max or --upper:**

```
py scrape.py -max 500
```
OR
```
py scrape.py --upper 500
```

Tells the program that the price maximum (upper bound) is 500.

**-num or --num:**

```
py scrape.py -num 10
```
OR
```
py scrape.py --num 10
```

Tells the program that the number of item links you want to pull data from is 100.

**-c:**

```
py scrape.py -c
```

Tells the program that you want it to output the cheapest item after it's scraped all links.

**-save or --out:**

```
py scrape.py -save test
```
OR
```
py scrape.py --out test
```

Tells the program that you want the product information to be written to a csv/json named test. If this argument is not provided the default csv/json the information will go to is: "out.csv"/"out.json"

#### Examples of Possible Run Commands:

Get all items within a price range (USD):

```
py scrape.py -item xbox s -min 200 -max 400 -num 10
```

Get all items above a price (USD):

```
py scrape.py -item yoga mats -min 10 -num 15
```

Get all items below a price (USD):

```
py scrape.py -item playstation -max 400 -num 10
```

Get all items no matter the price:

```
py scrape.py -item car tires -num 10
```

Get the cheapest item of the items scraped and write the information to a csv/json named "gfxcards":

```
py scrape.py -item rtx 3090 -num 50 -c -save gfxcards
```

## CSV: 

Format:

```
title,price,rating,reviews,availability,url
```

The CSV contains **ALL** of the relevant items scraped

## JSON:

Format:

![Amazon Scraper](https://i.imgur.com/xsFHBPt.png)


