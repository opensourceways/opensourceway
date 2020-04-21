---
title: "配置 issue 和 Pull Request 模板"
date: 2020-04-16T17:40:42+08:00
draft: false
weight: 1
enableToc: true
tocLevels: ["h2", "h3", "h4"]
---

# 配置 issues 模版和 pull request 模版

维护者通过预置的issues 模版和 pull request 模版可以让用户/贡献者按照预置的格式反馈信息，
使社区成员之间能够进行有效地交流，降低沟通成本，提高问题的解决效率。
模板的格式为Markdown文件。

## 使用 issues 模版

为满足不同的场景，建议维护者提供多个issue模板：
- 问题反馈模板 (Bug Report)
- 特性增强或需求模板 (Feature Request)
- 自定义模板 (Custom Template)

![issue 模板](images/issue_template.png)

### 通过github创建

1. 在GitHub上，导航到仓库的主页面,在仓库名称下，单击**Stttings（设置）**；

2. 在Feature中的issue下，单机**Set up templete（设置模板）**;

![设置 issue 模板](images/setup_issue_template_menu.png)

3. 使用**Add template（添加模板）** 下拉菜单，单击要创建的模板类型；

![添加 issue 模板](images/add_issue_template_menu.png)

4. 在提交之前可以对模板进行预览或编辑；

![预览 issue 模板](images/preview_and_edit_issue_template.png)

![编辑 issue 模板](images/edit_issue_template.png)

5. 在**Optional additional items（可选附加信息）** 中可以设置issue的默认标题、指定Assignees和标签等信息；

![添加可选配置](images/add_additional_items.png)

6. 完成编辑和预览后，单击页面右上角的**Propose changes（提议更新）**，输入提交信息后进行commit；
![提交 issue 模板](images/commit_changes.png)

7. 在仓库的提交记录中，可以看到本次提交增加了`.github/ISSUE_TEMPLATE/bug_report.md`文件。

### 手工创建
在`.github/ISSUE_TEMPLATE`目录下可以添加多个`.md`文件作为issue 模板，编辑文件内容后通过git进行提交。
文件的参考格式如下：

```
---
name: 模板名称
about: 模板描述

---

模板内容...
```

### issue 模板建议包含的内容
- issue的现象描述
- 系统环境、软件版本、参数配置等信息
- issue的复现步骤
- 相关调试日志：如果日志过多，建议贡献者通过链接形式提供
- 受影响的功能
- 期望的建议
- 相关的依赖

## 使用 pull request 模版

贡献者通过pull request向主仓库提交代码，为了更好地帮助贡献者在代码提交之前执行基础检查项，建议维护者在仓库的默认分支中提供pull request模板。
pull request模板分为默认模板和多模板，二者可以同时存在。

![使用 pull request 模版](images/pull_request.png)

### 创建默认模版
在`.github`目录下创建`pull_request_template.md`文件作为pull request 默认模板。当创建不带参数的pull request时，系统会引用该模板。

### 创建多模版
在`.github/PULL_REQUEST_TEMPLATE`目录下可以添加多个`.md`文件作为pull request 模板。
pull request模板需要通过查询参数进行调用，详细的使用方法参见[github帮助文档](https://help.github.com/en/github/managing-your-work-on-github/about-automation-for-issues-and-pull-requests-with-query-parameters)

### pull request 模板建议包含的内容
- 变更说明
- 测试用例执行结果
- 是否更新文档
- 相关评审人
- 解决/关联的issue: fixes #<issue number>


## 参考资料
* <https://help.github.com/en/github/building-a-strong-community/configuring-issue-templates-for-your-repository>
* <https://help.github.com/en/github/building-a-strong-community/creating-a-pull-request-template-for-your-repository>
