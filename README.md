<h1 align='center'>HecateJS</h1>

<p align='center'>Javascript Library and CLI for <a href='https://github.com/mapbox/Hecate'>Hecate</a>, the persistent, mutable data store focused on GeoJSON first interchange</p>

## General Usage

### Installation

**JS Library**

```sh
yarn add '@mapbox/hecatejs'
```

**CLI**

```sh
yarn global add `@mapbox/hecatejs'
```

### Instantiation

**JS Library**

```js
const Hecate = require('@mapbox/hecatejs');

const hecate = new Hecate({
    url: 'example.com/hecate',
    port: 8000
});
```

**CLI**

The CLI tool must be provided the URL to connect to for each subcommand.
This can be accomplished by manually setting the URL/Port or by letting it
query for Hecate resources on a signed in AWS account.


The --url/port or --stack options must be provided for every subcommand
but are omitted in this guide for clarity.

```sh
./cli.js --url 'example.com' --port 8000
```

```sh
./cli.js --stack buildings
```
_Would find the AWS ELB for a CloudFormation stack called `hecate-internal-buildings`_

### Registering a User Account

By default, most hecate instances are fairly open and will allow a wide range
of operations without authentication. Editing however, and querying on boxes with
tighter access restrictions will require registering a new account.

**JS Library**

```js
const Hecate = require('@mapbox/hecatejs');

const hecate = new Hecate({
    url: 'example.com/hecate',
    port: 8000
});

hecate.register({
    username: 'ingalls',
    password: 'yeaheh',
    email: 'ingalls@protonmail.com'
}, (err, res) => {
    if (err) throw err;
});
```

**CLI**

```sh
./cli.js register
```

### List Server Custom Authentication

See the [custom authentication](https://github.com/mapbox/Hecate#custom-authentication) section of the Hecate readme for more info

**JS Library**

```js
const Hecate = require('@mapbox/hecatejs');

const hecate = new Hecate({
    url: 'example.com/hecate',
    port: 8000
});

hecate.auth(null, (err, res) => {
    if (err) throw err;
});
```

**CLI**

```sh
./cli.js auth
```

### Query Data

To Be Written

### List JSON Schema Requirements

A hecate instance can optionally require that all the properties of GeoJSON features stored by the server
conform to a given JSON Schema. Failure to meet this schema will result in the import being rejected.


**JS Library**

```js
const Hecate = require('@mapbox/hecatejs');

const hecate = new Hecate({
    url: 'example.com/hecate',
    port: 8000
});

hecate.schema(null, (err, res) => {
    if (err) throw err;
});
```

**CLI**

```sh
./cli.js schema
```

### Import Data

To Be Written

### Generate Reversion Deltas

To Be Written

To Be Written
