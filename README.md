# rs_quotes
Using jQuery with Axios to get individual Ron Swanson quotes from an API

### Example Image

![example]

### API

[Ron Swanson quotes](http://ron-swanson-quotes.herokuapp.com/v2/quotes)

### Libraries
- [Axios](https://cdnjs.cloudflare.com/ajax/libs/axios/0.18.0/axios.min.js)
- [jQuery](https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js)

### Script

- with each click event, `jquery` replaces the button text with a Ron Swanson quote.
- `axios` backend gets the text string from the API.

```js
$('#get_quote').click(function() {
  axios.get("http://ron-swanson-quotes.herokuapp.com/v2/quotes")
  .then(function(res) {
    $('button').text(res.data);
  })
  .catch(function(error) {
    console.log(error);
  })
});
```

### Script (Alternate)

```js
  $('#get_quote').click(function() {
    fetch("http://ron-swanson-quotes.herokuapp.com/v2/quotes")
    .then(res => res.json())
    .then((data) => {
      this.friends = data
      $('button').text(data);
    })
  });
```

[example]: example.png "Example | Ron Swanson Quotes"
