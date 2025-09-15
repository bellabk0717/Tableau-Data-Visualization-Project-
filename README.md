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

## 第二章 数据可视化分析  
## Chapter 2. Data Visualization Analysis  

---

### 2.1 数据预处理  
### 2.1 Data Preprocessing  

在进行下一步分析之前，需要将三个数据集整合形成一个整体，如下图1所示。  
Before further analysis, the three datasets need to be integrated into one unified dataset, as shown in Figure 1.  

![图1 数据整合图示 / Figure 1. Data Integration](fig1.png)  

每个部分的链接方式如下图2所示。  
The linking method between each dataset is illustrated in Figure 2.  

![图2 数据链接方式 / Figure 2. Data Linking Structure](fig2.png)  

---

### 2.2 业绩分析  
### 2.2 Performance Analysis  

#### 2.2.1 地区业绩分析  
#### 2.2.1 Regional Performance Analysis  

首先，对各个战区的成交额情况进行大致的可视化分析。  
First, a general visualization of transaction amounts across different war zones is conducted.  

![图3 战区成交额情况堆叠图和甘特图 / Figure 3. Transaction Amounts by War Zone (Stacked & Gantt Chart)](fig3.png)  

上图用堆叠柱状图的形式展示了各个战区一线和二线城市成交额占比，并且使用双轴甘特图表现了各战区的成交总额。此外，还可以对战区做进一步的下钻，下钻层级为战区–城市–小组，如图4所示。  
The figure above shows the proportion of Tier-1 and Tier-2 city transaction amounts in each war zone using a stacked bar chart, and total transactions with a dual-axis Gantt chart. Further drill-down analysis can be performed by war zone → city → subgroup, as shown in Figure 4.  

![图4 地区成交额下钻分析 / Figure 4. Drill-down Analysis of Regional Transactions](fig4.png)  

此外，还可以使用词云图来对地区成交额情况进行分析。在“标记”选项卡中，将“成交额”作为大小，城市作为颜色和文本，得到成交额地区词云图如图5。  
In addition, a word cloud can be used to analyze regional transaction amounts. By setting "Transaction Amount" as size, and "City" as color and text in the marks card, we obtain a regional word cloud (Figure 5).  

![图5 成交额地区词云图 / Figure 5. Word Cloud of Regional Transaction Amounts](fig5.png)  

利用气泡图进行可视化得到各个地区成交额占比气泡图，如图6。  
A bubble chart was also created to show the proportion of transaction amounts by region (Figure 6).  

![图6 地区成交额占比气泡图 / Figure 6. Regional Transaction Amount Bubble Chart](fig6.png)  

接下来，可以通过多维环形图对各个战区内城市的成交额占比情况进行分析。列维度选择战区，城市作为颜色，成交额作为大小，得到环形图7。  
Next, a multi-ring chart was used to analyze the share of transaction amounts for cities within each war zone. "War Zone" was placed on columns, "City" as color, and "Transaction Amount" as size, resulting in Figure 7.  

![图7 地区多维环形图 / Figure 7. Multi-ring Chart of Regional Transaction Amounts](fig7.png)  

可以看出，一线城市的成交额占比较高，且长三角地区城市比如上海、苏州等成交额占比最高。为进一步可视化地区成交额分布以及其随时间变化的情况，创建趋势地图如图8，将“日期”添加至“页面”。该地图可以随着日期进行变化，8月29日情况如图8。  
It can be seen that Tier-1 cities contribute a higher proportion of transaction amounts, with Yangtze River Delta cities such as Shanghai and Suzhou being the highest. To further analyze regional distribution and time variation, a trend map was created with "Date" on the Pages shelf. Figure 8 shows the status on August 29.  

![图8 地区业绩趋势地图 / Figure 8. Regional Performance Trend Map](fig8.png)  

---

#### 2.2.2 小组业绩分析  
#### 2.2.2 Subgroup Performance Analysis  

在该部分，首先使用帕累托图探索成交额和小组的占比情况，如图9所示。此处可以用参数筛选排名前列的小组，但是由于小组数量较少，所以此图的筛选范围为全选。  
First, a Pareto chart was used to explore subgroup contributions to total transaction amounts (Figure 9). Parameter filters can be applied to show top groups, but since the number of subgroups is small, all were included.  

![图9 小组成交额帕累托图 / Figure 9. Subgroup Transaction Pareto Chart](fig9.png)  

由图9可以看出近60%的小组占据了80%的成交额。接下来，进一步对小组业绩进行评价。  
As shown in Figure 9, about 60% of the subgroups account for 80% of the total transactions. Next, subgroup performance was further evaluated.  

在评价绩效时，小组的目标完成情况是重要的依据，因此需要对各个小组的业绩完成情况进行可视化。在该部分的可视化中，可以使用条形图和甘特图相结合的方式对小组业绩目标完成情况进行可视化。  
When evaluating performance, target completion is a key metric. Therefore, subgroup target achievement was visualized using a combination of bar charts and Gantt charts.  

