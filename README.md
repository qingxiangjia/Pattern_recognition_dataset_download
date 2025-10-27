# Pattern_recognition_dataset_download 
# 模式识别数据集介绍及下载链接

## 题目一、目标检测任务（模式识别方法在驾驶员行为目标检测上的应用）
评价指标采用Average Precision(AP)、Recall、mAP@0.5、mAP@0.5:0.95等

##### 数据集介绍 本数据集包含了 7981 张训练图像，997 张验证图像和 997 张测试图像，所有图像都提供了对应打标好的标签，数据集大小约 350MB。数据集被标注为 YOLOv8 格式，适用于目标检测任务。数据集包括 3 个标签类别：Smoke、Phone 和 Drink。
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
![Uploading results.png…]()

##### 如果需要其他格式的标注数据，您可以使用相关代码进行转换，网上已有许多现成的工具可用于此目的。
##### 数据集应用：该数据集可用于训练物体检测模型，适用于 YOLO 系列算法或其他常见的检测框架。
