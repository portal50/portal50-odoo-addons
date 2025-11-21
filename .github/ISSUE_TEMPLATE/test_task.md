name: "外包测试任务"
about: "用于多个外包人员的基础 Odoo 技能测试与 PR 流程验证"
title: "[Test] Portal50 外包测试任务 - 请填写你的名字"
labels: test-task
assignees: ""
---

# Portal50 / Intracity AI — 外包测试任务

此任务用于验证外包是否具备基础 Odoo 模块开发能力，以及是否可以正确使用 GitHub PR 流程。
多个外包可同时使用此模板，每人需创建一个独立 Issue。

---

## 任务内容

请在 `addons/` 目录下创建一个新模块：

```
portal50_test_module
```

模块要求如下：

### 1. 创建模型
模型名：`portal50.test.model`

字段：
- `name` (Char)
- `description` (Text)

### 2. 创建菜单
在 Settings 下新增菜单路径：

```
Settings > Portal50 Test > Test Records
```

### 3. 创建视图
为 `portal50.test.model` 创建：

- tree 视图（至少显示 name）
- form 视图（包含 name 和 description）

### 4. 模块可独立安装

必须能执行：

```
odoo -i portal50_test_module -d testdb
```

且不报错。

---

## 代码提交流程（GitHub PR）

1. Fork 仓库  
   https://github.com/IntracityAI/portal50-odoo-addons

2. 创建开发分支：

```
git checkout -b feature-test-module
```

3. 完成开发后执行：

```
git add .
git commit -m "测试任务：portal50_test_module 完成"
git push -u origin feature-test-module
```

4. 在 GitHub 发起 Pull Request（PR）

PR 必须包含：
- 完成说明
- 模块安装截图
- tree 和 form 视图截图

---

## 注意事项

- 所有代码必须放在 `addons/portal50_test_module/` 下  
- 禁止修改 Odoo 核心文件  
- 模块结构必须符合 Odoo 官方标准  
