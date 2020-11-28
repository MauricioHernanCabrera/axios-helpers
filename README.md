## Helpers

### API Data
helpers for get, post, delete, patch and put http methods

```js
// bad
const exampleCreated = await axios.post('/examples', data)
console.log(exampleCreated.data)
  
// good
const exampleCreated = await axios.$post('/examples', data)
console.log(exampleCreated)
```


### Set Token

```js
// bad
axios.defaults.headers.common['Authorization'] = token
  
// good
axios.setToken(token)
```

### Set Bearer token
```js
// bad
axios.defaults.headers.common['Authorization'] = `Bearer ${token}`
  
// good
axios.setToken(token, 'Bearer')
```

### Set Base URL
```js
// bad
axios.defaults.baseURL = 'https://example.com'

// good
axios.setBaseURL('https://example.com');
```



### Set header
```js
// bad
axios.defaults.headers.common['Content-Type'] = 'application/json'
  
// good
axios.setHeader('Content-Type', 'application/json')
```



### Basic example
```js
const axiosHelpers = require('axios-helpers');
const axios = axiosHelpers(require('axios'));
axios.setBaseURL('https://example.com');

const createExample = async (data) => {
  const exampleCreated = await axios.$post('/examples', data)
  console.log(exampleCreated)
}
```