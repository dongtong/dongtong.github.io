
# 发布SvelteKit项目到Github Pages

## 安装 SvelteKit

```sh
npm create svelte@latest my-app
```

## 安装 @sveltejs/adapter-static 和 gh-pages. 

```sh
npm i -D @sveltejs/adapter-static gh-pages
```

## 更新 svelte.config.js，替换adapter-auto成adaptor-static.

```js
import adapter from '@sveltejs/adapter-static';
```

## 创建一个+layout.js

在 `src/routes/+layout.js` 里面添加以下代码

```js
export const prerender = true;
```

## 添加脚本到package.json. 

```json
"gh-pages": "npm run build && npx gh-pages -d build"
```

## 发布

今后的发布之需要 `npm run gh-pages`.

## 针对Tailwind CSS/Postcss的.nojekyll 文件处理

如果你使用postcss(例如Tailwind),你需要添加一个**空的`.nojekyll`**文件到`gh-pages`分支

