# Virtualtrips JavaScript code challenge

This challenge has three parts:

1. Written answers to [Questions](./QUESTIONS.md)
2. Building a geo search API server using Node.js
3. Building a React.js app to search for and display results

We're looking for elegant, clean solutions.  Try to think of and handle possible edge cases.

This challenge is sent to experienced developers and newcomers alike. Developers who are familiar with the technologies can complete this within an hour, those who are less familiar will take longer. We suggest spending a maximum of 2 hours on this challenge, the objective is to demonstrate you think through a problem.

## Part 1: Questions

The goal here is to demonstrate your JavaScript knowledge and to write your answers as clearly as possible. Please write each response under the relevant question in the [Questions](./QUESTIONS.md) file.

## Part 2: The geo search API server

The objective is to create a server which can be queried for names of points of interest in the UK.

For a given input such as `hastin` a set of matching results should be returned which start with this input.

Specification:

The server should respond to the following route

    /locations?q=fuzzyMatchString

Where `fuzzyMatchString` will be a partial name of a location. For example

    /locations?q=hastin

Could return a the following JSON response (NOTE: Your dataset only contains GB locations, so the results will differ)

    [
      "Hastings Castle",
      "Hastings Slieve Donard Hotel",
      "Hastings Everglades Hotel",
      "Hastings Railway Station",
      "Hastings Culloden Estate",
      "Hastings Europa Hotel",
      "Hastings District",
      "Hastingleigh",
      "Hastingwood",
      "Hastings Stormont",
      "Hastings Ballygally Castle Hotel",
      "Hastings Culloden Estate & Spa",
      "Hastings Slieve Donard Resort And Spa"
    ]

NOTE: You should only start fuzzy matches if 2 or more characters are in the search string.

Implementation:

You can use whatever server library you like but it must be written in [node.js](https://nodejs.org). 

The location data for your server should be stored in a [SQLite](https://www.sqlite.org/) database, and be loaded in from the [data source](data/) provided in this repo. The [readme](data/readme.txt) in that directory explains how to use the data.

## Part 3: The React.js app to search for and display results

The objective is to provide a user interface to search for names that queries the API server you made in part 2.

The interface should comprise of a search box and list of results.

The results should be displayed in a list below the search box and update as the user types:

```
   [ Search here     ]

   * Result 1
   * Result 2
   * Result 3
   * Result 4

```

NOTE: It is important to display the correct results for a given search term. 

Implementation:

The implementation should be a single page app using React.js. The solution is only required to support the latest version of Chrome.

## Rules

All work should be committed into a fork of this repo or pushed to a publicly-accessible repo. Feel free to add files/folders for part 2 and 3 as you see fit into this directory.

You'll get bonus points if you

 * Display coordinates next to results
 * Add tests your code
 * Provide good documentation
 * Sort the results by the closest name match

Good luck!
