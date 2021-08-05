# Git 规范

## Commit 格式

每次提交，Commit message 都包括三个部分：

`<type>(<scope>): <subject>`

例如 `feat(分析页): 增加雷达图`

**（1）type**

`type`用于说明 commit 的类别，只允许使用下面7个标识。

- feat：新功能（feature）
- fix：修补bug
- docs：文档（documentation）
- style： 格式（不影响代码运行的变动）
- refactor：重构（即不是新增功能，也不是修改bug的代码变动）
- test：增加测试
- chore：构建过程或辅助工具的变动

**（2）scope**

`scope`用于说明 commit 影响的范围，前端可以是对应的页面，后端可以是数据层、控制层、视图层等等，视项目不同而不同。

**（3）subject**

`subject`是 commit 目的的简短描述，不超过50个字符，统一使用中文描述，结尾不加句号。

