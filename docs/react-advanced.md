# 代碼分割

## 打包

多數的 React 應用均會使用到 Webpack, Browserify 工具建構,<br>
打包是將多個獨立的文件合併到單獨文件的過程,<br>
最終整個應用可一次性加載.<br>

有些工具如 Create React App, Next.js, Gatsby 或類似的類似工具,<br>
內部已整合 Webpack 配置可直接進行打包工作.

## import

在 ES6,<br>
最佳透過代碼分割的方法是透過 import(),<br>
這類語法目前並不是標準語法,<br>
需要透過如 Create React App 或是 Next.js 協助轉變配置.

```
import { add } from './math';

console.log(add(16, 26));
```

## React.lazy

透過 React.lazy,<br>
我們可輕易地將組件動態載入.

```
import React, { Component } from 'react'; 
import OtherComponent from './OtherComponent';

class MyComponent extends Component
{
  render() {
    return (
      <div>
        <OtherComponent />
      </div>
    )
  }
}
```

## Suspense

在 MyComponent 完成後,<br>
包含 OtherComponent 模塊尚未加載完成時,<br>
我們可以利用 Suspense 組件為該組件降級.

Root.js

```
import React, { Component, lazy, Suspense } from 'react';

const LazyComponent = lazy(() => {
  return new Promise(resolve => {
    setTimeout(() => resolve(import("./LazyComponent")), 2000);
  });
});

class Root extends Component {
  render() {
    return (
      <div>
        <Suspense fallback={<div>Loading...</div>}>
          <section>
            <LazyComponent />
          </section>
        </Suspense>
      </div>
    );
  }
}

export default Root;
```

LazyComponent.js

```
import React, { Component } from 'react';

class LazyComponent extends Component
{
  render () {
    return <h1>HELLO WORLD</h1>;
  }
}

export default LazyComponent;
```

## 異常處理

如果模塊加載失敗,<br>
可以利用異常處理來面對這些情況.

