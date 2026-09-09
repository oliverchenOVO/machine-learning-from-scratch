# Machine Learning from Scratch Labs

這個作品集整理大二機器學習課程中「先理解演算法，再與 sklearn 對照」的練習。重點不是追求大型資料集分數，而是以 NumPy 實作核心計算，並檢查與標準函式庫的差異。

## 收錄內容

| 主題 | 手刻內容 | 對照／結果 |
| --- | --- | --- |
| Decision Tree | entropy、information gain、遞迴分裂、leaf voting | NumPy 版 Accuracy 0.85；sklearn baseline 0.9474 |
| PCA | 中心化、協方差矩陣、特徵值／特徵向量、投影 | 前兩主成分累計解釋變異 0.9777 |
| PCA + KNN | 歐式距離、最近鄰投票、K 值比較 | 手刻與 sklearn 在該切分皆得到 1.0000 |
| Polynomial Regression | 多項式特徵、最小平方法 `numpy.linalg.lstsq` | 與 sklearn regression 對照 |
| SVM | 簡化版 SMO、polynomial kernel、預測 | NumPy 教學版 Accuracy 0.5667；sklearn baseline 1.0 |

這些分數來自小型教學切分，只用於驗證實作，並不代表一般化效能。特別是 KNN／sklearn SVM 的 1.0 來自很小的 Iris 測試集，README 不將它描述為實際部署表現。

## 資料夾

```text
notebooks/decision-tree/  決策樹手刻版與 sklearn baseline
notebooks/pca-knn/        PCA 手刻／套件比較及 KNN
notebooks/regression/     多項式回歸與最小平方法
notebooks/svm/            簡化版 NumPy SVM 與 sklearn baseline
docs/                     資料來源與公開檢查
```

## 執行

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

Notebook 使用 sklearn 內建的 Iris 與 Breast Cancer Wisconsin (Diagnostic) 資料，不需要將資料檔提交到倉庫。來源與授權見 [DATA_SOURCES.md](docs/DATA_SOURCES.md)。

原課程另有一份 K-means 圖片分割練習；因為它依賴來源尚未確認的圖片，而且迭代參數有不一致，本準備包暫不收錄，避免把無法完整重現的內容包裝成完成成果。
