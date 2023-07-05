# 「アルゴリズムとデータ構造に関するコードデータのアノテーションとその分析」のデータ

「アルゴリズムとデータ構造に関するコードデータのアノテーションとその分析」の問題及び解答ソースコード, 収集した生データやそれを加工したデータを保存しているものです.

## 説明

- `problems`: 問題及び解答ソースコード
  - `problems.md`: 30 問の問題一覧(AtCoder, AOJ, 自作問題へのリンク一覧, Markdown ファイル)
  - `answers`: 30 問分の解答ソースコード(python ファイル)
- `dataset`: 収集した生データ及びそれを加工したデータ
  - `raw`: 生データ(csv ファイル)
    - 日付順でソートしてあります.
    - 実験参加者の氏名やメールアドレスは個人情報保護のため, ID に変換しております.
  - `processed`: 加工したデータ
    - `problem`: 問題ごとにファイルを分けたデータ(csv ファイル)
    - `participant`: 実験参加者ごとにファイルを分けたデータ(csv ファイル)
  - `labeled`: ラベリングを実施した後のデータ
    - `data_labeled_all.csv`: 全てのデータに対してラベリングしたデータ(csv ファイル)
    - `label_content.csv`: ラベルの ID とラベル名のデータ(csv ファイル)
      - ラベルの詳細については, 下記発表文献の論文中の記載をご確認ください.
  - `visualization` : 問題ごとに重要な行と理由を可視化したデータ(Markdown ファイル)

## 発表文献

- 香取 浩紀, 山本 恒輔, 佐藤 安理沙 ジエンジエラ, 矢谷 浩司 (東京大学 Interactive Intelligent Systems Laboratory). アルゴリズムとデータ構造に関するコードデータのアノテーションとその分析. 2023. DICOMO.
