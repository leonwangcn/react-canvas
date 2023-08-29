# @liangshen/react-canvas

使用React的方式来编写Canvas, 运行环境只需要支持Canvas即可, 不再需要完整的浏览器的Dom Bom环境.

## 环境

node v16+


## 安装

如下俩种方式

1. 建议使用create-react-app的方式构建应用，命令如下

```
npx create-react-app my-app --template @liangshen/react-canvas 
```

2. 也可以在已有项目中进行安装, 使用 @liangshen/react-canvas 替换 react-dom 库来做渲染。

```
npm i @liangshen/react-canvas -S
```

## 使用方法

index.tsx
```tsx
import React from "react";
import ReactCanvas from "@liangshen/react-canvas";
import App from "./App";

// 如果是浏览器环境 获取到index.html中的Canvas对象, 或者在这里创建一个Canvas
const canvas = document.getElementsByTagName('canvas')[0];
ReactCanvas.render(canvas,
    <React.StrictMode>
        <App />
    </React.StrictMode>
);
```

html中添加一个Canvas元素, 或者在js中动态创建一个Canvas

index.html
```html
<!DOCTYPE html>
<html>
    <body>
        <canvas id="canvas" width="800" height="400"></canvas>
    </body>
</html>
```

App.tsx
```tsx
import {Text} from '@liangshen/react-canvas';
export const App = () => <>
    <Text value={'测试一下'}></Text>
</>
```

## @liangshen/react-canvas 提供的一些组件

* Text 文本
* Image 图片类似html中的`img`
* View 类似html中的`div`
* ScrollView 类似html中可滚动的`div`

## 打包

如果使用了Layout插件的方式, 执行
```
npm run build:lib:layout-plugin
```

### 使用到了minigame-canvas-engine做为Canvas的渲染库, 还是特别感谢下作者🙏


