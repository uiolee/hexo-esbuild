# hexo-esbuild

Minify JavaScripts, CSS files via [esbuild](https://esbuild.github.io) [Transformer](https://esbuild.github.io/api/#transform).

## Install

```bash
pnpm add hexo-esbuild

# npm i hexo-esbuild
```

## Configuration

### Default Configuration

> Defined in [src/default_config.ts](src/default_config.ts)

```yaml
hexo_esbuild:
  enable: true
  js:
    enable: true
    after_render: "js" # hexo filter hook. support https://hexo.io/api/filter#after-render
    priority: 999 # hexo filter priority. Lower priority means that it will be executed first
    exclude:
      - "**.min.js"
    esbuildTransformOptions: # the esbuild transform options. https://esbuild.github.io/api/#transform
      loader: "js"
      minify: true
      logLevel: "warning"
  css:
    enable: true
    after_render: "css"
    priority: 999
    exclude:
      - "**.min.css"
    esbuildTransformOptions:
      loader: "css"
      minify: true
      logLevel: "warning"
```
