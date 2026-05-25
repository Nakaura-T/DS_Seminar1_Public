# データファイル

本ディレクトリには、授業で使用するサンプルデータセットを配置します。

## 📊 データセット一覧

### 基本データセット
以下のデータセットは授業で使用します：

- **iris.csv** - アヤメの分類データ（第2-4回）
- **titanic.csv** - タイタニック号乗客データ（第2-5回）
- **wine.csv** - ワインの品質データ（第6回）

### データの取得方法

#### 方法1：scikit-learnから取得（推奨）
多くのデータセットはscikit-learnに含まれています：

```python
from sklearn.datasets import load_iris, load_wine
import pandas as pd

# Irisデータセット
iris = load_iris()
iris_df = pd.DataFrame(iris.data, columns=iris.feature_names)
iris_df['species'] = iris.target

# Wineデータセット
wine = load_wine()
wine_df = pd.DataFrame(wine.data, columns=wine.feature_names)
wine_df['target'] = wine.target
```

#### 方法2：直接ダウンロード
一部のデータセットは以下からダウンロードできます：

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php)
- [Kaggle Datasets](https://www.kaggle.com/datasets)
- [Seaborn Datasets](https://github.com/mwaskom/seaborn-data)

## 📝 データの説明

### Iris（アヤメ）データセット
- **サンプル数**：150
- **特徴量**：4（がく片の長さ・幅、花弁の長さ・幅）
- **クラス**：3種類（Setosa, Versicolor, Virginica）
- **用途**：分類問題の基礎

### Titanic（タイタニック号）データセット
- **サンプル数**：891（訓練データ）
- **特徴量**：年齢、性別、客室クラス、運賃など
- **目的変数**：生存/死亡
- **用途**：二値分類、データ前処理の学習

### Wine（ワイン）データセット
- **サンプル数**：178
- **特徴量**：13（アルコール度数、色の濃さなど）
- **クラス**：3種類
- **用途**：多クラス分類、クラスタリング

## ⚠️ 注意事項

### データの取り扱い
- 本授業では公開データセットのみを使用します
- 実際の医療データは使用しません（倫理的配慮）
- データの著作権・ライセンスを確認してください

### ファイルサイズ
- 大きなデータファイル（>10MB）はGitにコミットしないでください
- 必要に応じて`.gitignore`に追加してください

### Google Colabでの利用
Colabでは、以下の方法でデータを読み込めます：

```python
# GitHubから直接読み込み
url = 'https://raw.githubusercontent.com/[ユーザー名]/DS_Seminar1/main/data/iris.csv'
df = pd.read_csv(url)

# またはscikit-learnから
from sklearn.datasets import load_iris
iris = load_iris()
```

## 📚 参考リンク

- [Pandas データ読み込みガイド](https://pandas.pydata.org/docs/user_guide/io.html)
- [scikit-learn データセット](https://scikit-learn.org/stable/datasets.html)
- [Seaborn サンプルデータ](https://github.com/mwaskom/seaborn-data)

---

**Last updated**: 2026-02-14
