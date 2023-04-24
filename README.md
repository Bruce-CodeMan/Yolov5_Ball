<!--
 * @Date: 2023-04-24 09:05:55
 * @Author: Bruce
 * @Description: 
-->
# Yolov5_Ball

## 环境的安装

```
pip install -r requirements.txt
```

## 数据集的训练

```
1. 将准备好的数据集放到根目录下,并解压
2. 使用处理数据脚本prepare_data.py
3. 修改data目录下的文件voc_ball.yaml文件,改成自己的训练路径,类别编号
4. 修改models目录下的文件yolov5s_ball.yaml, 修改类别的数目
```

## ==开始训练==

```
python train.py --data data/voc_ball.yaml --cfg models/yolov5s_ball.yaml --weights weights/yolov5s.pt --batch-size 16 --epochs 50 --workers 4
```