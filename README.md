
# 概要
kaggleのTitanicのデータセットを用いて、決定木により分類モデルの構築、評価を行う。

# 使用データ

データの出典([https://www.kaggle.com/datasets/yasserh/titanic-dataset])

データの形式(CSV)  

zipファイル形式でダウンロード

# 環境、依存ライブラリ
python(3.12.9),pandas,scikit-learn

# データの理解
乗客が生き残ったかどうかが'Survived' カラムに 0 or 1で記録されている。  
説明変数となるカラムは量的データと質的データが存在している。(今回は量的データのみを説明変数として使用)  
欠損値は下記の通りであった  

Sex              0  
Age            177  
SibSp            0  
Parch            0  
Ticket           0  
Fare             0  
Cabin          687  
Embarked         2  

なお今回は欠損値の削除、補完は行っていない。  

# モデルの構築
scikit-learnのtreeからDecisionTreeClassifierをインポートし、決定木のモデルを作成する。  
fitメソッドによりモデルの学習を行う。  

# モデルの評価
scoreメソッドにより正解率を確認する。  
*0.9528619528619529*  
表示された結果から今回は95%の正解率であった。  
しかし、訓練用データとテスト用データの分割を行っていないため、スコアが高く出ていると考えられる。  
