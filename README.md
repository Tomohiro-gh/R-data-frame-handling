# R-data-frame-handling
R data frame handling (memo)


### 重複なしのrownamesを作成
ref) https://staffblog.amelieff.jp/entry/2021/10/05/120000
```
genes.df[[1]] <- make.names(genes.df[[1]], unique=TRUE)
```

