# Chapter-3
第三章算例中涉及的数据与产消者参数

# 概述  
本项目是博士论文 _**《智能配电网产消者能量共享优化方法研究》-“第三章 考虑信息交互时延影响的异步迭代优化方法”**_ 中案例研究参数的说明文档。  

> _**2_Prosumers**_：包含 2 个产消者的能源共享案例研究参数与历史数据集。  
> _**10_Prosumers**_：包含 10 个产消者的能源共享案例研究参数与历史数据集。  
> _**50_Prosumers**_：包含 50 个产消者的能源共享案例研究参数与历史数据集。  
> _**100_Prosumers**_：包含 100 个产消者的能源共享案例研究参数与历史数据集。

# 环境要求
>Python 3  
>Numpy  

# 打开方式
以 _**2_Prosumers**_ 为例，包含两类文件。<br>
***"Decision_Making_Model_Parameters.npy"*** 为产消者决策模型的参数。<br>
***"pr_data i.xlsx"*** 包含通过历史成功通信获得的数据（随机生成）。<br>

## 在 Python 中运行以下代码即可打开 ***"Decision_Making_Model_Parameters.npy"***。
```Python
import numpy as np
dict_ = np.load('Decision_Making_Model_Parameters.npy',allow_pickle = True).item()
```

# 参数说明
### 我们的参数以字典（dictionary）的形式构建，不同键（key）的具体含义解释如下：  

>_**'Qi'**_ : 指代文中的 _**Q<sub>i</sub>**_；  
>_**'di'**_ : 指代文中的 _**d<sub>i</sub>**_；   
>_**'Ai'**_ : 指代文中 _**x<sub>i,r</sub>**_ 的系数矩阵；  
>_**'Bi'**_ : 指代文中 _**x<sub>i,r</sub>**_ 的边界向量；  
>_**'E'**_ : 指代文中 _**x<sub>i,r</sub>**_ 的系数矩阵；  
>_**'Di'**_ : 指代文中 _**D<sub>i</sub>**_。  

# 历史数据集说明
### 历史数据集以 .xlsx 文件记录，不同列的具体含义解释如下：

>_**'Resource 1'**_ : 指代成功通信数据中资源 1 的上界（下界默认为 0）；  
>_**'Resource 2'**_ : 指代成功通信数据中资源 2 的上界（下界默认为 0）；    
>_**'Price'**_ : 指代成功通信数据中的影子价格（或乘子 lamda）；   
>_**'Demand'**_ : 指代成功通信数据中的电力需求（或 _**D<sub>i</sub>**_）；     
>_**'virtual_var'**_ : 指代成功通信数据中的辅助变量 _**y<sub>i,sh</sub>**_；  
>_**'trade_volumn'**_ : 指代成功通信数据中的最优响应 _**x<sub>i,sh</sub>**_。

# 异质产消者说明
### 异质产消者记录在 "two heterogeneous prosumers.npy" 文件中，不同参数的具体含义解释如下：
>_**'Obj'**_ : 指代成本函数的形式。有两个值：Foursq（四次函数）和 Twosq（二次函数）；  
>_**'Con'**_ : 指代约束函数的形式。有两个值：Twosq（二次函数）和 Linear（线性函数）；  
>当 Obj 为 Twosq 且 Con 为 Linear 时，形式与上述参数说明一致；  
>当 Obj 为 Foursq 时，Qi 和 di 分别指代成本函数中四次项和二次项的系数；  
>当 Con 为 Linear 时，Ai 和 Bi 分别指代约束函数中二次项和常数项的系数。
