# Extract the domain name from a URL

## Problem Description

Write a function that when given a URL as a string, parses out just the domain name and returns it as a string. For example:

```
input: "https://github.com/"
output: "github"
```

```
input: "https://www.codewars.com/kata/514a024011ea4fb54200004b"
output: "codewars"
```

## Solution Approach

1. Remove the protocol (http, https) and www. from the URL.
2. Split the URL by the dot (.) and return the first part.

## Code Implementation

```js
function domainName(url) {
  url = url.replace(/^(https?:\/\/)?(www\.)?/, '');
  const domainName = url.split('.')[0];
  return domainName;
}
```

## Test Cases

```js
console.log(domainName('https://github.com/')); // "github"
console.log(
  domainName('https://www.codewars.com/kata/514a024011ea4fb54200004b')
); // "codewars"
```

## Other Solutions

```js
function domainName(url) {
  return url.match(/(?:http(?:s)?:\/\/)?(?:w{3}\.)?([^\.]+)/i)[1];
}
```
