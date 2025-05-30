# 金融事件知识图谱构建实践

这是一个基于Python的新闻知识图谱构建系统，能够从财经新闻网站爬取数据，提取实体关系，构建知识图谱，并进行可视化分析。

## 功能概述

1. **新闻爬取**：从指定网站抓取新闻排行榜数据
2. **实体关系提取**：使用DeepSeek API提取新闻中的实体和关系
3. **知识图谱存储**：将提取的知识存储到Neo4j图数据库
4. **数据可视化**：使用NetworkX和Matplotlib可视化知识图谱
5. **图神经网络准备**：将图谱数据转换为PyTorch Geometric格式


## 主要组件

### 1. 新闻爬虫 (`NewsSpider`类)
- 使用Requests和BeautifulSoup抓取新闻
- 支持自动拼接相对URL
- 实现礼貌性爬取延迟

### 2. 实体关系提取 (`EntityExtractor`类)
- 集成DeepSeek API
- 支持实体属性增强
- 自动生成属性模板

### 3. Neo4j存储 (`Neo4jStorage`类)
- 创建新闻节点和实体节点
- 建立节点间关系
- 支持清空数据库

### 4. 增强爬虫 (`EnhancedNewsSpider`类)
- 组合爬取、提取和存储功能
- 实现两阶段处理流程

### 5. 数据导出与可视化
- 从Neo4j导出CSV数据
- 使用NetworkX构建图结构
- 多种可视化方式：
  - 按新闻分组的子图
  - 整体网络图
  - 节点类型分布图

### 6. 图神经网络准备
- 提取节点特征
- 构建边索引
- 生成PyTorch Geometric的Data对象

## 安装与运行

### 前置要求
- Python 3.8+
- Neo4j数据库 (3.5+)
- DeepSeek API密钥

### 依赖安装
```bash
pip install -r requirements.txt
