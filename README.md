# 課題
Mermaidを触ってみよう

マークダウンファイルを編集して、Mermaidで図を描いてみよう

# 取り組み方
* 本プロジェクトをforkしてください。
* README.mdを編集して、Mermaidを使いこなしてください
* できたらプルリクエストを出します

# 課題項目
## 流れ図
### 条件
- 開始と終了ノードをつける
- 条件分岐を組み込む
- 5ノード以上
- カッコいいほど高得点

## 解答
-テーマ:数当てゲーム
```mermaid
flowchart TD;
  A([ゲーム開始]) --> B[答えの数字生成]
  B --> C[/プレイヤー入力/]
  C --> D{プレイヤーの入力<答え} 
  D -- 真 --> E[正解のほうが大きい旨を伝える]
  E --> C
  D -- 偽 --> F{プレイヤーの入力>答え} 
  F -- 真 --> G[正解のほうが小さい旨を伝える]
  G --> C
  F -- 偽 --> H[正解の旨を伝える]
  H -->I([終了])
```

## シーケンス図
### 条件
- 3人以上
- メッセージをやり取りしない人がいないように
- 自己呼び出しを含むこと
- カッコいいほど高得点

## 解答
-テーマ:カラオケの会員登録

```mermaid
sequenceDiagram
  participant お客
  participant 店員
  participant PC
  お客->>サーバ: 会員情報を入力
  サーバ->>お客: 受付番号発行
  お客->>店員: 受付番号提示
  店員->>PC: 受付番号入力
  PC->>サーバ: 受付番号提供
      loop サーバ処理
      サーバ->>サーバ: 受付番号確認
  end
  サーバ->>PC: 本人確認画面を表示
  店員->>お客: 身分証提示を要求
  お客->>店員: 身分証を提示
  店員->>PC: 身分証情報を入力
  PC->>サーバ: 身分証情報を提供
  loop サーバ処理
      サーバ->>サーバ: 受付番号確認
  end
  サーバ-->>お客: 会員登録完了のメッセージ
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
-テーマ:大学内の人 

```mermaid
classDiagram
人 o-- 学生
人 o-- 従業員

人 o-- 外国人
人 o-- 自国人

人 o--男性
人 o--女性

人 : 役割
人 : 性別
人 : 国籍

学生<|--学部生
学生<|--博士課程学生

従業員<|--教員
従業員<|--事務員

教員<|--准教授
教員<|--教授
教員<|--助教
```
