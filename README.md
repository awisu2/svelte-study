# svelte study

summary of my svelte study

- [Introduction / Basics • Svelte Tutorial](https://svelte.dev/tutorial/basics)
- [Docs • Svelte](https://svelte.dev/docs)

*NOTE*

- about sapper: sapper's successor is Sveltekit, as stated in the documentation. [Docs • Sapper](https://sapper.svelte.dev/docs)

## Todo

- [] [SvelteKit • The fastest way to build Svelte apps](https://kit.svelte.dev/)

## 自分の環境で使う方法

現時点で vite-plugin-svelte, rollup-plugin-svelte, svelte-loader をサポートしているとのこと

[Introduction / Making an app • Svelte Tutorial](https://svelte.jp/tutorial/making-an-app)

### 各種ビルド

- rollup-plugin-svelte: rollup コマンドに対応したビルド方法 ([doc](./rollup-svelte/README.md))

## docs

- [tips](./docs/tips.md): 知っておくと便利なこと
- [problems](./docs/problems.md): 時折当たる問題メモ
- [Svelte for VS Code \- Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode)

## contents

- [rollup-svelte](./rollup-svelte) : rollup-plugin-svelte を利用して動作をさせてみました
  - rolluup: node.js でのビルド環境
- [sveltekit](./sveltekit) : svelte の開発補助パッケージ sveltekit を利用して動作をさせてみました。vite によってビルド及び動作
- [with webpack](https://github.com/awisu2/webpack-study/tree/main/svelteWithTypescript): webpack + svelte + typescript

## self svelte components

- [lasyImageOrder](./components/LasyImageOrder.svelte): lasy load image on order
- [sidebarMover](./components/sidebarMover.svelte): resize the side area with the mouse
