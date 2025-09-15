# 📊 蚂蚁微贷Tableau Dashboard经营分析 / Ant Microfinance Tableau Dashboard and Business Insights Case  
**Date / 日期:** June 15, 2024  

---

## 📑 目录 / Table of Contents
- 前言 Preface
- 第一章 背景介绍 Background
  - 1.1 数据来源 Data Source
  - 1.2 数据概况 Data Overview
- 第二章 数据可视化分析 Visualization Analysis
  - 2.1 数据预处理 Data Preprocessing
  - 2.2 业绩分析 Performance Analysis
  - 2.3 获客分析 Customer Acquisition Analysis
  - 2.4 利润分析 Profitability Analysis
- 第三章 结论与建议 Conclusions & Recommendationsrecommendations)
---

## 前言 / Preface  

对于网络借贷公司而言，大数据的支持对其精准进行客户定位和业绩评估有重要意义。  
For online lending companies, the support of big data plays an important role in precise customer targeting and performance evaluation.  

通过分析数据，企业可以评估各个地区、各地区经理业绩情况，追踪业绩路径，分析客户转化情况进而优化工作流程等。  
Through data analysis, enterprises can assess the performance of each region and regional manager, track performance paths, analyze customer conversion, and optimize workflows.  

本报告以网贷成交数据为研究对象，通过数据可视化的方法，深入分析了蚂蚁金服2020年8月份的借贷成交情况。  
This report takes the online loan transaction data of Ant Financial in August 2020 as the research object.  

通过对成交数据、获客数据和业绩目标数据的整合与分析，本报告旨在揭示不同地区、不同战区以及不同业务小组的业绩表现，评估获客效率，预测未来趋势，并总结其业务现状。  
Through the integration and analysis of transaction data, customer acquisition data, and performance target data, this report aims to reveal the performance of different regions, zones, and business groups, evaluate acquisition efficiency, forecast future trends, and summarize the current business situation.  

在撰写过程中，本报告采用了多种数据可视化技术，包括：  
Stacked charts, Gantt charts, word clouds, bubble charts, ring charts, trend maps, Pareto charts, bullet charts, funnel charts, radar charts, Sankey diagrams, box plots, and waterfall charts — in order to achieve comprehensive, in-depth, and intuitive analysis.  

---

## 第一章 背景介绍 / 1. Background  

### 1.1 数据来源 / 1.1 Data Source  

本报告基于之前的项目积累，采用蚂蚁金服借贷成交数据进行数据可视化。  
This report is based on the accumulation of previous projects and uses Ant Financial loan transaction data for visualization.  

由于数据量较大且蚂蚁金服数据难以获取，所以本报告只涉及其2020年8月内的部分数据，每个数据集数据量均小于1000条。  
Since the dataset is large and Ant Financial data is difficult to obtain, this report only involves partial data from August 2020, each dataset containing fewer than 1,000 records.  

一共涉及三个数据集：成交数据、获客数据、业绩目标。  
A total of three datasets are involved: transaction data, acquisition data, and performance targets.  

---

### 1.2 数据概况 / 1.2 Data Overview  

#### 8月成交数据 / August Transaction Data  

该数据集分为三个 Sheet：  
The dataset is divided into three sheets:  
- Sheet1: 成交数据 / Transaction data (867 rows)  
- Sheet2: 战区信息 / War zone information  
- Sheet3: 城市信息 / City information  

**表1 部分成交数据 / Table 1. Sample Transaction Data**  

| 日期 | 业务组 | 成交额 | 应收利息 | 逾期金额 | 战区 | 城市 | 小组 |
|------|--------|--------|----------|----------|------|------|------|
| 2020-08-01 | 西部战区–重庆一组 | 15,568 | 1,009 | 0 | 西部战区 | 重庆 | 重庆一组 |
| 2020-08-01 | 西部战区–西安一组 | 53,172 | 4,791 | 0 | 西部战区 | 西安 | 西安一组 |
| 2020-08-01 | 西部战区–武汉一组 | 45,255 | 5,447 | 0 | 西部战区 | 武汉 | 武汉一组 |
| 2020-08-01 | 西部战区–成都一组 | 102,755 | 10,027 | 0 | 西部战区 | 成都 | 成都一组 |
| 2020-08-01 | 西部战区–成都二组 | 5,500  | 789   | 0 | 西部战区 | 成都 | 成都二组 |

