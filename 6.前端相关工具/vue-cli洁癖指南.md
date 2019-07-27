# vue-cli 配合vscode的洁癖指南

1. 安装时，选择babel+eslint
在这里，一定要选择第一项：`babel + eslint`，这两个是必不可少的。我见到有些人嫌eslint麻烦，居然在项目建立好之后手工把eslint关掉的，简直无语。

2. 安装vetur插件[vscode插件]

3. 安装@vue/prettier插件
```
yarn add -D @vue/eslint-config-prettier
```

4. 配置eslint配置
然后在package.json或者.eslintrc.js或者其它什么你设置eslint的地方，给它加上：
```
"extends": [
      "plugin:vue/essential",
      "eslint:recommended",
      "@vue/prettier"
],
```

5. 对prettier做设置
在项目的根目录下创建一个.prettierrc.js文件，然后在其中加入：
```
module.exports = {
  semi: false,
  singleQuote: true
}
```

6. 添加.vscode
在.vscode文件夹里增加settings.json文件,文件里添加以下代码：
```
{
  "eslint.autoFixOnSave": true,
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    {
      "language": "vue",
      "autoFix": true
    }
  ],
}
```

