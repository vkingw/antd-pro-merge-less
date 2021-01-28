## antd-pro-merge-less-ng

使用方式：

```js
const genCss = require('antd-pro-merge-less');

genCss(
  'C:/GitHub/ant-design',
  [
    {
      theme: 'dark',
      fileName: './.temp/dark.css',
    },
    {
      fileName: './.temp/mingQing.css',
      modifyVars: {
        '@primary-color': '#13C2C2',
      },
    },
  ],
  {
    // 是否压缩css
    min: false,
    // css module
    isModule: false,
    // 忽略 antd 的依赖,用于打包 antd 自己的依赖
    ignoreAntd: true,
    // 忽略 pro-layout 的依赖
    ignoreProLayout: true,
    // 不使用缓存
    cache: false,
    filterFileLess: filename => boolean,
    extraLibraries: []
  },
);
```
生成的css文件会注释掉 ***url\(.*assets*** 相关内容，解决图片加载问题
