# Online Loan Transaction Data Visualization Report  
**Author:** Li Yiping  
**Date:** June 15, 2024  

---

## Preface
For online lending companies, the support of big data plays an important role in precise customer targeting and performance evaluation. Through data analysis, enterprises can assess the performance of each region and regional manager, track performance paths, analyze customer conversion, and optimize workflows.  

This report takes the online loan transaction data of Ant Financial in August 2020 as the research object. Through the integration and analysis of transaction data, customer acquisition data, and performance target data, this report aims to reveal the performance of different regions, zones, and business groups, evaluate acquisition efficiency, forecast future trends, and summarize the current business situation.  

In the preparation of this report, a variety of data visualization techniques were applied, including stacked charts, Gantt charts, word clouds, bubble charts, ring charts, trend maps, Pareto charts, bullet charts, funnel charts, radar charts, Sankey diagrams, box plots, and waterfall charts, in order to achieve comprehensive, in-depth, and intuitive analytical effects.  

---

## 1. Background

### 1.1 Data Source
This report is based on the accumulation of previous projects and uses Ant Financial loan transaction data for visualization. Since the dataset is large and Ant Financial data is difficult to obtain, this report only involves partial data from August 2020, each dataset containing fewer than 1,000 records. A total of three datasets are involved: transaction data, acquisition data, and performance targets.  

### 1.2 Data Overview

#### August Transaction Data
The dataset is divided into three sheets. Sheet 1 shows transaction data (867 rows), Sheet 2 shows war zone information, and Sheet 3 shows city information.  

**Table 1. Sample Transaction Data**  
| Date       | Business Group            | Transaction Amount | Interest Receivable | Overdue Amount | War Zone   | City   | Subgroup   |
|------------|---------------------------|--------------------|---------------------|----------------|------------|--------|------------|
| 2020-08-01 | West Zone – Chongqing 1   | 15,568             | 1,009               | 0              | West Zone  | Chongqing | Chongqing 1 |
| 2020-08-01 | West Zone – Xi’an 1       | 53,172             | 4,791               | 0              | West Zone  | Xi’an    | Xi’an 1 |
| 2020-08-01 | West Zone – Wuhan 1       | 45,255             | 5,447               | 0              | West Zone  | Wuhan    | Wuhan 1 |
| 2020-08-01 | West Zone – Chengdu 1     | 102,755            | 10,027              | 0              | West Zone  | Chengdu  | Chengdu 1 |
| 2020-08-01 | West Zone – Chengdu 2     | 5,500              | 789                 | 0              | West Zone  | Chengdu  | Chengdu 2 |

**Table 2. War Zone Information**  
| Zone Name  | Zone ID | Manager | Level |
|------------|---------|---------|-------|
| East Zone  | 001     | Jiang Yong | Level 1 |
| South Zone | 002     | Gao Anping | Level 2 |
| West Zone  | 003     | Tian Nan   | Level 2 |
| North Zone | 004     | Shen Lexin | Level 3 |

**Table 3. City Information**  
| City ID | City     | Manager   | Level | Avg. Monthly Salary |
|---------|----------|-----------|-------|---------------------|
| 001     | Shanghai | Wu Gang   | Tier 1 | 12,114 |
| 002     | Guangzhou| Sun Bing  | Tier 1 | 9,854  |
| 003     | Hangzhou | Du Guangliang | Tier 2 | 10,499 |
| 004     | Nanjing  | Su Chuan  | Tier 2 | 9,912  |
| 005     | Hefei    | Hou Yangbing | Tier 2 | 8,694 |
| 006     | Wuhan    | Wang Gang | Tier 2 | 9,107  |
| 007     | Beijing  | Fan Junfa | Tier 1 | 12,358 |
| 008     | Shenzhen | Gao Hongzhuang | Tier 1 | 11,498 |
| 009     | Chengdu  | Ye Chao   | Tier 2 | 9,016  |
| 010     | Xi’an    | Huang Pengtian | Tier 2 | 8,295 |
| 011     | Tianjin  | Feng Qian | Tier 1 | 8,244  |
| 012     | Chongqing| Yu Zimo   | Tier 2 | 9,713  |
| 013     | Suzhou   | Zhang Jian| Tier 2 | 8,800  |

#### August Acquisition Data
Dataset 2 shows acquisition data (867 rows), corresponding to the transaction dataset.  

**Table 4. Sample Acquisition Data**  
| Date       | Business Group            | Registered | Verified | Clicked | Granted | Converted | Avg. Sesame Score |
|------------|---------------------------|------------|----------|---------|---------|-----------|-------------------|
| 2020-08-01 | West Zone – Chongqing 1   | 1,387      | 1,375    | 1,327   | 836     | 439       | 688 |
| 2020-08-01 | West Zone – Xi’an 1       | 3,717      | 3,652    | 3,534   | 2,135   | 1,196     | 691 |
| 2020-08-01 | West Zone – Wuhan 1       | 2,052      | 1,990    | 1,900   | 1,211   | 553       | 700 |
| 2020-08-01 | West Zone – Chengdu 1     | 2,179      | 2,129    | 2,053   | 1,330   | 782       | 692 |
| 2020-08-01 | West Zone – Chengdu 2     | 672        | 662      | 643     | 443     | 209       | 692 |

**Notes:**  
- *Clicked (戳额)*: In online transactions, this refers to clicking/confirming the payment amount.  
- *Granted (给额)*: Refers to the granting of funds (transfer/payment).  
- *Sesame Credit Score (芝麻分)*: A credit scoring system launched by Ant Financial (range: 350–950; higher = better credit).  

#### August Performance Target Data
Performance targets are grouped by region, with 30 rows total.  

**Table 5. Regional Performance Targets**  
| Business Group | Target Amount |
|----------------|----------------|
| North Zone – Beijing 2 | 190,810 |
| North Zone – Beijing 3 | 1,986,429 |
| North Zone – Beijing 4 | 1,241,545 |
| North Zone – Beijing 1 | 374,627 |
