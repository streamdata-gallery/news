---
swagger: "2.0"
x-collection-name: New York Times
x-complete: 0
info:
  title: New York Times The Semantic API
  description: The Semantic API complements the Articles API. With the Semantic API,
    you get access to the long list of people, places, organizations and other locations,
    entities and descriptors that make up the controlled vocabulary used as metadata
    by The New York Times (sometimes referred to as Times Tags and used for Times
    Topics pages.
  termsOfService: https://developer.nytimes.com/tou
  version: 2.0.0
host: api.nytimes.com
basePath: /svc
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /topstories/v2/{section}.{format}:
    get:
      summary: Top Stories
      description: The Top Stories API returns a list of articles and associated images
        currently on the specified section.  Support JSON and JSONP.
      operationId: the-top-stories-api-returns-a-list-of-articles-and-associated-images-currently-on-the-specified-sect
      x-api-path-slug: topstoriesv2section-format-get
      parameters:
      - in: query
        name: callback
        description: The name of the function the API call results will be passed
          to
      - in: path
        name: format
        description: if this is JSONP or JSON
      - in: path
        name: section
        description: The section the story appears in
      responses:
        200:
          description: OK
      tags:
      - News
  /search/v2/articlesearch.json:
    get:
      summary: Article Search
      description: Article SearchWith the Article Search API, you can search New York
        Times articles from Sept. 18, 1851 to today, retrieving headlines, abstracts,
        lead paragraphs, links to associated multimedia and other article.
      operationId: article-search-requests-use-the-following-uri-structure
      x-api-path-slug: searchv2articlesearch-json-get
      parameters:
      - in: query
        name: api-key
        description: The API key
        type: string
        format: string
      - in: query
        name: begin_date
        description: 'Format: YYYYMMDD Restricts responses to results with publication
          dates of the date specified or later'
      - in: query
        name: end_date
        description: 'Format: YYYYMMDD Restricts responses to results with publication
          dates of the date specified or earlier'
      - in: query
        name: facet_field
        description: Comma-delimited list of facetsSpecifies the sets of facet values
          to include in the facets array at the end of response, which collects the
          facet values from all the search results
      - in: query
        name: facet_filter
        description: When set to true, facet counts will respect any applied filters
          (fq, date range, etc
      - in: query
        name: fl
        description: Comma-delimited list of fields (no limit)  Limits the fields
          returned in your search results
      - in: query
        name: fq
        description: Filtered search query using standard Lucene syntax
      - in: query
        name: hl
        description: Enables highlighting in search results
      - in: query
        name: page
        description: The value of page corresponds to a set of 10 results (it does
          not indicate the starting number of the result set)
      - in: query
        name: q
        description: Search query term
      - in: query
        name: sort
        description: By default, search results are sorted by their relevance to the
          query term (q)
      responses:
        200:
          description: OK
      tags:
      - News
  /books/v2/lists.{format}:
    get:
      summary: Best Seller List
      description: The Books API has services for getting information about The New
        York Times Best Sellers Lists and Book Reviews.
      operationId: GET_lists-format
      x-api-path-slug: booksv2lists-format-get
      parameters:
      - in: query
        name: bestsellers-date
        description: YYYY-MM-DDThe week-ending date for the sales reflected on list-name
      - in: query
        name: date
        description: YYYY-MM-DD  The date the best-seller list was published on NYTimes
      - in: path
        name: format
        description: The format
        type: string
        format: string
      - in: query
        name: isbn
        description: International Standard Book Number, 10 or 13 digits
      - in: query
        name: list
        description: The name of the Times best-seller list
      - in: query
        name: offset
        description: Sets the starting point of the result set
      - in: query
        name: published-date
        description: YYYY-MM-DDThe date the best-seller list was published on NYTimes
      - in: query
        name: rank
        description: The rank of the best seller on list-name as of bestsellers-date
      - in: query
        name: rank-last-week
        description: The rank of the best seller on list-name one week prior to bestsellers-date
      - in: query
        name: sort-order
        description: Sets the sort order of the result set
      - in: query
        name: weeks-on-list
        description: The number of weeks that the best seller has been on list-name,
          as of bestsellers-date
      responses:
        200:
          description: OK
      tags:
      - News
      - Lists
  /query.json:
    get:
      summary: Geographic API
      description: The Geographic API extends the Semantic API, using a linked data
        approach to enhance location concepts used in The New York Times' controlled
        vocabulary and data resources which combine them with the GeoNames database,
        an authoritative and free to use database of global geographical places, names
        and features.
      operationId: geographic-api
      x-api-path-slug: query-json-get
      parameters:
      - in: query
        name: date_range
        description: Start date to end date in the following format- YYYY-MM-DD:YYYY-MM-DD
      - in: query
        name: elevation
        description: The elevation of the specified place, in meters
      - in: query
        name: facets
        description: When facets is set to 1, a count of all facets will be included
          in the response
      - in: query
        name: filter
        description: Filters search results based on the facets provided
      - in: query
        name: latitude
        description: The latitude of the specified place
      - in: query
        name: limit
        description: Limits the number of results returned
      - in: query
        name: longitude
        description: The longitude of the specified place
      - in: query
        name: name
        description: A displayable name for the specified place
      - in: query
        name: offset
        description: Sets the starting point of the result set
      - in: query
        name: query
        description: 'Search keywords to perform a text search on the fields: web_description,
          event_name and venue_name'
      - in: query
        name: sort
        description: Sorts your results on the fields specified
      - in: query
        name: sw
        description: Along with ne, forms a bounded box using the longitude and latitude
          coordinates specified as the southwest corner
      responses:
        200:
          description: OK
      tags:
      - News
      - Geo
  /mostpopular/v2/mostshared/{section}/{time-period}.json:
    get:
      summary: Most Shared by Section & Time Period
      description: With the Most Popular API, you can get links and metadata for the
        blog posts and articles that are most frequently e-mailed, shared and viewed
        by NYTimes.co
      operationId: GET_mostshared-section-time-period-json
      x-api-path-slug: mostpopularv2mostsharedsectiontimeperiod-json-get
      parameters:
      - in: path
        name: section
        description: The section of the paper
        type: string
        format: string
      - in: path
        name: time-period
        description: The period of time
        type: string
        format: string
      responses:
        200:
          description: OK
      tags:
      - News
  /mostpopular/v2/mostemailed/{section}/{time-period}.json:
    get:
      summary: Most Emailed by Section & Time Period
      description: With the Most Popular API, you can get links and metadata for the
        blog posts and articles that are most frequently e-mailed, shared and viewed
        by NYTimes.co
      operationId: GET_mostemailed-section-time-period-json
      x-api-path-slug: mostpopularv2mostemailedsectiontimeperiod-json-get
      parameters:
      - in: path
        name: section
        description: The section of the paper
        type: string
        format: string
      - in: path
        name: time-period
        description: The period of time
        type: string
        format: string
      responses:
        200:
          description: OK
      tags:
      - News
  /mostpopular/v2/mostviewed/{section}/{time-period}.json:
    get:
      summary: Most Viewed by Section & Time Period
      description: With the Most Popular API, you can get links and metadata for the
        blog posts and articles that are most frequently e-mailed, shared and viewed
        by NYTimes.co
      operationId: GET_mostviewed-section-time-period-json
      x-api-path-slug: mostpopularv2mostviewedsectiontimeperiod-json-get
      parameters:
      - in: path
        name: section
        description: The section of the paper
        type: string
        format: string
      - in: path
        name: time-period
        description: The period of time
        type: string
        format: string
      responses:
        200:
          description: OK
      tags:
      - News
  /name/{concept-type}/{specific-concept}.json:
    get:
      summary: The Semantic API
      description: The Semantic API complements the Articles API. With the Semantic
        API, you get access to the long list of people, places, organizations and
        other locations, entities and descriptors that make up the controlled vocabulary
        used as metadata by The New York Times (sometimes referred to as Times Tags
        and used for Times Topics pages.
      operationId: getSemantics
      x-api-path-slug: nameconcepttypespecificconcept-json-get
      parameters:
      - in: path
        name: concept-type
        description: The type of the concept, used for Constructing a Semantic API
          Request by Concept Type and Specific Concept Name
      - in: query
        name: fields
        description: 'all or comma-separated list of specific optional fields: pages,
          ticker_symbol, links, taxonomy, combinations, geocodes, article_list, scope_notes,
          search_api_queryOptional fields are returned in result_set'
      - in: query
        name: query
        description: Precedes the search term string
      - in: path
        name: specific-concept
        description: The name of the concept, used for Constructing a Semantic API
          Request by Concept Type and Specific Concept Name
      responses:
        200:
          description: OK
      tags:
      - Semantics
      - News
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---