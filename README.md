# README

This repo demonstrates a problem using StimulusReflex (pre8) and the newly released Stimulus 3.1, at least with my particular setup using esbuild.

On the main branch, Stimulus 3.1 is installed. Clone this repo and run `bin/dev` and you should see an error that looks like this:

```
16:05:34 js.1   | yarn run v1.22.17
16:05:34 js.1   | $ esbuild app/javascript/*.* --bundle --sourcemap --outdir=app/assets/builds --public-path=assets --watch
16:05:34 js.1   | ✘ [ERROR] Could not resolve "stimulus"
16:05:34 js.1   |
16:05:34 js.1   |     app/javascript/controllers/application.js:1:28:
16:05:34 js.1   |       1 │ import { Application } from "stimulus"
16:05:34 js.1   |         ╵                             ~~~~~~~~~~
16:05:34 js.1   |
16:05:34 js.1   |   The path "." is not exported by package "stimulus":
16:05:34 js.1   |
16:05:34 js.1   |     node_modules/stimulus/package.json:15:13:
16:05:34 js.1   |       15 │   "exports": {
16:05:34 js.1   |          ╵              ^
16:05:34 js.1   |
16:05:34 js.1   |   You can mark the path "stimulus" as external to exclude it from the bundle, which will remove this error.
16:05:34 js.1   |
16:05:34 js.1   | ✘ [ERROR] Could not resolve "stimulus"
16:05:34 js.1   |
16:05:34 js.1   |     node_modules/stimulus_reflex/javascript/stimulus_reflex.js:1:27:
16:05:34 js.1   |       1 │ import { Controller } from 'stimulus'
16:05:34 js.1   |         ╵                            ~~~~~~~~~~
16:05:34 js.1   |
16:05:34 js.1   |   The path "." is not exported by package "stimulus":
16:05:34 js.1   |
16:05:34 js.1   |     node_modules/stimulus/package.json:15:13:
16:05:34 js.1   |       15 │   "exports": {
16:05:34 js.1   |          ╵              ^
16:05:34 js.1   |
16:05:34 js.1   |   You can mark the path "stimulus" as external to exclude it from the bundle, which will remove this error.
16:05:34 js.1   |
16:05:34 js.1   | 2 errors
```

Switch to the stimulus-3.0 branch (or just `yarn remove stimulus && yarn add stimulus@3.0.1` against the main branch) and see that `bin/dev` runs without errors.
