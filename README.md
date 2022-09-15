## 1. 简介

- 本项目主要是基于autoencoder算法对汽车电池的异常检测。autoencoder是一种能通过无监督学习进行数据的降维，并且可以将降维后的数据又重新还原。我们利用这一点，训练出可以将正常样本进行重建
还原，却不能将异于正常分布的数据样本进行较好的还原，导致还原误差较大。因此一个新的样本被编码、解码后，他的误差超过了所设置得阈值则认为此样本维异常样本。所以在此次项目中我们先用正常得样本
训练autoencoder,之后在设置合适的阈值进行异常检测。
-此次我们所用的评价指标为AUC。
## 2. 数据集和比赛结果
-训练集：文件类型为.pkl文件，每个pkl文件内容为元组形式，（data,metadata）；
data：形状为（256，8），每列数据对应特征['volt','current','soc','max_single_volt','min_single_volt','max_temp','min_temp','timestamp']
metadata：包含label和mileage信息，label标签中‘00’表示正常片段，‘10’表示异常片段。

测试集：文件类型为.pkl文件，每个pkl文件内容为元组形式，
data,metadata）；
data：形状为（256，8），每列数据对应特征['volt','current','soc','max_single_volt','min_single_volt','max_temp','min_temp','timestamp']
metadata：仅包含mileage信息。
-比赛结果通过运行代码会获得csv文件。
3. 准备数据与环境

### 3.1 准备环境

- 建议将代码中用到的非python原生的库，都写在requirements.txt中，直接使用`pip install -r requirements.txt`安装依赖即可。

### 3.2 准备数据

- 将训练集数据中的部分正常样本选出来作为用来训练模型，训练模型之前还要将数据进行标准化处理。
## 5. LICENSE

- 本项目的发布受[Apache 2.0 license](https://github.com/thinkenergy/vloong-Anomaly-detection/blob/master/LICENSE)许可认证。
