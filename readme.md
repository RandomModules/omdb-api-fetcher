# OMDb api fetcher

[![Node.js Package](https://github.com/RandomModules/omdb-api-fetcher/actions/workflows/npm-publish-github-packages.yml/badge.svg?branch=main)](https://github.com/RandomModules/omdb-api-fetcher/actions/workflows/npm-publish-github-packages.yml)

Predefined OMDb api fetcher : this is a implement of the api feature of OMDb.

## Get started

```js
const { Omdb } = require('omdb-api-fetcher')

const movies = async (yourParam) => {

    // Using destructuring or anything base on your case.
    const {title} = yourParam

    const movie = new Omdb({
        search: title,
        apiKey: 'YOUR_API_KEY'
    })

    const metaData = await movie.fetchSearch()

    console.log(metaData)

}
```

## Parameter References

Look at the Function Parmeter Equivalent Table bellow to looking for the parameter.

```js
const movie = new Omdb({
    search: 'any_title',
    apiKey: 'YOUR_API_KEY',
    type: 'movie',
    imdbId: 'movie_id_on_imdb',
    year: 2023,
    plot: 'full',
    format: 'json',
    callback: 'callback_name',
})
```

## Function Parmeter Equivalent Table

| **Function Parameter** | **API Querry Parameter** | **Required** | **Valid Options**      | **Default Value** | **Description**                        |
|------------------------|----------------------|--------------|------------------------|-------------------|----------------------------------------|
| search                 | s                    | Yes          |                        | empty           | Movie title to search for. **         |
| imdbId                 | i                    | Optional*    |                        | empty           | A valid IMDb ID (e.g. tt1285016)       |
| title                  | t                    | Optional*    |                        | empty           | Movie title to search for.             |
| type                   | type                 | No           | movie, series, episode | empty           | Type of result to return.              |
| year                   | y                    | No           |                        | empty           | Year of release.                       |
| plot                   | plot                 | No           | short, full            | short             | Return short or full plot.             |
| page                   | page                 | No           | 1-100                  | 1                 | Page number to return. **              |
| format                 | r                    | No           | json, xml              | json              | The data type to return.               |
| callback               | callback             | No           |                        | empty           | JSONP callback name.                   |
| apiVersion             | v                    | No           |                        | 1                 | API version (reserved for future use). |
| apiKey                 | apikey               | Yes          |                        | empty               | API Key                                |

Note:  
<sup> * </sup> Optional  
<sup> ** </sup> For fetchSearch Only
