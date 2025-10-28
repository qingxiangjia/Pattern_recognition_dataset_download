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

##### cityspaces数据集子集（推介使用）

##### 原始cityspaces数据集下载地址（不推介使用太大） 通过网盘分享的文件：cityscapes.zip   链接: https://pan.baidu.com/s/1_zqsRd7Wy4AW9gbG-Lf9OA?pwd=49nj 提取码: 49nj 
 
##### 数据集参数
|  | 原始cityspaces数据集 | cityspaces数据集子集 | 是否有标签 |
|:-----------:|:----------------:|:---------:|:---------:|
| train | 2975张 | 288张 | 有
| val | 500张 | 48张 | 有
| test | 1525张 | 0张 | 官方数据集test不提供标签
| 数据集大小 | 11.03G | 863M | 

##### 训练时间开销及参考结果：
        1080显卡，2080,3060,4060,3090,4090，A100等显卡都可以运行，可以根据自己显卡参数和配置适量调整模型的输入参数和数据集参数
        IoU是像素级语义分割指标（不区分个体），nIoU是实例级分割指标（区分每个独立目标，按实例大小加权）
        cityspaces数据集子集：Nvidia Geforce GTX 3090Ti （24GB显存） 显卡，使用标准deeplabv3+，骨干网络resnet18模型，在提供的cityspaces数据集子集，训练和验证1000epoch 大约需要6个小时，推介使用这个
        

        原始cityspaces数据集：Nvidia Geforce GTX 3090Ti （24GB显存） 显卡，使用标准deeplabv3+，骨干网络resnet18模型，在提供的原始cityspaces数据集，训练和验证1000epoch 大约需要55个小时，训练较为耗时不推介使用
        100epoch结果：                                        580epoch结果：
        classes          IoU      nIoU                classes          IoU      nIoU
        --------------------------------                --------------------------------
        road          : 0.931      nan                road          : 0.925      nan
        sidewalk      : 0.693      nan                sidewalk      : 0.715      nan
        building      : 0.850      nan                building      : 0.861      nan
        wall          : 0.576      nan                wall          : 0.586      nan
        fence         : 0.394      nan                fence         : 0.392      nan
        pole          : 0.387      nan                pole          : 0.389      nan
        traffic light : 0.389      nan                traffic light : 0.385      nan
        traffic sign  : 0.546      nan                traffic sign  : 0.603      nan
        vegetation    : 0.854      nan                vegetation    : 0.843      nan
        terrain       : 0.576      nan                terrain       : 0.531      nan
        sky           : 0.884      nan                sky           : 0.831      nan
        person        : 0.586    0.444                person        : 0.623    0.465
        rider         : 0.330    0.173                rider         : 0.438    0.208
        car           : 0.862    0.784                car           : 0.910    0.757
        truck         : 0.269    0.211                truck         : 0.726    0.497
        bus           : 0.666    0.503                bus           : 0.821    0.609
        train         : 0.000    0.000                train         : 0.000    0.000
        motorcycle    : 0.275    0.106                motorcycle    : 0.401    0.155
        bicycle       : 0.543    0.406                bicycle       : 0.529    0.374
        --------------------------------                --------------------------------
        Score Average : 0.559    0.328                Score Average : 0.606    0.383
        --------------------------------                --------------------------------
        
        
        categories       IoU      nIoU                categories       IoU      nIoU
        --------------------------------                --------------------------------
        flat          : 0.944      nan                flat          : 0.940      nan
        construction  : 0.858      nan                construction  : 0.866      nan
        object        : 0.450      nan                object        : 0.459      nan
        nature        : 0.877      nan                nature        : 0.875      nan
        sky           : 0.884      nan                sky           : 0.831      nan
        human         : 0.627    0.499                human         : 0.645    0.504
        vehicle       : 0.865    0.772                vehicle       : 0.883    0.746
        --------------------------------                --------------------------------
        Score Average : 0.786    0.635                Score Average : 0.786    0.625
        --------------------------------                --------------------------------
| 图片名 | 原始cityspaces数据集 100epoch验证集效果 | 原始cityspaces数据集 580epoch验证集效果 |
|:-----------:|:----------------:|:---------:|
| frankfurt_000000_012868_overlayed.png | <img width="1024" height="512" alt="frankfurt_000000_012868_overlayed" src="https://github.com/user-attachments/assets/0470b052-656a-4672-9221-5d8417e57d8f" /> | <img width="1024" height="512" alt="frankfurt_000000_012868_overlayed" src="https://github.com/user-attachments/assets/3e866aec-6e27-4b51-8828-b9fd8b3f9aa2" />
| lindau_000022_000019_overlayed.png | <img width="1024" height="512" alt="lindau_000022_000019_overlayed" src="https://github.com/user-attachments/assets/5fcab31d-f4e1-47ef-bcab-aefac2d6521f" /> | <img width="1024" height="512" alt="lindau_000022_000019_overlayed" src="https://github.com/user-attachments/assets/0a316572-0a9e-4cd6-9e7d-7ad21c5f6577" />
| munster_000023_000019_overlayed.png | <img width="1024" height="512" alt="munster_000023_000019_overlayed" src="https://github.com/user-attachments/assets/7a5e6b45-9839-430b-8eb4-2ea242ffbdef" /> | <img width="1024" height="512" alt="munster_000023_000019_overlayed" src="https://github.com/user-attachments/assets/f288c17c-b3ab-4ccc-a647-ffd0ecbea0c7" />

##### Cityscapes 7类到19类映射

| 类别组 (7类) | 包含的具体类别 (19类) 
|:-----------:|:----------------:|
| flat |  road, sidewalk
| construction |  building, wall, fence
| object |  pole, traffic light, traffic sign
| nature |  vegetation, terrain
| sky |  sky
| human |  person, rider
| vehicle | car, truck, bus, train, motorcycle, bicycle
	
	
	

## 题目三、多模态行为识别（模式识别跨校课程竞赛）

##### 比赛名称 多模态行为识别
##### 参赛链接待上传，请等待
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
##### Example Videos

| Depth | Thermal-IR | RGB |
|:-----------:|:----------------:|:---------:|
| ![output_depth](https://github.com/user-attachments/assets/c0c73c81-5d15-407e-b341-bbfd5b58bd1d) | ![output_ir](https://github.com/user-attachments/assets/dc6abb8b-ab5f-4f0b-aafc-81c3d1783102) | ![output_rgb](https://github.com/user-attachments/assets/3d8c5ec3-6b22-4486-beac-475c94b8ac0c)

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



