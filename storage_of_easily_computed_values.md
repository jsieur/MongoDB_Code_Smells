# Storage of easily computed values

## Description

<p>Storing easily calculated values unnecessarily takes storage space. Rarely they can improve performance, but their storage is unnecessary when they can be easily calculated.</p>

## Example

<p>Suppose the following collection:</p>
<pre><code>db={
  "beers": [
    {
      "_id": 1,
      "name": "Lupulus Hibernatus",
      "bottle_case_size": 24,
      "bottle_liter_capacity": 0.33,
      "liter_per_case": 7.92
    },
    {
      "_id": 2,
      "name": "Maes Pils",
      "bottle_case_size": 24,
      "bottle_liter_capacity": 0.25,
      "liter_per_case": 6
    }
  ]
}</code></pre>

## Solution

The <code>liter_per_case</code> can be deleted as the program can compute it when needed:
<pre><code>db={
  "beers": [
    {
      "_id": 1,
      "name": "Lupulus Hibernatus",
      "bottle_case_size": 24,
      "bottle_liter_capacity": 0.33,
    },
    {
      "_id": 2,
      "name": "Maes Pils",
      "bottle_case_size": 24,
      "bottle_liter_capacity": 0.25,
    }
  ]
}</code></pre>