| Date       | Business Group          | Transaction Amount | Interest Receivable | Overdue Amount | War Zone   | City      | Subgroup   |
|------------|-------------------------|--------------------|---------------------|----------------|------------|-----------|------------|
| 2020-08-01 | West Zone – Chongqing 1 | 15,568             | 1,009               | 0              | West Zone  | Chongqing | Chongqing 1 |
| 2020-08-01 | West Zone – Xi’an 1     | 53,172             | 4,791               | 0              | West Zone  | Xi’an     | Xi’an 1 |
| 2020-08-01 | West Zone – Wuhan 1     | 45,255             | 5,447               | 0              | West Zone  | Wuhan     | Wuhan 1 |
| 2020-08-01 | West Zone – Chengdu 1   | 102,755            | 10,027              | 0              | West Zone  | Chengdu   | Chengdu 1 |
| 2020-08-01 | West Zone – Chengdu 2   | 5,500              | 789                 | 0              | West Zone  | Chengdu   | Chengdu 2 |

---

**表2 战区信息 / Table 2. War Zone Information**  

| 战区名称 | 战区编号 | 战区经理 | 战区等级 |
|----------|----------|----------|----------|
| 东部战区 | 001      | 江永     | 一级战区 |
| 南部战区 | 002      | 高安平   | 二级战区 |
| 西部战区 | 003      | 田楠     | 二级战区 |
| 北部战区 | 004      | 沈乐欣   | 三级战区 |

| Zone Name  | Zone ID | Manager   | Level   |
|------------|---------|-----------|---------|
| East Zone  | 001     | Jiang Yong| Level 1 |
| South Zone | 002     | Gao Anping| Level 2 |
| West Zone  | 003     | Tian Nan  | Level 2 |
| North Zone | 004     | Shen Lexin| Level 3 |

---

**表3 城市信息 / Table 3. City Information**  

| 城市编号 | 城市 | 城市经理 | 城市等级 | 平均月薪 |
|----------|------|----------|----------|----------|
| 001      | 上海 | 吴刚     | 一线     | 12114    |
| 002      | 广州 | 孙乒     | 一线     | 9854     |
| 003      | 杭州 | 杜光亮   | 二线     | 10499    |
| 004      | 南京 | 苏川     | 二线     | 9912     |

| City ID | City     | Manager   | Level  | Avg. Monthly Salary |
|---------|----------|-----------|--------|---------------------|
| 001     | Shanghai | Wu Gang   | Tier 1 | 12,114              |
| 002     | Guangzhou| Sun Bing  | Tier 1 | 9,854               |
| 003     | Hangzhou | Du Guangliang | Tier 2 | 10,499          |
| 004     | Nanjing  | Su Chuan  | Tier 2 | 9,912               |

---

#### 8月获客数据 / August Acquisition Data  

数据集2展示获客数据，共867条数据，与前述成交数据对应。  
Dataset 2 shows acquisition data (867 rows), corresponding to the transaction dataset.  

**表4 部分获客数据 / Table 4. Sample Acquisition Data**  

| 日期       | 业务组         | 注册人数 | 实名认证人数 | 戳额人数 | 给额人数 | 成交人数 | 平均芝麻分 |
|------------|----------------|----------|--------------|----------|----------|----------|------------|
| 2020-08-01 | 西部战区–重庆一组 | 1,387    | 1,375        | 1,327    | 836      | 439      | 688        |

