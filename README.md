# R-data-frame-handling
R data frame handling (memo)


##  <span style="color: `#007AFF`">重複なしのrownamesを作成</span>
ref) https://staffblog.amelieff.jp/entry/2021/10/05/120000

```r
# using make.names() function
genes.df[[1]] <- make.names(genes.df[[1]], unique=TRUE)
```

## NA処理について
ある列にNAが入った場合，　同じ行にある列の要素を代入するやり方 https://anpontan382.hatenablog.com/entry/2017/05/07/223539
```r
## １列目のNAの要素を3列目で置き換える
genes.df[[1]][which(is.na(genes.df[[1]]))] <-
  genes.df[[3]][which(is.na(genes.df[[1]]))]
```

##　重複行を置換する機能
重複を見つけ出し，　重複があった場合には別の列を参照し，その値を入れる
```r
# 3列目の重複部分について，1行目を代入する
  genes.df[[3]][which(duplicated(df.merge[[3]]))] <- 
    df.merge[[1]][which(duplicated(df.merge[[3]]))]
```
