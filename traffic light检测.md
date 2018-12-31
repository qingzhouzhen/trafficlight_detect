## traffic light检测

改自https://gluon-cv.mxnet.io/build/examples_detection/train_yolo_v3.html#sphx-glr-build-examples-detection-train-yolo-v3-py

1. ```train_yolo3.py``` warmup-epoch改为4
2. 更改读数据的路径，我这里检测红绿灯，格式与pascal voc数据格式一样就行，可以参考我的另外一篇博客http://www.huanghanqing.com/2018/11/18/gluoncv-yolo3%E8%AE%AD%E7%BB%83%E8%87%AA%E5%B7%B1%E7%9A%84%E6%95%B0%E6%8D%AE%E9%9B%86/
3. 修改检测类别，gluon默认的是20类，改成自己label里包含的类别，这里只检测一类，注意把tuple改成list类，不然读类别的length会报错，```vi /home/xxx/miniconda3/lib/python3.7/site-packages/gluoncv/data/pascal_voc/detection.py```类别改成```CLASSES = ['light']```

##### 训练结果：

```
INFO:root:[Epoch 29] Training cost: 898.358, ObjLoss=13.969, BoxCenterLoss=4.401, BoxScaleLoss=2.256, ClassLoss=0.058
INFO:root:[Epoch 29] Validation: 
light=0.4072734751879137
mAP=0.4072734751879137
```