| Date       | Business Group          | Registered | Verified | Clicked | Granted | Converted | Avg. Sesame Score |
|------------|-------------------------|------------|----------|---------|---------|-----------|-------------------|
| 2020-08-01 | West Zone – Chongqing 1 | 1,387      | 1,375    | 1,327   | 836     | 439       | 688               |

**注释 / Notes**  
- 戳额 (Clicked): 确认支付金额 / Confirming the payment amount  
- 给额 (Granted): 转账或支付 / Granting funds (transfer/payment)  
- 芝麻分 (Sesame Score): 350–950, 分数越高信用越好 / Higher scores = better credit  

---

#### 8月业绩目标数据 / August Performance Target Data  

业绩目标由各个地区划分，因此数据量较小，共30条数据。  
Performance targets are grouped by region, with 30 rows total.  

**表5 各地区业绩目标 / Table 5. Regional Performance Targets**  

| 业务组 | 目标 |
|--------|------|
| 北部战区–北京二组 | 190,810 |
| 北部战区–北京三组 | 1,986,429 |

| Business Group         | Target Amount |
|------------------------|----------------|
| North Zone – Beijing 2 | 190,810        |
| North Zone – Beijing 3 | 1,986,429      |

---

## 第二章 数据可视化分析  
## Chapter 2. Data Visualization Analysis  

---

### 2.1 数据预处理  
### 2.1 Data Preprocessing  

在进行下一步分析之前，需要将三个数据集整合形成一个整体，如下图1所示。  
Before further analysis, the three datasets need to be integrated into one unified dataset, as shown in Figure 1.  
<img width="434" height="244" alt="1" src="https://github.com/user-attachments/assets/3ee93cd5-a4f3-47ed-82a2-6feeb111d0e3" />

图1 数据整合图示 / Figure 1. Data Integration

每个部分的链接方式如下图2所示。  
The linking method between each dataset is illustrated in Figure 2.  
<img width="938" height="518" alt="fig2" src="https://github.com/user-attachments/assets/bf574bc4-2eda-47f4-997e-3c558cfa20f2" />

图2 数据链接方式 / Figure 2. Data Linking Structure]

---

### 2.2 业绩分析  
### 2.2 Performance Analysis  

#### 2.2.1 地区业绩分析  
#### 2.2.1 Regional Performance Analysis  

首先，对各个战区的成交额情况进行大致的可视化分析。  
First, a general visualization of transaction amounts across different war zones is conducted.  
<img width="751" height="462" alt="fig3" src="https://github.com/user-attachments/assets/5c7193c0-de3c-4a79-a79f-a082dd3c1692" />

图3 战区成交额情况堆叠图和甘特图 / Figure 3. Transaction Amounts by War Zone (Stacked & Gantt Chart)

上图用堆叠柱状图的形式展示了各个战区一线和二线城市成交额占比，并且使用双轴甘特图表现了各战区的成交总额。此外，还可以对战区做进一步的下钻，下钻层级为战区–城市–小组，如图4所示。  
The figure above shows the proportion of Tier-1 and Tier-2 city transaction amounts in each war zone using a stacked bar chart, and total transactions with a dual-axis Gantt chart. Further drill-down analysis can be performed by war zone → city → subgroup, as shown in Figure 4. 

<img width="1488" height="924" alt="fig4" src="https://github.com/user-attachments/assets/2026cd9d-d0b6-4046-861f-c33dcd115dbc" />

图4 地区成交额下钻分析 / Figure 4. Drill-down Analysis of Regional Transactions

此外，还可以使用词云图来对地区成交额情况进行分析。在“标记”选项卡中，将“成交额”作为大小，城市作为颜色和文本，得到成交额地区词云图如图5。  
In addition, a word cloud can be used to analyze regional transaction amounts. By setting "Transaction Amount" as size, and "City" as color and text in the marks card, we obtain a regional word cloud (Figure 5).  

<img width="1134" height="757" alt="fig5" src="https://github.com/user-attachments/assets/435390ac-b5e1-436e-99f0-8315667a249d" />

