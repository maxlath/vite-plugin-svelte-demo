Demo for https://github.com/sveltejs/vite-plugin-svelte/pull/1166

## Reproduce the issue
```sh
git clone https://github.com/maxlath/vite-plugin-svelte-demo
cd vite-plugin-svelte-demo
pnpm install
pnpm start
```
and in another terminal
```sh
curl http://localhost:5173/
```
results in the following error in the vite logs:
```
2:55:26 PM [vite] (client) Pre-transform error: :5:2 Expected a valid CSS identifier
https://svelte.dev/e/css_expected_identifier

- Did you forget to add a lang attribute to your style tag?
- Did you forget to add a style preprocessor? See https://github.com/sveltejs/vite-plugin-svelte/blob/main/docs/preprocess.md for more information.
- Did you forget to add a scss preprocessor? See https://github.com/sveltejs/vite-plugin-svelte/blob/main/docs/preprocess.md for more information.
  Plugin: vite-plugin-svelte
  File: /tmp/bla/vite-plugin-svelte-demo/src/App.svelte:5:2
   3 |
   4 |  <style lang="scss">
   5 |    $some-color: red;
          ^
   6 |    .h1{
   7 |      color: $some-color;
```

Note the **"Did you forget to add a lang attribute to your style tag?"** message, despite having `<style lang="scss">`
