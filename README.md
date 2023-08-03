# Minimal reproduction of Nuxt/Nitro bug

## How to reproduce

1. Checkout this repo
2. Run `npm i`
3. npm `npm run build`
4. Observe nitro build fails with error

Output:

```
$ npm run build

> build
> nuxt build

Nuxi 3.6.5                                                                                                                                      7:11:12 pm
Nuxt 3.6.5 with Nitro 2.5.2                                                                                                                     7:11:12 pm
ℹ Building client...                                                                                                                           7:11:14 pm
ℹ vite v4.3.9 building for production...                                                                                                       7:11:14 pm
ℹ ✓ 87 modules transformed.                                                                                                                    7:11:15 pm
ℹ .nuxt/dist/client/manifest.json                   1.59 kB │ gzip:  0.31 kB                                                                   7:11:16 pm
ℹ .nuxt/dist/client/_nuxt/error-500.aa16ed4d.css    1.95 kB │ gzip:  0.74 kB                                                                   7:11:16 pm
ℹ .nuxt/dist/client/_nuxt/error-404.23f2309d.css    3.63 kB │ gzip:  1.12 kB                                                                   7:11:16 pm
ℹ .nuxt/dist/client/_nuxt/entry.bbc96c86.css       12.13 kB │ gzip:  2.49 kB                                                                   7:11:16 pm
ℹ .nuxt/dist/client/_nuxt/error-500.e3dce893.js     1.88 kB │ gzip:  0.99 kB                                                                   7:11:16 pm
ℹ .nuxt/dist/client/_nuxt/error-404.ffddabaa.js     6.53 kB │ gzip:  2.90 kB                                                                   7:11:16 pm
ℹ .nuxt/dist/client/_nuxt/entry.0d4b01b9.js       198.09 kB │ gzip: 55.54 kB                                                                   7:11:16 pm
ℹ ✓ built in 2.00s                                                                                                                             7:11:16 pm
✔ Client built in 2007ms                                                                                                                       7:11:16 pm
ℹ Building server...                                                                                                                           7:11:16 pm
ℹ vite v4.3.9 building SSR bundle for production...                                                                                            7:11:16 pm
ℹ ✓ 44 modules transformed.                                                                                                                    7:11:17 pm
ℹ .nuxt/dist/server/_nuxt/entry-styles.6cce99fb.mjs             0.08 kB                                                                        7:11:17 pm
ℹ .nuxt/dist/server/_nuxt/error-404-styles.cf00f4cc.mjs         0.15 kB                                                                        7:11:17 pm
ℹ .nuxt/dist/server/_nuxt/error-500-styles.a001b7ed.mjs         0.15 kB                                                                        7:11:17 pm
ℹ .nuxt/dist/server/styles.mjs                                  0.46 kB                                                                        7:11:17 pm
ℹ .nuxt/dist/server/_nuxt/island-renderer-f70c2cce.js           1.05 kB │ map:   1.40 kB                                                       7:11:17 pm
ℹ .nuxt/dist/server/_nuxt/error-500-styles-1.mjs-0a86f27a.js    2.17 kB │ map:   0.12 kB                                                       7:11:17 pm
ℹ .nuxt/dist/server/_nuxt/error-500-f2715e45.js                 3.02 kB │ map:   3.78 kB                                                       7:11:17 pm
ℹ .nuxt/dist/server/_nuxt/error-404-styles-1.mjs-6ef6e240.js    3.86 kB │ map:   0.12 kB                                                       7:11:17 pm
ℹ .nuxt/dist/server/_nuxt/error-404-a8f489e4.js                 9.67 kB │ map:  18.91 kB                                                       7:11:17 pm
ℹ .nuxt/dist/server/_nuxt/entry-styles-1.mjs-bfad4fc1.js       12.38 kB │ map:   0.11 kB                                                       7:11:17 pm
ℹ .nuxt/dist/server/server.mjs                                121.13 kB │ map: 167.96 kB                                                       7:11:17 pm
ℹ ✓ built in 991ms                                                                                                                             7:11:17 pm
✔ Server built in 1000ms                                                                                                                       7:11:17 pm
✔ Generated public .output/public                                                                                                        nitro 7:11:17 pm
ℹ Building Nitro Server (preset: node-server)                                                                                            nitro 7:11:17 pm

 ERROR  TypeError: Cannot read properties of undefined (reading 'pkgName')                                                                nitro 7:11:22 pm


undefined


 ERROR  Cannot read properties of undefined (reading 'pkgName')                                                                                 7:11:22 pm

  at node_modules/nitropack/dist/shared/nitro.7a525996.mjs:609:32
  at Array.map (<anonymous>)
  at node_modules/nitropack/dist/shared/nitro.7a525996.mjs:607:38
  at Array.flatMap (<anonymous>)
  at findPackageParents (node_modules/nitropack/dist/shared/nitro.7a525996.mjs:606:26)
  at Object.buildEnd (node_modules/nitropack/dist/shared/nitro.7a525996.mjs:629:59)
  at async Promise.all (index 0)
  at async PluginDriver.hookParallel (node_modules/rollup/dist/es/shared/node-entry.js:25264:9)
  at async node_modules/rollup/dist/es/shared/node-entry.js:26501:9
  at async catchUnfinishedHookActions (node_modules/rollup/dist/es/shared/node-entry.js:25702:16)
```
