# Leetcode_tracker
# 📚 LeetCode CN ➜ Notion 同步工具

> 自动从 **LeetCode 中文站**抓取题目信息（标题、描述、难度、标签），并同步到你的 Notion，Let's记录刷题的点点滴滴🧑‍🤝‍🧑。

## 功能概述

1. 支持输入 LeetCode 中文站 URL 自动提取 slug  
2. 使用官方 GraphQL API 获取完整题目内容（含翻译标题、描述、难度、标签）  
3. 自动写入 Notion Database  
4. CLI/Colab 弹窗交互输入：Importance / Review 状态 / Comments

## 技术栈 & 原理

- Python 3.x
- 使用 `requests` 调用 LeetCode CN 的 GraphQL 接口
- 使用 `notion-client`（Python SDK）调用 Notion 官方 REST API
- HTML 转 Notion blocks：BeautifulSoup 解析后分块生成

## 准备工作

1. **创建 Notion Integration**  
   - 前往 [Notion My Integrations](https://www.notion.com/my-integrations) 新建一个内部集成  
   - 保存 `Internal Integration Token`
   <img width="450" height="240" alt="Snipaste_2025-07-12_10-58-33" src="https://github.com/user-attachments/assets/79e2e8b0-3f56-48c2-b762-a3d951e90d83" />


2. **创建你的 LeetCode Tracker Database**
   - 打开 Notion，新建一个 Database（表格视图）
     参考：[Notion Database Demo](https://held-cress-aa2.notion.site/ebd/22ea5250489c80869851e6fac66ca7dc?v=22ea5250489c81238de0000c775032d6)
     
     <img width="750" height="290" alt="Snipaste_2025-07-12_11-03-02" src="https://github.com/user-attachments/assets/778e7403-6b98-4b58-b18a-745375a19f4d" />
     
     如果想自己定义不同的table，需要在colab中修改对应的代码，主要修改表项名即可
   - 记下该数据库的 ID，后续在colab中输入  
右上角-分享-共享-拷贝链接，链接中的`https://www.notion.so/`后面紧跟着的32位即数据库ID

3. **在 Database 中关联你的集成**
   - 点击右上角三个点，选择集成
   - 输入你的 Integration 名称搜索，添加连接
     


## 使用步骤

1. 打开以下Colab链接并复制一份到自己的google drive：[Colab python代码](https://colab.research.google.com/drive/1S5_OcN1mXaemD7RlXbCeJMNr0t2G1vEb?usp=sharing)
2. 按照以下步骤执行（以下也可参见Colab中的“使用步骤”提示）
```bash
# 1. 填写你的 NOTION_TOKEN 和 DATABASE_ID
# 2. 全部运行
# 3. 按提示输入 Importance、Review、Comments、URL
# 4. 成功写入/更新 Notion
