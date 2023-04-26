<!--
 * @Date: 2023-04-24 09:05:55
 * @Author: Bruce
 * @Description: 
-->
## 简介

```
单目标物体检测
此项目是根据yolov5的模型框架来实时检测足球
```

## 环境的安装

```
pip install -r requirements.txt
```

## **检测结果**

<img width="1172" alt="b7c729f0d552dc40560e4ccb3da61c9" src="https://user-images.githubusercontent.com/65518559/234010629-f67a7b2a-4422-4785-a42d-8d401edebcb9.png">

https://user-images.githubusercontent.com/65518559/233912141-b72a8167-84e5-46c7-9f91-a83f95d04ff4.mp4

## 数据集的训练

```
1. 将准备好的数据集放到根目录下,并解压
2. 使用处理数据脚本prepare_data.py
3. 修改data目录下的文件voc_ball.yaml文件,改成自己的训练路径,类别编号
4. 修改models目录下的文件yolov5s_ball.yaml, 修改类别的数目
```

## **开始训练**

```
python train.py --data data/voc_ball.yaml --cfg models/yolov5s_ball.yaml --weights weights/yolov5s.pt --batch-size 16 --epochs 50 --workers 4
```

## **测试图片**

```
python detect.py --source ./testfiles/img1.jpg --weights runs/train/exp/weights/best.pt --conf-thres 0.3
```

## **测试视频**

```
python detect.py --source ./testfiles/messi.mp4 --weights runs/train/exp/weights/best.pt --conf-thres 0.3
```

## **性能统计**

```
python val.py --data data/voc_ball.yaml --weights runs/train/exp/weights/best.pt --batch-size 16
```