![图10 小组业绩完成情况与目标 / Figure 10. Subgroup Performance vs. Target](fig10.png)  

从图10可以看出，一些小组按时完成任务，而部分小组没能如期完成任务。但是考虑到地区经济的差异，只是从条形图来看不足以全面说明小组的业绩情况，因此进一步细化条形图成为标靶图。  
Figure 10 shows that some subgroups completed their tasks on time, while others did not. Considering regional economic differences, bar charts alone are not sufficient, so bullet charts were created for a more precise view.  

将目标修改为条形图，将其调细，按单元格添加平均值参考线（因为分母为1所以此处平均值就是目标值本身）。为了进一步展现小组目标完成情况，创建“达成率”目标字段：`sum([成交额]) / sum([目标额])`，并将其作为颜色添加在“目标”条形图上。可视化如图11。  
The target field was visualized as a thin bar with reference lines at the average (equal to the target itself). A new calculated field "Achievement Rate" = `SUM([Transaction Amount]) / SUM([Target Amount])` was added as color. The visualization is shown in Figure 11.  

![图11 小组业绩完成情况标靶图 / Figure 11. Subgroup Bullet Chart for Target Achievement](fig11.png)  

图11展示了各个小组的目标达成情况，由图可知，业绩完成情况最好的几组分别为南京二组、成都一组等，而广州一组、南京一组的业绩表现较差。  
Figure 11 displays subgroup achievement rates. The best-performing subgroups are Nanjing Group 2 and Chengdu Group 1, while Guangzhou Group 1 and Nanjing Group 1 performed poorly.  

另外，应收利息是该公司主要的利润来源，而逾期金额则意味着亏损的可能。因此，需要将逾期金额与应收利息做对照比较，以观察各个战区逾期金额是否给利润造成压力。如图12所示。  
Additionally, interest receivable is the main source of profit, while overdue amounts represent potential losses. Thus, overdue vs. receivable interest was compared to assess profit pressure across war zones (Figure 12).  

![图12 小组逾期金额和应收利润条形图 / Figure 12. Overdue Amount vs. Receivable Interest](fig12.png)  

由图12可以看出，部分小组，比如广州三组和西安一组的逾期金额超过了应收利息，说明利润情况比较危险。本报告将在后文具体分析利润情况。  
As shown in Figure 12, some groups, such as Guangzhou Group 3 and Xi’an Group 1, had overdue amounts exceeding receivable interest, indicating dangerous profitability conditions. Profit analysis will be discussed in detail later.  

在实际的业务应用中，公司需要根据时间对各个地区或是业务经理的业绩情况做追踪分析，此时可以使用树图。以“周”为时间单位放置于“行”，将战区作为颜色，将成交额作为大小，并打上标签。得到图13为地区业绩追踪图。  
In practical business applications, companies need to track performance by region and manager over time. Tree maps were used for this purpose, with "Week" on rows, "War Zone" as color, and "Transaction Amount" as size. Figure 13 shows the regional tracking result.  

![图13 地区业绩追踪图 / Figure 13. Regional Performance Tracking Tree Map](fig13.png)  

将鼠标置于特定的地区上就可以看到该地区业绩的排位变化，但在导出的图中没有办法实现这一点。进一步可以得到地区经理的业绩追踪图如图14。  
Hovering over a region reveals its ranking changes, though this cannot be captured in exported images. A further drill-down yields city manager tracking results (Figure 14).  

![图14 城市经理业绩追踪图 / Figure 14. City Manager Performance Tracking](fig14.png)  

另外，也可以使用凹凸图进一步分析各经理在8月各周中的成交额排序。可视化如图15。  
Additionally, bump charts were used to analyze manager ranking changes in weekly transactions during August (Figure 15).  

![图15 城市经理业绩排序凹凸图 / Figure 15. City Manager Ranking Bump Chart](fig15.png)  

如图14、15可以看出，孙乒的业绩占比一直较高而且稳定，杜光亮的业绩后期表现不如前期，而且业绩表现优秀的总是特定的几个人，同时，业绩排名末尾的人也比较稳定。  
As Figures 14 and 15 show, Sun Bing consistently maintained high and stable performance, while Du Guangliang’s performance declined later in the month. Top performers remained mostly the same individuals, and those ranked at the bottom also stayed stable.  

---

#### 2.2.3 业绩预测  
#### 2.2.3 Performance Forecasting  

利用Tableau可以对数据进行趋势预测。在“分析”栏中选择“预测”模型和趋势线，添加指数趋势线和多项式趋势线，得到图16。  
Tableau’s forecasting function was applied. By adding exponential and polynomial trendlines from the "Analytics" pane, Figure 16 was obtained.  

![图16 业绩预测折线图 / Figure 16. Performance Forecast Line Chart](fig16.png)  

图16展示了利用八月的成交额总和预测的截止9月12日的成交额。由预测可以看出，九月上旬成交额增速变缓。  
Figure 16 shows the forecasted transaction amounts up to September 12, based on August totals. The forecast indicates a slowdown in early September.  

