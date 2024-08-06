# JS

## Methods

### String

#### 'replace'

- syntax:

  - `string.replace(pattern, replacement)`

- description:

  - return a new string with matched pattern replaced by replacement
  - pattern: the pattern to replace
  - replacement: the replacement to replace the pattern with can be a string or a Regular Expression

  - example:

```js
const url = 'https://github.com/';
const replaced = url.replace('https://', 'http://');
console.log(replaced);
// expected output: "http://github.com/"
```

#### 'split'

- syntax:
  - `string.split(separator)`
  - `string.split(separator, limit)`
- description:

  - splits a string into an array of substrings

- example:

```js
const url = 'https://github.com/';
const matches = url.split('/');
console.log(matches);
// expected output: ["https:", "", "github.com", ""]
```

#### 'match'

- syntax:
  - `string.match(regularExpression)`
- description:
  - returns an array of the matches
    - index 0: the full match
    - index 1: the first capture group
    - index 2: the second capture group
    - ...
  - regular expression
- example:

```js
const url = 'https://github.com/';
const matches = url.match(/(?:http(?:s)?:\/\/)?(?:w{3}\.)?([^\.]+)/i);
console.log(matches);
// expected output: ["https://github.com/", "github"]
```
