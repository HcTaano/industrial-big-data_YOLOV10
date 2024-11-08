# industrial-big-data_YOLOV10

---
created: 2024/6/29 15:27 <br>
modified: 2024/6/29 16:00 <br>
author: jingbin.Wei <br>
tags: 本科课业 
---

## task:
**工业大数据课程作业，使用yolov10模型进行SMT检测**

## CLI指令
*这里是我在训练验证推理时使用的指令，可以根据需要和情况自行调整相关参数*

**训练指令**
```bash
yolo detect train data=smt.yaml model=yolov10n.yaml epochs=50 batch=64 imgsz=320 device=0
```
- 可根据电脑配置自行调整

**验证指令**
```
yolo detect val model=D:\Users\lostW\Documents\09PythonProject\SMT\yolov10\runs\detect\train14\weights\best.pt data=smt.yaml batch=128 conf=0.485
```
- conf可选，第一次验证建议使用默认值
- 模型权重路径应更改为自己的pathtobest.pt

**推理指令**
```
yolo detect predict model=D:\Users\lostW\Documents\09PythonProject\SMT\yolov10\runs\detect\train14\weights\best.pt source=D:\Users\lostW\Documents\09PythonProject\SMT\datasets\pred\pathtoimg conf=0.485 imgsz=320/1536/1600/1440
```
- conf可选，第一次验证建议使用默认值
- 模型权重路径应更改为自己的pathtobest.pt
- pathtoimg应更改为自己的用来预测图像文件或者文件夹
- imgsz后的值分别对应a组，b1,b2,c1预测时较好的缩放尺寸，建议使用这些尺寸
