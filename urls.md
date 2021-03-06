## Routes

### Table of Contents

- [List of comics in the api](#apititlesjson)
- [Comic's sales by issue](#apititlesidby-issuejson)
- [Comic's sale by month](#apititlesidby-monthjson)
- [Source data](#apisource-datayear-monthjson)

### Base url

Prepend `https://comichron-data.github.io` to all routes shown below to form the full url.

### `/api/titles.json`

List of all comics in the api, sorted by title.

#### Example

```js
[
  {
    "id": "saga-image",
    "title": "Saga",
    "publisher": "Image"
  },
  {
    "id": "shutter-image",
    "title": "Shutter",
    "publisher": "Image"
  },
  // and so on
]
```

### `/api/titles/{id}/by-issue.json`

Comic's sales numbers by issue.

- `id` is the comic's id (see `/api/titles.json`)

#### Example

```js
{
  "id": "comic id",
  "title": "comic title",
  "publisher": "comic publisher",
  "records": [
    {
      "issue": 1,
      "count": 5000
    },
    {
      "issue": 2,
      "count": 4000
    },
    // and so on
  ]
}
```

### `/api/titles/{id}/by-month.json`

Comic's sales numbers by month.

- `id` is the comic's id (see `/api/titles.json`)

#### Example

```js
{
  "id": "comic id",
  "title": "comic title",
  "publisher": "comic publisher",
  "records": [
    {
      "year": 2012,
      "month": 3,
      "count": 37641
    },
    {
      "year": 2012,
      "month": 4,
      "count": 46526
    },
    // and so on
  ]
}
```

### `/api/source-data/{year}-{month}.json`

Data scraped from comichron. All other routes are based on this data.

- `year` is a 4 digit year.
- `month` is a 2 digit month (e.g. `02`, `11`). January is `01`.

#### Example

```js
[
  {
    "rank": 1,
    "title": "Star Wars Shattered Empire",
    "id": "star-wars-shattered-empire-marvel",
    "issue": 1,
    "price": "$3.99",
    "publisher": "Marvel",
    "count": 208884
  },
  {
    "rank": 2,
    "title": "Star Wars",
    "id": "star-wars-marvel",
    "issue": 9,
    "price": "$3.99",
    "publisher": "Marvel",
    "count": 135817
  },
  // and so on
]
```
