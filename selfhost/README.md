第1世代: Ruby版 v3 コンパイラ

```sh
# テスト
rake test_v3
```

```sh
# コンパイル
../pricc ../examples/fibonacci.pric > fibonacci.exe.txt

# 実行ファイルを VM で実行
../pricvm fibonacci.exe.txt

# コンパイル＋実行
../pricrun ../examples/fibonacci.pric
```

第2世代: Pric版 v3 コンパイラ

```sh
# テスト
./test.sh all
```

```sh
mkdir -p exe

# 第2世代コンパイラでライフゲームをコンパイル
./pricc ../examples/game_of_life.pric > exe/game_of_life.exe.txt

# VM で実行
VERBOSE=1 SKIP=1000 ../pricvm exe/game_of_life.exe.txt

# コンパイル＋実行
VERBOSE=1 SKIP=1000 ./pricrun ../examples/game_of_life.pric
```

```sh
# (1) 第1世代コンパイラで第2世代コンパイラをコンパイル
# (2) (1) で生成された実行ファイル（第2世代コンパイラ）で第2世代コンパイラ自身をコンパイル

# 上記 (1), (2) の出力（実行ファイル）が一致することを確認:
./test_selfhost.sh
# （作者の環境だと 15分程度）
```
