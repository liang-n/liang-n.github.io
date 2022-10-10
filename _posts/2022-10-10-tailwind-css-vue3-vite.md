---
layout: post
title: "在 Vue 3 + Vite 项目中安装 Tailwind CSS"
subtitle: "Install Tailwind CSS in Vue3 + Vite project"
date: 2022-10-10 15:38:00
author: "Liang"
catalog: true
header-style: img
header-img: "img/in-post/tailwind-css-vue3-vite/img.png"
header-mask: 0.6
tags:
  - vue3
  - vite
  - css
  - tailwindcss
---

### 初始化 Tailwind CSS

首先，使用 NPM 安装 Tailwind 以及其它依赖项:

```ssh
npm install -D tailwindcss@latest postcss@latest autoprefixer@latest
```

安装后，使用 `npx` 命令生成 `tailwind.config.js` 和 `postcss.config.js` 配置文件：

```
npx tailwindcss init -p
```

接下来，先配置 Tailwind 来移除生产环境下没有使用到的样式声明：

```js
// tailwind.config.js

module.exports = {
  content: ["./index.html", "./src/**/*.{vue,js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

在 `tailwind.config.js` 文件中，配置 `content` 选项指定所有的 `pages` 和 `components` 文件，使得 Tailwind 可以在生产构建中对未使用的样式进行摇树优化。

然后，创建 `./src/index.css` 文件并填充以下内容：

```css
/* ./src/index.css */

@tailwind base;
@tailwind components;
@tailwind utilities;
```

最后，将 `./src/index.css` 文件导入到 `./src/main.js` 文件中：

```js
// src/main.js

import { createApp } from "vue";
import App from "./App.vue";
import "./index.css";

createApp(App).mount("#app");
```

现在，运行 `npm run dev`, Tailwind CSS 就可以在您的 Vue 3 and Vite 项目中使用了，并且还会在构建时移除未使用的 CSS，以获得最佳性能。

### Tailwind CSS + VS Code 代码提示

为了更加流畅的使用体验，我们还需要在 VS Code 中再安装 [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) 插件获得丰富的 Tailwind CSS 代码提示。
