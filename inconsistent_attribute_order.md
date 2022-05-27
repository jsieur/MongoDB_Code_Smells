# Inconsistent attribute order

## Description

<p>MongoDB allows flexibility, but a consistent attribute order is necessary when searching for documents. Breaking this rule can lead to incomplete query results.</p>

## Example

<p>Suppose the following collection:</p>
<pre><code>db={
  "books": [
    {
      "_id": 1,
      "isbn": 9780140817744,
      "author": {
        "surname": "Orwell",
        "firstname": "George"
      },
      "title": "1984" 
    },
    {
      "_id": 2,
      "isbn": 9780631120001,
      "author": {
        "firstname": "Ludwig",
        "surname": "Wittgenstein"
      },
      "title": "On certainty"
    }
  ]
}</code></pre>

<p>The following query would not result in any document because of the wrong field order:</p>
<pre><code>
db.books.find({
  "author": {
    "firstname": "George",
    "surname": "Orwell"
  }
})</code></pre>


## Solution

The order of author's attributes should be consistent:

<pre><code>db={
  "books": [
    {
      "_id": 1,
      "isbn": 9780140817744,
      "author": {
        "firstname": "George",
        "surname": "Orwell"
      },
      "title": "1984"
    },
    {
      "_id": 2,
      "isbn": 9780631120001,
      "author": {
        "firstname": "Ludwig",
        "surname": "Wittgenstein"
      },
      "title": "On certainty"
    } 
  ]
}</code></pre>