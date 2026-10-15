# Zotero Add-ons Scraper

**Zotero 插件信息采集与索引自动化。**

本仓库是 [syt2/zotero-addons-scraper](https://github.com/syt2/zotero-addons-scraper) 的派生副本，用于学习与探索 Zotero 插件生态。原始项目、上游发布入口与来源说明保留在下方。

[上游项目](https://github.com/syt2/zotero-addons-scraper) &nbsp; / &nbsp; [插件条目](addons) &nbsp; / &nbsp; [工作流](../../actions) &nbsp; / &nbsp; 

## 工作流概览

```mermaid
flowchart LR
    A[插件条目] --> B[获取仓库与发布信息]
    B --> C[整理为 JSON]
    C --> D[publish 分支与 Release]
```

在自己的 fork 中使用时，先在 Actions 中启用所需的定时工作流。是否已执行或已发布，应以本仓库的 Actions 与 Releases 实际状态为准。

## 上游说明

以下内容保留上游的使用方式、发布目标和标签约定。徽章与发布链接指向上游，不表示本 fork 的构建或发布状态。

![GitHub Build Status](https://img.shields.io/github/actions/workflow/status/syt2/zotero-addons-scraper/main.yml?logo=githubactions)
![GitHub Last Commit Time](https://img.shields.io/github/last-commit/syt2/zotero-addons-scraper/publish?logo=github)
![jsdelivr hits](https://img.shields.io/jsdelivr/gh/hw/syt2/zotero-addons-scraper?logo=jsdelivr)


This is a script repository for scraping [Zotero](https://www.zotero.org) add-ons, intended for use with [Zotero Addons](https://github.com/syt2/zotero-addons).  
> Switch to `addon-scraper` source in [Zotero Addons](https://github.com/syt2/zotero-addons) to use this repository.

## Workflows
This repository utilizes GitHub Actions workflow for automation. 
including the following steps:
- Retrieve [Zotero](https://www.zotero.org) add-on information specified in [addons](addons) folder
- Parse add-on information into JSON data
- Publish the JSON data to the [`publish`](https://github.com/syt2/zotero-addons-scraper/blob/publish/addon_infos.json) branch and the [latest release](https://github.com/syt2/zotero-addons-scraper/releases/latest)

## Contributing
Adding a new add-on entry `{owner}@{repo}` in the [addons](addons) folder.

Optionally, add up to two tags by writing JSON content to the file:
```json
{"tags": ["reader", "utility"]}
```

Available tags:

| Tag | Description |
|---|---|
| `ai` | AI-powered features (summarization, chat, translation via LLM) |
| `metadata` | Metadata retrieval, citation counts, impact factor, formatting |
| `reader` | PDF reading experience, annotation, highlighting |
| `notes` | Note-taking, markdown export, knowledge management |
| `attachment` | File management, attachment organization, OCR |
| `interface` | UI enhancements, themes, column customization |
| `integration` | Integration with external services (Notion, Obsidian, Word, etc.) |
| `utility` | Zotero system tools (automation, deduplication, plugin management) |

## Usage
1. `fork` this repository
2. Enable actions and scheduled workflow in `Actions` page of forked repository
