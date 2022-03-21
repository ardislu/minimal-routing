# minimal-routing

Demo website for the minimum JavaScript required to implement client-side routing.

## Web server configuration

This demo website assumes that the web server has been configured to serve `index.html` on all routes **EXCEPT** for the special path: `/errors/NotFound`. For `/errors/NotFound`, the web server must respond with a `404 Not Found` error and the file `/errors/404.html`.

Note: this file path is intentionally nested in a folder because some static site hosts (like [Cloudflare Pages](https://developers.cloudflare.com/pages/platform/serving-pages)) use a top-level `404.html` page as a flag to override the desired behavior of serving `index.html` on all other routes.

The desired behavior can be replicated locally using the npm package [local-web-server](https://www.npmjs.com/package/local-web-server):

```
ws --spa index.html --rewrite '/errors/(.*) -> /errors/404.html'
```