图5 成交额地区词云图 / Figure 5. Word Cloud of Regional Transaction Amounts

利用气泡图进行可视化得到各个地区成交额占比气泡图，如图6。  
A bubble chart was also created to show the proportion of transaction amounts by region (Figure 6). 

<img width="781" height="521" alt="fig6" src="https://github.com/user-attachments/assets/3ebd1519-4109-4908-9fc4-cd768db0b2f2" />

图6 地区成交额占比气泡图 / Figure 6. Regional Transaction Amount Bubble Chart 

接下来，可以通过多维环形图对各个战区内城市的成交额占比情况进行分析。列维度选择战区，城市作为颜色，成交额作为大小，得到环形图7。  
Next, a multi-ring chart was used to analyze the share of transaction amounts for cities within each war zone. "War Zone" was placed on columns, "City" as color, and "Transaction Amount" as size, resulting in Figure 7.  

<img width="781" height="521" alt="fig7" src="https://github.com/user-attachments/assets/c8c05d2d-0cd3-40a7-8690-8ab8f9340a2d" />

图7 地区多维环形图 / Figure 7. Multi-ring Chart of Regional Transaction Amounts

可以看出，一线城市的成交额占比较高，且长三角地区城市比如上海、苏州等成交额占比最高。为进一步可视化地区成交额分布以及其随时间变化的情况，创建趋势地图如图8，将“日期”添加至“页面”。该地图可以随着日期进行变化，8月29日情况如图8。  

It can be seen that Tier-1 cities contribute a higher proportion of transaction amounts, with Yangtze River Delta cities such as Shanghai and Suzhou being the highest. To further analyze regional distribution and time variation, a trend map was created with "Date" on the Pages shelf. Figure 8 shows the status on August 29.  

<img width="1267" height="845" alt="fig8" src="https://github.com/user-attachments/assets/22f948de-71f9-4833-9834-114c2cf478d7" />

图8 地区业绩趋势地图 / Figure 8. Regional Performance Trend Map

---

#### 2.2.2 小组业绩分析  
#### 2.2.2 Subgroup Performance Analysis  

在该部分，首先使用帕累托图探索成交额和小组的占比情况，如图9所示。此处可以用参数筛选排名前列的小组，但是由于小组数量较少，所以此图的筛选范围为全选。  
First, a Pareto chart was used to explore subgroup contributions to total transaction amounts (Figure 9). Parameter filters can be applied to show top groups, but since the number of subgroups is small, all were included.  

<img width="883" height="534" alt="fig9" src="https://github.com/user-attachments/assets/9efda8ae-4f15-4ded-8314-2e97e0b3ed4d" />

图9 小组成交额帕累托图 / Figure 9. Subgroup Transaction Pareto Chart


由图9可以看出近60%的小组占据了80%的成交额。接下来，进一步对小组业绩进行评价。  
As shown in Figure 9, about 60% of the subgroups account for 80% of the total transactions. Next, subgroup performance was further evaluated.  

在评价绩效时，小组的目标完成情况是重要的依据，因此需要对各个小组的业绩完成情况进行可视化。在该部分的可视化中，可以使用条形图和甘特图相结合的方式对小组业绩目标完成情况进行可视化。  
When evaluating performance, target completion is a key metric. Therefore, subgroup target achievement was visualized using a combination of bar charts and Gantt charts.  

<img width="781" height="407" alt="fig10" src="https://github.com/user-attachments/assets/50e458db-9e77-476b-af60-f0c4883c51d8" />

图10 小组业绩完成情况与目标 / Figure 10. Subgroup Performance vs. Target

从图10可以看出，一些小组按时完成任务，而部分小组没能如期完成任务。但是考虑到地区经济的差异，只是从条形图来看不足以全面说明小组的业绩情况，因此进一步细化条形图成为标靶图。  
Figure 10 shows that some subgroups completed their tasks on time, while others did not. Considering regional economic differences, bar charts alone are not sufficient, so bullet charts were created for a more precise view.  

