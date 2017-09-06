# keyv-postgres-shrink [<img width="100" align="right" src="https://rawgit.com/lukechilds/keyv/master/media/logo.svg" alt="keyv">](https://github.com/lukechilds/keyv)

Fork of the PostgreSQL storage adapter for [Keyv](https://github.com/lukechilds/keyv). Supports removing expired data via a `shrink` function.

Requires Postgres 9.5 or newer for `ON CONFLICT` support to allow performant upserts. [Why?](https://stackoverflow.com/questions/17267417/how-to-upsert-merge-insert-on-duplicate-update-in-postgresql/17267423#17267423)

## Install

```shell
npm install --save keyv keyv-postgres-shrink
```

## Usage

```js
const Keyv = require('keyv');
const KeyvStorageAdapter = require('keyv-postgres-shrink');

const storage = new KeyvStorageAdapter({
  uri: 'postgresql://user:pass@localhost:5432/dbname',
  table: 'myappcache'
});

const keyv = new Keyv({
  store: storage,
  namespace: 'myapp'
});

keyv.on('error', handleConnectionError);
```


## License

MIT © MySidesTheyAreGone

MIT © Luke Childs
