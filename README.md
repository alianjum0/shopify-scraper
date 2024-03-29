# Shopify scrapping bot

Generic Bot to scrap all products from a Shopify or e-commerce website

## Practical use cases

 - A website is required to redesign to another platform.

How does it work?
================  

 This script runs sitemapper which find all the pages of the website using
`sitemapper` module. Then it runs metascraper on all the products pages using
browserless in baches of 100 pages to collect product data. All the sites are
stored in `domain.com-sites.json` file and products are stored in
`domain.com-data.json`.

## Installation

 - Installing Node.js from [Node.js download page](https://nodejs.org/en/download/)
 - `npm install`
 - Create `.env` file same as [.env.example](/.env.example) and set the
   variables.
 - Set *URL* variable in `.env` file. 
 - Set *TEST_COUNT* variable to run on few pages for test, so it is not blocked by too many
   request.
 - `npm start` (run the product_scrapper.js, and write all the products to
   domain.com-data.json)
 - Tested on websites
```
URL=https://www.cavamorande.cl/sitemap.xml
URL=https://kharakapas.com/sitemap.xml
URL=https://argentwork.com/sitemap.xml
```

## Transforming Response Data

 - In every website there are some values not available. To remove null value
   use [transform](/transform.js) script. 
 - Write comma seperated values in `.env` file for *KEYS*
 - Run transofrm script `npm run transform`

