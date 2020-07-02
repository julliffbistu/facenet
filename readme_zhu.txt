
https://blog.csdn.net/ctwy291314/article/details/81142969






1. tuxiang zhuanchicun

 sudo python align_dataset_mtcnn.py /home/zhulifu/Desktop/facenet/data/lfw_data/lfw /home/zhulifu/Desktop/facenet/data/lfw_data/lfw_160 --image_size 160 --margin 32 --random_order --gpu_memory_fraction 0.25 


2.

sudo python3 src/validate_on_lfw.py /home/zhulifu/Desktop/facenet/data/lfw_data/lfw_160/ /home/zhulifu/Desktop/facenet/src/models/20180408-102900.pb



3.cha kan liangfutu de oushijuli

sudo  python src/compare.py /home/zhulifu/Desktop/facenet/src/models/20180408-102900.pb /home/zhulifu/Desktop/facenet/data/images/Anthony_Hopkins_0001.jpg /home/zhulifu/Desktop/facenet/data/images/Anthony_Hopkins_0002.jpg --gpu_memory_fraction 0.25


4. zhuan .pik wenjian



    模式= TRAIN：

    使用来自数据集的计算出来的向量来训练分类器 
    将训练好的分类模型保存为python pickle文件

    模式= CLASSIFY：

    加载分类模型
    使用来自数据集测试部分的嵌入来测试分类器

A:
 sudo python src/classifier.py TRAIN  /home/zhulifu/Desktop/facenet/data/lfw_data/lfw_160/  /home/zhulifu/Desktop/facenet/src/models/20180408-102900.pb  /home/zhulifu/Desktop/facenet/src/models/my_classifier.pkl

B:
python src\classifier.py CLASSIFY D:\eclipse-workspace\facenet-master\data\face_store\new D:\eclipse-workspace\facenet-master\models\20180408-102900 D:\eclipse-workspace\facenet-master\models\classifier.pkl



5. ce shi xiaoguo
调用facenet-master\contributed\predict.py

sudo python contributed/predict.py  /home/zhulifu/Desktop/facenet/data/images/Anthony_Hopkins_0001.jpg /home/zhulifu/Desktop/facenet/src/models/20180408-102900.pb  /home/zhulifu/Desktop/facenet/src/models/my_classifier.pkl


6. diao yong she xiang tou
摄像头识别人脸效果
修改contributed目录下的face.py


gpu_memory_fraction = 0.3
facenet_model_checkpoint = os.path.dirname(__file__) + "/../model_checkpoints/20170512-110547"
classifier_model = os.path.dirname(__file__) + "/../model_checkpoints/my_classifier_1.pkl"
debug = False

gai wei:


gpu_memory_fraction = 0.3
facenet_model_checkpoint ="/home/zhulifu/Desktop/facenet/src/models/20180408-102900.pb"
classifier_model ="/home/zhulifu/Desktop/facenet/src/models/my_classifier.pkl"
debug = False



sudo python contributed/real_time_face_recognition.py