将目标修改为条形图，将其调细，按单元格添加平均值参考线（因为分母为1所以此处平均值就是目标值本身）。为了进一步展现小组目标完成情况，创建“达成率”目标字段：`sum([成交额]) / sum([目标额])`，并将其作为颜色添加在“目标”条形图上。可视化如图11。  
The target field was visualized as a thin bar with reference lines at the average (equal to the target itself). A new calculated field "Achievement Rate" = `SUM([Transaction Amount]) / SUM([Target Amount])` was added as color. The visualization is shown in Figure 11.  

<img width="781" height="407" alt="fig11" src="https://github.com/user-attachments/assets/57ae5c74-0d48-4699-ba68-c6915b753e7e" />

图11 小组业绩完成情况标靶图 / Figure 11. Subgroup Bullet Chart for Target Achievement

图11展示了各个小组的目标达成情况，由图可知，业绩完成情况最好的几组分别为南京二组、成都一组等，而广州一组、南京一组的业绩表现较差。  
Figure 11 displays subgroup achievement rates. The best-performing subgroups are Nanjing Group 2 and Chengdu Group 1, while Guangzhou Group 1 and Nanjing Group 1 performed poorly.  

另外，应收利息是该公司主要的利润来源，而逾期金额则意味着亏损的可能。因此，需要将逾期金额与应收利息做对照比较，以观察各个战区逾期金额是否给利润造成压力。如图12所示。  
Additionally, interest receivable is the main source of profit, while overdue amounts represent potential losses. Thus, overdue vs. receivable interest was compared to assess profit pressure across war zones (Figure 12).  

<img width="781" height="407" alt="fig12" src="https://github.com/user-attachments/assets/a9e3f0ef-48e1-4b7c-97b5-bddf6a3e147d" />

图12 小组逾期金额和应收利润条形图 / Figure 12. Overdue Amount vs. Receivable Interest 

由图12可以看出，部分小组，比如广州三组和西安一组的逾期金额超过了应收利息，说明利润情况比较危险。本报告将在后文具体分析利润情况。  
As shown in Figure 12, some groups, such as Guangzhou Group 3 and Xi’an Group 1, had overdue amounts exceeding receivable interest, indicating dangerous profitability conditions. Profit analysis will be discussed in detail later.  

在实际的业务应用中，公司需要根据时间对各个地区或是业务经理的业绩情况做追踪分析，此时可以使用树图。以“周”为时间单位放置于“行”，将战区作为颜色，将成交额作为大小，并打上标签。得到图13为地区业绩追踪图。  
In practical business applications, companies need to track performance by region and manager over time. Tree maps were used for this purpose, with "Week" on rows, "War Zone" as color, and "Transaction Amount" as size. Figure 13 shows the regional tracking result.  

<img width="781" height="533" alt="fig13" src="https://github.com/user-attachments/assets/4ba5ee21-e98f-4719-9a18-360ee8a6b1ac" />

图13 地区业绩追踪图 / Figure 13. Regional Performance Tracking Tree Map

将鼠标置于特定的地区上就可以看到该地区业绩的排位变化，但在导出的图中没有办法实现这一点。进一步可以得到地区经理的业绩追踪图如图14。  
Hovering over a region reveals its ranking changes, though this cannot be captured in exported images. A further drill-down yields city manager tracking results (Figure 14).  

<img width="781" height="533" alt="fig14" src="https://github.com/user-attachments/assets/13bdd053-f97e-4f11-b624-26b32d32249e" />

图14 城市经理业绩追踪图 / Figure 14. City Manager Performance Tracking


另外，也可以使用凹凸图进一步分析各经理在8月各周中的成交额排序。可视化如图15。  
Additionally, bump charts were used to analyze manager ranking changes in weekly transactions during August (Figure 15).  

<img width="627" height="420" alt="fig15" src="https://github.com/user-attachments/assets/50403a02-0241-4a7c-883a-7c006db93d04" />

