# 深層学習 day４ Section３：軽量化・高速化技術

## 確認テスト１

<p align="center">
    <img src="https://github.com/ontheroad2021/RabbitChallenge/blob/main/images/4_2_3_2_Review_Test_01.png"> 
</p>

解答：

（い）  
ＨｘＷｘＣｘＫｘＫ  

（ＫｘＫ）で出力マップの１ピクセル分は計算できる。  
それが（ＨｘＷｘＣ）必要である。
従って、計算量は、ＨｘＷｘＣｘＫｘＫ となる。 


（う）  
ＨｘＷｘＣｘＭ  

（Ｃ）で出力マップの１ピクセル分は計算できる。  
それが（ＨｘＷｘＭ）必要である。
従って、計算量は、ＨｘＷｘＣｘＭ となる。 

## 確認テスト２

<p align="center">
    <img src="https://github.com/ontheroad2021/RabbitChallenge/blob/main/images/4_2_3_2_Review_Test_02.png"> 
</p>

解答：Dilated causal convolution

## 確認テスト３

<p align="center">
    <img src="https://github.com/ontheroad2021/RabbitChallenge/blob/main/images/4_2_3_2_Review_Test_03.png"> 
</p>

解答：パラメータ数に対する受容野が広い  

Wavenetの工夫というのは、パラメータは既存の畳み込みの手法と同じくらいの数で作りたいのだけども、より長い時間的範囲を上手く使いたいという目標を持っていました。そこでスキップを上手くかませる事でより広い時間の情報を出力時に使用する事ができるようになります。
