# [0002. 25.04](https://github.com/Tdahuyou/TNotes.change-log/tree/main/notes/0002.%2025.04)

<!-- region:toc -->

- [1. 🗓 25.04.30](#1--250430)
- [2. 🗓 25.04.29](#2--250429)

<!-- endregion:toc -->

## 1. 🗓 25.04.30

- electron
  - 完成 `TNotes.electron` 仓库的初始化
- nodejs
  - 移除 vitepress 导入代码片段的语法 `<<< @/filepath`

## 2. 🗓 25.04.29

- TNotes
  - 知识库 `TNotes.xxx` 汇总到 TNotes 中，以便查阅
    - 备注：
    - 直接在 `update.js` 中做了修改，还存在一些问题：
      - 代码优化
      - 有些笔记内容 README.md 依赖 vitepress 特性，比如动态加载文件 `<<< ./demos/1/1.cjs` 等等，这意味着在搬运的时候需要连同 demos 目录一起搬运。
    - 根知识库 TNotes
      - 现在的效果：
        - ![图 0](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2025-05-10-23-47-06.png)
        - 现在已经可以在根知识库中直接访问所有知识库的笔记了。
      - 新增：
        - 如果新增一个知识库，需要在根知识库 TNotes 中配置一下 sidebar，将新的知识库给引入到目录中。新的知识库的配置文件中需要加上 `"rootDocsSrcDir": "../\_/docs/src",` 配置，值为根知识库的相对路径。
      - 改进：
        - 还有很多地方有待优化，根知识库中的一些全局文章也还没整理，还有一些旧版的知识库没有迁移。
  - 在知识库的菜单项中插入 `TODO.md`，以便查阅更新记录
  - 每篇笔记结尾的更新时间，加上 `👣 xxxx`
  - `tn:new` 命令创建的笔记配置文件 `.tnotes.json` 中添加 id 字段
  - 每篇笔记的评论 ID 引用当前笔记配置文件 `.tnotes.json` 中的 ID 字段
  - 每篇笔记生成唯一的 id，丢到 `.tnotes.json` 中
  - 每个知识库生成唯一的 id，丢到 `.tnotes.json` 中