图15 城市经理业绩排序凹凸图 / Figure 15. City Manager Ranking Bump Chart

如图14、15可以看出，孙乒的业绩占比一直较高而且稳定，杜光亮的业绩后期表现不如前期，而且业绩表现优秀的总是特定的几个人，同时，业绩排名末尾的人也比较稳定。  
As Figures 14 and 15 show, Sun Bing consistently maintained high and stable performance, while Du Guangliang’s performance declined later in the month. Top performers remained mostly the same individuals, and those ranked at the bottom also stayed stable.  

---

#### 2.2.3 业绩预测  
#### 2.2.3 Performance Forecasting  

利用Tableau可以对数据进行趋势预测。在“分析”栏中选择“预测”模型和趋势线，添加指数趋势线和多项式趋势线，得到图16。  
Tableau’s forecasting function was applied. By adding exponential and polynomial trendlines from the "Analytics" pane, Figure 16 was obtained.  

<img width="781" height="521" alt="fig16" src="https://github.com/user-attachments/assets/b64a51f5-ddfd-4a0c-a733-c7aad54266fb" />

图16 业绩预测折线图 / Figure 16. Performance Forecast Line Chart


图16展示了利用八月的成交额总和预测的截止9月12日的成交额。由预测可以看出，九月上旬成交额增速变缓。  
Figure 16 shows the forecasted transaction amounts up to September 12, based on August totals. The forecast indicates a slowdown in early September.  

---

### 2.3 获客分析  
### 2.3 Customer Acquisition Analysis  

使用漏斗图来进行获客转化的分析，即用户转化漏斗。在原始数据表中，用户转化的流程为：注册人数–实名认证人数–戳额人数–给额人数–成交人数。转化情况如图17。  
A funnel chart was used to analyze customer acquisition and conversion, i.e., the user conversion funnel. In the raw dataset, the conversion process is: Registered → Verified → Clicked → Granted → Converted. The results are shown in Figure 17.  

<img width="762" height="291" alt="fig17" src="https://github.com/user-attachments/assets/b365c716-21b2-4d99-b699-2cdabb8c2006" />

图17 用户转化漏斗图 / Figure 17. Customer Conversion Funnel

由图17可以看出，注册、实名认证、戳额三个阶段转化率比较高，但是从戳额到给额阶段转化率大幅降低，说明从戳额到给额是用户转化的关键阶段。进一步以周为单位切分，并用平均芝麻分作为颜色来评估获客质量，得到图18。  
As shown in Figure 17, the conversion rates for registration, verification, and clicking are relatively high. However, the rate drops significantly from “Clicked” to “Granted,” indicating this is the key bottleneck in conversion. Further analysis was conducted on a weekly basis, with average Sesame Credit Score used as color to evaluate acquisition quality, as shown in Figure 18.  

<img width="768" height="209" alt="fig18" src="https://github.com/user-attachments/assets/49b19c71-1a2b-47dc-934a-e1c7cc924599" />

图18 获客情况时间变化漏斗图 / Figure 18. Weekly Customer Acquisition Funnel with Credit Scores

由图18可知，八月后三周的获客质量相对较高。  
As shown in Figure 18, customer acquisition quality was relatively higher in the last three weeks of August.  

接下来，用雷达图分析各个战区的获客能力。  
Next, a radar chart was used to analyze acquisition ability across war zones.  

将各个战区的获客数据归一化并处理后得到如表6所示的数据集，利用该数据集将各个战区的获客情况可视化为雷达图，如图19所示。  
After normalizing acquisition data by war zone (Table 6), a radar chart was created to visualize acquisition performance, as shown in Figure 19.  

<img width="605" height="534" alt="fig19" src="https://github.com/user-attachments/assets/fd9947ba-d8e8-4ca6-88f8-5f57e7f59788" />

图19 战区获客雷达图 / Figure 19. Customer Acquisition Radar Chart by War Zone]

