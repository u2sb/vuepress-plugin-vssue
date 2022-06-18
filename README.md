> 当前版本仅适配 vuepress 1.x

## 演示

- [U2SB](https://github.com/u2sb/www.u2sb.com)
- [xxwhite](https://github.com/MonoLogueChi/blog.xxwhite.com)

## 安装

```
yarn add vuepress-plugin-vssue-global
```

## 配置

配置完全继承 [@vssue/vuepress-plugin-vssue](https://vssue.js.org/zh/guide/vuepress.html)，增加配置项如下：

- title: vssue title，支持 ejs 模板
- needComments: 默认是否需要评论区，当配置为 false 时，需文章 frontmatter 添加`comments: true`才会开启评论区。

```js
module.exports = {
  plugins: [
    [
      "vuepress-plugin-vssue-global",
      {
        platform: "github",
        title: "[Comment]<%- frontmatter.title %>",
        needComments: true,
        // 其他的 Vssue 配置
        clientId: "",
        clientSecret: "",
        owner: "",
        repo: "",
      },
    ],
  ],
};
```

## 开启和关闭评论

每篇文章单独控制评论区，需配置 frontmatter

关闭评论区：

```yml
comments: false
```

开启评论区：

```yml
comments: true
```
