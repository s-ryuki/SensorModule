SensorModule
============
　ロボットに実装されたセンサの計測値を受け取り、出力を行うコンポーネントです。  
　このコンポーネントを利用することでフィードバック制御などが行えるようになります。  
　  
コンポーネントの仕様
--------------------
  ロボットに実装されたセンサの計測値を受け取り、出力を行うコンポーネントです。
　　　　[![画像1][image1]](https://github.com/downloads/s-ryuki/Pictures/SensorModule_Comm.png)
[image1]:https://github.com/downloads/s-ryuki/Pictures/SensorModule_Comm.png

　OutPortからはセンサの番号とセンサ値がTimedlongSeq型で出力されます。
  提供するプログラムはmbed NXP LPC1768ですが、SensorModuleの通信プロトコルに沿ってシリアル通信でき、またAD変換可能でできればどのようなマイコンでも使用可能です。

使用方法
--------
　　　　(1)PCとセンサを接続します。  
　　　　(2)接続したCOMポート番号を確認し、sensor.iniを編集します。  
　　　　(3)sensor.iniで使用するセンサの数等を編集し保存します。  
　　　　(4)SensorModule.pyを起動します。  
　　　　(5)RTSytemEditor上でHumanInterfaceまたはそれに準ずるコンポーネントと繋ぎActivateします。  
　  
　このコンポーネントは複数のセンサを用いることが可能です。  
　sensor.iniで受け取るセンサの数、センサ値の個数、センサデータの大きさを設定する必要があります。
　  
　　　　　[![画像2][image2]](https://github.com/downloads/s-ryuki/Pictures/SensorModule_ini.png)
[image2]:https://github.com/downloads/s-ryuki/Pictures/SensorModule_ini.png

####　　　　　画面説明####
　　　　　　　　①接続したセンサのCOMポート番号   
　　　　　　　　②使用するセンサやマイコンの通信ボーレート  
　　　　　　　　③タイムアウト  
　　　　　　　　④使用するセンサの個数  
　　　　　　　　⑤各センサの情報  
　　　　　　　　　　　datanam_1 = 2：データの番号  
　　　　　　　　　　　getdata_1 = 3：センサ値の個数  
　　　　　　　　　　　unitlength_1byte = 2：出力するセンサ値の大きさ  
　  
　　例えば現在市販されているヒューマノイドロボットには加速度センサ（Gセンサ）の他にジャイロセンサや測距センサ、  
　力覚センサ等を搭載したものもあります。
　これらを搭載することで、より研究用ロボットに近いヒューマノイドにすることが可能です。
　  
　なお、SensorModuleのShellにはセンサ番号とセンサ値が表示されます。  
　　　　　　[![画像3][image3]](https://github.com/downloads/s-ryuki/Pictures/SensorModule_shell2.png)
[image3]:https://github.com/downloads/s-ryuki/Pictures/SensorModule_shell2.png
