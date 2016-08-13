# Routing

- Never expose technical details in URLs

## Routes

### Regex

#### Supported Regex metacharacters

> `+`, `?`, `*`, `(`, and `)`

#### Route paths using regular expressions
- **/user** and **/username** `app.get('/user(name)?', (req, res) => res.render('user'))`
- multiple `a` eg. `/khaan` and `/khaaaan` support both with `app.get('/khaa+n', (req, res) => res.render('khaaan'))`

To use the full power of Regex for your routes

```js
app.get(/crazy|mad(ness)?|lunacy/, (req, res) => res.render('madness'))`
```

## Route parameters

eg. `:name` -> `/staff/:name` -> `req.params.name`

## Subdomains
- To handle subdomains in the same server suse npm package `vhost`
- [ ] add vhost code from pg 160



## articles

- [Tim Berner Lee, Cool URIs](https://www.w3.org/Provider/Style/URI.html)

