swagger: "2.0"
x-collection-name: Intrinio
x-complete: 1
info:
  title: Intrinio
  version: 1.0.0
host: api.intrinio.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /news_sector_sentiments:
    get:
      summary: Sector News Sentiments
      description: Returns daily summaries of news sentiments by sector and date.
      operationId: sector-news-sentiments
      x-api-path-slug: news-sector-sentiments-get
      parameters:
      - in: query
        name: end_date
        description: 'the latest date for which to return data: YYYY'
        type: string
      - in: query
        name: page_number
        description: an integer greater than or equal to 1 for specifying the page
          number for the return values
        type: string
      - in: query
        name: page_size
        description: an integer greater than 1 for specifying the number of results
          on each page
        type: string
      - in: query
        name: sector
        description: 'the name of the sector: SECTORS'
        type: string
      - in: query
        name: source
        description: 'The source of the data: tip'
        type: string
      - in: query
        name: start_date
        description: 'the earliest date for which to return data: YYYY'
        type: string
      responses:
        200:
          description: OK
      tags:
      - Market Data
      - News
      - Sector
      - Sentiments