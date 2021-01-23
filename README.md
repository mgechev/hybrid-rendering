# Hybrid Rendering in Angular

Starting from v11.1 Angular enables hybrid rendering by default for Universal projects.

## Usage

```
$ yarn prerender
$ node dist/hybrid-rendering/server/main.js
$ open http://localhost:4000
```

Once you start the Universal server it will:
- Serve the route `/about` from the prerendered at build-time page `dist/hybrid-rendering/browser/about/index.html`
- Server-side render `/` and `/user/:id`

By default, the command `yarn prerender` will:
- Discover all the routes using [guess-parser](https://npmjs.org/package/guess-parser)
- Prerender all the non-parametrized routes excluding `/` and store them under `dist/[app]/browser`
- Output a server under `dist/[app]/server/main.js` which will SSR the rest at runtime

## License

MIT
