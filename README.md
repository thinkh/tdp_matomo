tdp_matomo [![Phovea][phovea-image]][phovea-url] [![NPM version][npm-image]][npm-url] [![Dependency Status][daviddm-image]][daviddm-url]
=====================

Matomo tracking for TDP applications based on provenance graph commands.

Configuration
------------

The tracking starts when a URL to a Matomo backend is set in the `config.js`.
The site ID corresponds with the Matomo site.

```js
{
  "matomo": {
    "url": "https://matomo.my-example-domain.com/", // matomo url with a trailing slash
    "site": "1"
  }
}
```

### Provenance Commands

The tracked default provenance commands from [tdp_core](https://github.com/datavisyn/tdp_core) are defined in [actions.ts](./src/actions.ts).

Add a list of custom events when initializing the tracking:

```ts
const trackableActions: ITrackableAction[] = [
  // id = phovea extension id
  {id: 'targidCreateView', event: {category:'view', action: 'create'}},
];
trackApp(app, trackableActions);
```


Installation
------------

```
git clone https://github.com/datavisyn/tdp_matomo.git
cd tdp_matomo
npm install
```

Testing
-------

```
npm test
```

Building
--------

```
npm run build
```



***

<a href="https://caleydo.org"><img src="http://caleydo.org/assets/images/logos/caleydo.svg" align="left" width="200px" hspace="10" vspace="6"></a>
This repository is part of **[Phovea](http://phovea.caleydo.org/)**, a platform for developing web-based visualization applications. For tutorials, API docs, and more information about the build and deployment process, see the [documentation page](http://phovea.caleydo.org).


[phovea-image]: https://img.shields.io/badge/Phovea-Client%20Plugin-F47D20.svg
[phovea-url]: https://phovea.caleydo.org
[npm-image]: https://badge.fury.io/js/tdp_matomo.svg
[npm-url]: https://npmjs.org/package/tdp_matomo
[daviddm-image]: https://david-dm.org/datavisyn/tdp_matomo/status.svg
[daviddm-url]: https://david-dm.org/datavisyn/tdp_matomo
