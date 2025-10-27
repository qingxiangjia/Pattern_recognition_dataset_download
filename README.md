# Pattern_recognition_dataset_download 
# 模式识别大作业数据集介绍及下载链接

## 题目一、目标检测任务（模式识别方法在驾驶员行为目标检测上的应用）
评价指标采用Average Precision(AP)、Recall、mAP@0.5、mAP@0.5:0.95等

##### 数据集介绍 本数据集包含了 7981 张训练图像，997 张验证图像和 997 张测试图像，所有图像都提供了对应打标好的标签，数据集大小约 350MB。数据集被标注为 YOLOv8 格式，适用于目标检测任务。数据集包括 3 个标签类别：Smoke、Phone 和 Drink。
##### 下载地址：通过网盘分享的文件：datasets_3种抽烟喝水玩手机.zip   链接: https://pan.baidu.com/s/1IwxpW9Sp3s9y4Cuz1HK6Uw?pwd=3ddp 提取码: 3ddp 
##### 数据集结构：
        训练集：7981 张图像
        验证集：997 张图像
        测试集：997 张图像
##### 数据总大小：约 350MB
##### 标签类别 本数据集包含以下 3 个类别：
        Smoke：吸烟
        Phone：手机
        Drink：喝水
##### 标签类别的格式符合 YOLOv8 标注标准，具体为：
nc: 3 # 标签类别个数
names: ['Smoke', 'Phone', 'Drink'] # 标签名

##### 数据格式
        本数据集使用 YOLOv8 格式进行标注。每张图像对应一个 .txt 文件，文件中包含图像中各个物体的标签信息，每行表示一个物体，格式如下：
        <class> <x_center> <y_center> <width> <height>
        class：物体的类别索引（从 0 开始，Smoke 为 0，Phone 为 1，Drink 为 2）。
        x_center、y_center：物体边界框中心点的归一化坐标。
        width、height：物体边界框的宽度和高度，均为归一化值（相对于图像宽度和高度）。

##### 训练时间开销及参考结果：
        Nvidia Geforce GTX 1080Ti （11GB显存） 显卡，使用标准yolov8n模型，在提供的数据集上，训练和验证150epoch 大约需要3小时，参考结果
        metrics/precision(B)	      metrics/recall(B)	       metrics/mAP50(B)	    metrics/mAP50-95(B)
              0.94429	                      0.89767	             0.94152	       0.65009
<img width="2400" height="1200" alt="results" src="https://github.com/user-attachments/assets/3e587f1e-7662-4ce0-8188-3a8406c606b0" />


##### 如果需要其他格式的标注数据，您可以使用相关代码进行转换，网上已有许多现成的工具可用于此目的。
##### 数据集应用：该数据集可用于训练物体检测模型，适用于 YOLO 系列算法或其他常见的检测框架。



## 题目二、图像语义分割任务（模式识别方法在城市街景分割上的应用）





## 题目三、多模态行为识别（模式识别跨校课程竞赛）

##### 比赛名称 多模态行为识别
##### 参赛链接待上传
##### 允许提交次数 无限次
##### 提交截止时间 2025-12-31 00:00:01
##### 比赛任务设置
        学生需要上传，利用"generate_submission.py"生成需提交的"submission.csv"文件
##### 比赛说明
        提供的多模态行为识别数据集包含700组多模态视频（其中500组用于训练，200组用于测试），涵盖20个动作类别。评测时会计算在测试集上的Top-1、Top-5指标并以Top-1为依据进行排名。
##### 任务描述
        基于MMAR数据集的多模态行为识别，MMAR数据集包含三种模态（RGB、Depth、Infrared）对齐的20种行为类别，每种行为类别大约30到70个视频序列，每个视频序列有100到200帧，需要根据视频的三个不同模态的特征，用算法识别该视频序列属于哪一个行为类别。
##### 数据说明  数据集详细介绍以及baseline代码请参考：https://github.com/happylinze/multi-modal-tsm 。
        任务所使用图像数据集，训练集每个模态包含500个视频序列，被分为20类，每个类别有超过30个的视频序列；测试集每个模态包含200个视频序列，同样包含20个类。
        其中20个类别分别为： switch light、up the stairs、pack backpack、ride a bike、turn around、fold clothes、hug somebody、long jump、move the chair、open the umbrella、orchestra conducting、rope skipping、shake hands、squat、swivel、tie shoes 、tie hair、twist waist、wear hat、down the stairs。
        本次所用数据集是该链接中所提到数据集的子集。
        注意：需要自行把训练数据划分为训练集和验证集。

##### 提交结果
        训练完成后，利用提供的“generate_submission.py”文件，生成在测试集上的预测结果, 文件格式为.csv，命名为 "submission.csv"
        文件内的字段需要按照以下指定格式写入。（video id, predicted Top-5 classes）
        
##### 结果文件要求：
        1.每个类别的行数和测试集原始数据行数应一 一对应，不可乱序。
        2.输出结果应检查是否和测试集数量一样的200行的数据，否则成绩无效。
        3.输出结果文件命名为submission.csv，文件中样例如下(第一列是video id，第二列为predicted Top-5 classes的预测结果)：
        |video_id|prediction   
        |1     |16 11 12 5 18 
        |2     |15 1 19 7 4  
        |3     |3 7 9 18 4
        |4     |11 4 16 12 5
        |5     |7 3 18 9 11
        |6     |15 5 1 19 2
        |7     |8 13 6 10 17
        |8     |9 2 18 5 16
        |9     |4 15 18 3 11
        ......