由于各个战区的获客情况雷达图高度重合，所以图19筛选了东部战区和西部战区作为展示。由图19可知，各个战区在注册人数、实名认证人数、戳额人数获客程度较好，而在给额人数和成交人数方面获客不佳，这与前文用户转化情况一致。  
Since the radar plots for all zones overlapped heavily, only the East and West zones were displayed in Figure 19. The chart shows that war zones performed well in registration, verification, and clicking, but poorly in granting and conversion—consistent with the earlier funnel analysis.  

进一步的，利用桑基图表示时间、战区、获客情况三个维度的流量转化。其中，时间为“周数”，一共5周；战区为东南西北四战区；获客情况依据前文用户转化率，选取戳额人数、给额人数和成交人数三个阶段。桑基图如图20。  
Furthermore, a Sankey diagram was used to show flow conversion across three dimensions: Time (five weeks), War Zone (East, South, West, North), and Acquisition Stage (Clicked, Granted, Converted). The result is shown in Figure 20.  

<img width="500" height="400" alt="fig20" src="https://github.com/user-attachments/assets/af26b263-b7df-4e72-9d39-2a36f44b7282" />

图20 时间-战区-获客桑基图 / Figure 20. Time–Zone–Acquisition Sankey Diagram

---

### 2.4 利润分析  
### 2.4 Profitability Analysis  

在该数据中，与利润相关的字段一共有四个：应收利息、逾期金额、资金成本、获客成本。为了进一步观察其利润，我们创建“毛利率”= SUM([应收利息]) – SUM([逾期金额]) – SUM([资金成本]) – SUM([获客成本])。  
In the dataset, four fields are related to profitability: Interest Receivable, Overdue Amount, Funding Cost, and Acquisition Cost. To assess profit, a new measure was defined:  
**Gross Profit = SUM(Interest Receivable) – SUM(Overdue) – SUM(Funding Cost) – SUM(Acquisition Cost)**.  

其中“获客成本” = 注册人数 × 0.5；“资金成本” = 成交额 × 0.03。  
Where Acquisition Cost = Registered × 0.5, and Funding Cost = Transaction Amount × 0.03.  

首先，使用箱线图查看各个战区主要城市的成交额以及其利润情况。毛利大于0者为蓝色，毛利小于0者为红色。  
First, a box plot was used to examine transaction amounts and profitability by major cities in each war zone. Cities with positive gross profit were marked blue, and those with negative profit were marked red.  

<img width="591" height="521" alt="fig21" src="https://github.com/user-attachments/assets/d53d3800-8f46-4588-b7be-16649ad8e7ed" />

图21 地区成交额和利润箱线图 / Figure 21. Regional Transaction and Profit Box Plot

由图21可以大致看出各个战区城市成交额排名概况，并且能够看出其是否盈利。比如广州，虽然成交额很高，但是其利润却是最低的。为进一步分析这种情况的原因，我们使用瀑布图对小组利润进行下钻分析，如图22所示。  
Figure 21 shows the general ranking of transaction amounts by city, along with profitability. For example, Guangzhou has high transaction amounts but the lowest profit. To further analyze the reasons, a waterfall chart of subgroup profits was created (Figure 22).  

<img width="724" height="521" alt="fig22" src="https://github.com/user-attachments/assets/55328d62-a6b6-4c9d-b596-54432ccd64d4" />

图22 小组利润瀑布图 / Figure 22. Subgroup Profit Waterfall Chart

从图22可以简单看出，全部小组的毛利润总和为负，部分小组毛利明显偏低，比如广东一组、广东三组等。为了进一步分析是什么因素导致其利润偏低，我们分析其毛利占比、逾期金额占比、获客成本占比、资金成本占比。分别创建三个占比的字段，以逾期金额占比为例：逾期占比 = SUM([逾期金额]) / SUM([应收利息])。占比如图23所示。  
As shown in Figure 22, the total gross profit of all subgroups was negative, with some (e.g., Guangdong Group 1 and Group 3) significantly underperforming. To identify the drivers of low profit, ratios were calculated for overdue, acquisition cost, and funding cost. For example, Overdue Ratio = SUM(Overdue) / SUM(Interest Receivable). Results are shown in Figure 23.  

