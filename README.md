# hiragana-recognizer
This is a CNN for learning hiragana. It is implemented using Chainer.

## ファイルの内容
* nets.py
  * Describe the definition of neural network
* trainer.py
  * Script to learn DNN (Deep Neural Network), CNN
* inferencer.py
  + Use the network trained by dnn_trainer.py to display the wrong image and its predicted value
* text_generator.py
  + Create traindata.txt and testdata.txt based on the imgs / directory
* image_restorer.py
  + Get 64x64 PNG image from ETL dataset and save in imgs directory

## Moved environment
* Ubuntu 14.04LTS
* Python 3.5.2 (Anaconda)
* Chainer 1.20.0

## Referenced URL
[By handwriting Hiragana recognition, 99.78% accuracy with deep learning] (http://qiita.com/yukoba/items/7a687e44395783eb32b1)

## Data preparation
* [ETL Data Set] (http://etlcdb.db.aist.go.jp/?page_id=2461)
* Download from above
* Answer zip and run image_restorer.py to save the image in imgs
* Optional: running text_generator.py will create new traindata.txt and testdata.txt)

## How to use
For example, if you execute with the following arguments, you will learn 10 epoch with GPU0
```
python trainer.py traindata.txt testdata.txt --gpu 0 --epoch 10
```

## Notes
* The correct answer rate is about 99.5% at maximum.
* With Geforce GTX 980Ti, learning is completed in about 10 minutes
* Memory usage is about 4GB
