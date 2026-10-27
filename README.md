# scrapy_quotes

A Scrapy spider that collects every quote from [quotes.toscrape.com](http://quotes.toscrape.com/), following the "Next" link through all pages.

## Setup

With pipenv (the `Pipfile` targets Python 3.9):

```
pipenv install
```

Or install Scrapy directly:

```
pip install scrapy
```

## Usage

```
scrapy crawl quotes -O quotes.json
```

`-O` overwrites the output file. Use a `.csv` extension to export CSV instead.

## Output

Each item has two fields:

| Field    | Description                              |
|----------|------------------------------------------|
| `author` | The quote's author                       |
| `text`   | The quote, with curly quote marks removed |

A full run scrapes 10 pages and yields 100 quotes. `quotes.json` in this repo is a sample of that output.

## Project layout

```
quotes/
  spiders/quotes_spider.py   # the spider
  settings.py                # Scrapy settings (obeys robots.txt, UTF-8 export)
scrapy.cfg
Pipfile
```
