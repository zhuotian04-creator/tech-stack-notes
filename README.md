# Tech Stack Notes

这是一个用于整理不同技术栈学习笔记、开发环境配置、项目模板和常用命令的仓库。

本仓库主要服务于个人学习、项目开发和后续知识复盘，内容会持续更新。

---

## 仓库定位

这个仓库不放具体业务项目源码，主要用于存放：

- 技术栈学习笔记
- 软件安装与环境配置教程
- 常用开发命令
- 项目初始化流程
- 常见报错与解决方案
- 可复用的项目模板说明
- 面向学弟学妹的教学文档

---

## 目录结构

```text
tech-stack-notes/
├── README.md
├── 00-Git-GitHub/
│   ├── Git基础命令.md
│   ├── GitHub推送流程.md
│   └── 常见错误处理.md
│
├── 01-VSCode/
│   ├── VSCode基础配置.md
│   ├── VSCode配置文件Profiles.md
│   ├── VSCode配置Python环境.md
│   └── VSCode配置STM32环境.md
│
├── 02-Python/
│   ├── Python安装教程.md
│   ├── Python虚拟环境venv.md
│   ├── pip常用命令.md
│   └── requirements依赖管理.md
│
├── 03-Django/
│   ├── Django项目创建流程.md
│   ├── Django目录结构说明.md
│   ├── Django连接数据库.md
│   └── Django后端接口开发.md
│
├── 04-Vue3/
│   ├── Vue3项目创建.md
│   ├── Vue3目录结构.md
│   ├── Vue3组件开发.md
│   └── Vue3接口请求.md
│
├── 05-uni-app/
│   ├── uni-app项目创建.md
│   ├── 微信小程序配置.md
│   ├── uni-app请求后端接口.md
│   └── uni-app常见问题.md
│
├── 06-STM32/
│   ├── STM32CubeMX到VSCode开发流程.md
│   ├── STM32CubeProgrammer烧录流程.md
│   ├── Keil5开发流程.md
│   └── STM32常见报错处理.md
│
├── 07-Docker/
│   ├── Docker安装教程.md
│   ├── Docker常用命令.md
│   └── Docker部署Django项目.md
│
└── templates/
    ├── django-template/
    ├── vue3-template/
    ├── uniapp-template/
    └── python-script-template/
## 目录说明

|目录|内容|
|---|---|
|`00-Git-GitHub`|Git 基础命令、GitHub 推送流程、分支管理、常见错误|
|`01-VSCode`|VS Code 安装、插件配置、Profile 配置、不同语言开发环境|
|`02-Python`|Python 安装、虚拟环境、pip、依赖管理、脚本开发|
|`03-Django`|Django 后端项目创建、目录结构、数据库连接、接口开发|
|`04-Vue3`|Vue 3 前端项目创建、组件开发、接口请求|
|`05-uni-app`|uni-app 开发、微信小程序配置、前后端联调|
|`06-STM32`|STM32 开发环境、CubeMX、VS Code、Keil5、烧录流程|
|`07-Docker`|Docker 安装、容器命令、项目部署|
|`templates`|常用项目模板和初始化结构|

---

## 使用方式

### 1. 写新笔记

每学习一个新的技术点，就在对应目录下新建 `.md` 文件。

例如：

```
01-VSCode/VSCode配置Python环境.md02-Python/Python虚拟环境venv.md03-Django/Django项目创建流程.md
```

---

### 2. 记录问题

遇到报错时，建议按照下面格式记录：

```
# 问题标题## 问题现象这里记录报错信息、截图说明、发生场景。## 原因分析这里记录为什么会出现这个问题。## 解决方法这里记录具体解决步骤。## 总结这里记录以后如何避免这个问题。
```

---

### 3. 记录命令

常用命令建议单独整理，方便后续复制使用。

例如：

```
git statusgit add .git commit -m "update notes"git push
```

---

## 笔记命名规范

建议使用中文标题，方便自己快速查找。

推荐格式：

```
技术名称 + 具体内容.md
```

示例：

```
VSCode配置Python环境.mdPython虚拟环境venv.mdDjango项目创建流程.mdSTM32CubeMX到VSCode开发流程.mdGitHub推送流程.md
```

---

## Markdown 编写规范

每篇笔记建议包含以下结构：

```
# 标题## 一、背景说明## 二、操作步骤## 三、核心命令## 四、常见问题## 五、总结
```

---

## Git 同步命令

手动同步时使用：

```
git statusgit add .git commit -m "update notes"git push
```

首次推送时使用：

```
git add .git commit -m "init: add tech stack notes"git push -u origin main
```

---

## Obsidian 使用说明

本仓库可以作为 Obsidian 笔记库使用。

推荐使用方式：

1. 使用 Obsidian 打开本仓库文件夹
2. 在 Obsidian 中编写 Markdown 笔记
3. 使用 Git 或 Obsidian Git 插件同步到 GitHub

推荐忽略 Obsidian 临时文件：

```
.trash/.obsidian/workspace.json.obsidian/workspace-mobile.json.obsidian/cache/
```

---

## 当前重点整理方向

近期主要整理以下内容：

- VS Code 配置 Python 环境
- VS Code Profile 配置方法
- GitHub 仓库推送流程
- Obsidian 与 GitHub 同步流程
- Python 虚拟环境配置
- Django 后端项目创建
- uni-app 与微信小程序开发
- STM32 从 CubeMX 到 VS Code 的开发流程

---

## 项目原则

本仓库遵循以下原则：

1. 内容尽量详细，适合复盘和教学
2. 命令尽量完整，方便复制执行
3. 每个技术点单独成文，便于后期维护
4. 报错问题要记录现象、原因和解决方法
5. 项目源码和学习笔记分开管理

---

## 维护记录

|时间|内容|
|---|---|
|2026-04-30|创建技术栈笔记仓库|
|2026-04-30|初始化 README 和目录结构|

---

## License

本仓库主要用于个人学习和技术积累，内容仅供学习参考。