<img width="1489" height="1103" alt="fig23" src="https://github.com/user-attachments/assets/cf9fdd00-3834-4be0-8499-208509f5517d" />

图23 利润占比图 / Figure 23. Profit Composition Ratios

如图23，可以看出，利润的减少主要是由于逾期金额的增加所致，资金成本和获客成本基本保持稳定。从利润占比来看，北京一组的利润占比是最低的，即使它的毛利总额排名靠中间位，因此需要特别关注。广州三组利润占比倒数第二，同时毛利率总额也是最低的，应该重点关注。  
As shown in Figure 23, the decline in profitability was mainly driven by rising overdue amounts, while funding and acquisition costs remained stable. Beijing Group 1 had the lowest profit ratio despite a mid-level gross profit, indicating it requires special attention. Guangzhou Group 3 ranked second worst in profit ratio and also had the lowest gross profit overall, suggesting it should be closely monitored.  

---
---

## 第三章 结论与建议  
## Chapter 3. Conclusions and Recommendations  

由以上分析，报告可以粗略得出以下结论。  
From the above analysis, the report can roughly draw the following conclusions.  

首先地区业绩存在差异，不同战区和城市在成交额上存在显著差异，其中一线城市的成交额普遍高于二线和三线城市。  
First, there are significant differences in regional performance. Different war zones and cities show distinct transaction amounts, with Tier-1 cities generally outperforming Tier-2 and Tier-3 cities.  

对于小组业绩表现而言，部分小组业绩表现突出，占据了较大的市场份额，但也有部分小组业绩不佳。值得注意的是，有些小组虽然成交额总数比较低，但是其超额完成业绩目标。  
In terms of subgroup performance, some subgroups stood out and occupied a large market share, while others performed poorly. Notably, some subgroups achieved or exceeded their performance targets despite having relatively low total transaction amounts.  

进一步分析城市经理的业绩表现可以看出，各经理的业绩排名相对稳定，业绩优秀的人持续位列前茅，而业绩不佳的人则一直位于尾部。  
Further analysis of city managers’ performance shows that rankings were relatively stable: top performers consistently stayed ahead, while underperformers remained at the bottom.  

在获客阶段，从戳额到给额的阶段转化率下降明显，表明这一环节是提升获客效率的关键。  
At the acquisition stage, the conversion rate dropped significantly from “Clicked” to “Granted,” indicating that this step is the key to improving acquisition efficiency.  

另外，利用趋势预测模型，本报告预测了短期内的成交额变化，发现增速有放缓的趋势。  
In addition, using trend forecasting models, the report predicted short-term transaction changes, showing that the growth rate is slowing down.  

进一步考虑利润情况，可以发现部分小组成交额虽然占比较高，但是利润状况并不乐观，需要重点关注逾期金额的控制。  
Considering profitability, it was found that some subgroups, despite having high transaction shares, had unfavorable profit conditions. This highlights the need to focus on controlling overdue amounts.  

---

基于以上分析，本报告建议提升一线城市市场，拓展二三线城市市场。  
Based on the above analysis, this report recommends strengthening Tier-1 city markets and expanding into Tier-2 and Tier-3 markets.  

对于一线城市，重点关注其中成交额占比大但是毛利较低的小组，比如广东三组等，采取措施降低逾期金额，优化成本。  
For Tier-1 cities, special attention should be given to subgroups with high transaction shares but low gross profit, such as Guangdong Group 3. Measures should be taken to reduce overdue amounts and optimize costs.  

对于二三线城市，应该聚焦于提高其成交总额，提升客户转化率，达到整体业绩的提升和市场的拓展。  
For Tier-2 and Tier-3 cities, efforts should focus on increasing transaction totals and improving customer conversion rates, in order to achieve overall performance growth and market expansion.  

---

