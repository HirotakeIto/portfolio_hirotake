---
title: "デルタメソッドの復習"
author: "hirotakeito"
date: "2019/7/30"
output: 
  html_document: 
    keep_md: yes
---



## データ

デルタ法の復習をします。
alr3の次のデータを使います


```r
data(Transact)
head(Transact)
```

```
##    t1   t2  time
## 1   0 1166  2396
## 2   0 1656  2348
## 3   0  899  2403
## 4 516 3315 13518
## 5 623 3969 13437
## 6 395 3087  7914
```
## 組み込み関数を使った方法
組み込み関数に `deltaMethod` という関数があり、次の様な感じに使える

```r
m1 = lm(time ~ t1 + t2, data = Transact)
result = deltaMethod(m1, "b1 + b2", parameterNames = paste("b", 0:2, sep = ""))
result
```

```
##         Estimate       SE    2.5 %   97.5 %
## b1 + b2 7.496605 0.365442 6.780352 8.212858
```
この`b1`とか`b2`の変数名は`parameterNames`のオプションで名付けをしている。
名前空間には、回帰結果オブジェクトの`coef`に存在する名前も用いることができる。

```r
m1 = lm(t1 ~ time + t2, data = Transact)
coef(m1)
```

```
##  (Intercept)         time           t2 
## -87.81108357   0.06978828  -0.03802979
```

```r
deltaMethod(m1, "time + (Intercept)")
```

```
##                    Estimate       SE     2.5 %    97.5 %
## time + (Intercept) -87.7413 18.51484 -124.0297 -51.45288
```
felmとかでも同様

```r
m1 = lfe::felm(time ~ t1 + t2 | 0 | 0 | 0, data = Transact)
coef(m1)
```

```
## (Intercept)          t1          t2 
##  144.369443    5.462057    2.034549
```

```r
deltaMethod(m1, "t1 + t2")
```

```
##         Estimate       SE    2.5 %   97.5 %
## t1 + t2 7.496605 0.365442 6.780352 8.212858
```
ただよくわからないのは`felm`オブジェクトを使うと、名前空間を`deltaMethod`を実行する際に使えなくなる。

```r
deltaMethod(m1, "b1 +b2", parameterNames = paste("b", 0:2, sep = ""))
```

```
## Error in eval(g.): object 'b1' not found
```

## おててで計算

次にデルタメソッドをお手手で確認をする。

デルタメソッドは次の様な定理である。$\mu_1$及び$\mu_2$が確率変数だとして、その合成関数$g(\mu_1, \mu_2)$の分布の近似を調べる。

-----------------------------------------------------------

Theorem 3 Suppose the conditions of Theorem 2. Suppose $g$ is a function of two vari-
ables mapped to two variables, that is continuous and also has a derivative $g ^ { \prime }$ at $\left( \mu _ { 1 } , \mu _ { 2 } \right) ,$
and that $g ^ { \prime } \left( \mu _ { 1 } , \mu _ { 2 } \right)$ is non zero. Then

$$
\sqrt { n } \left( g \left( \hat { \mu } _ { 1 , n } , \hat { \mu } _ { 2 , n } \right) - g \left( \mu _ { 1 } , \mu _ { 2 } \right) \right) \rightarrow N \left( 0 , g ^ { \prime } \left( \mu _ { 1 } , \mu _ { 2 } \right) A g ^ { \prime } \left( \mu _ { 1 } , \mu _ { 2 } \right) ^ { T } \right)
$$


$A$ is covariance matrix. 

(from : http://fisher.stats.uwo.ca/faculty/kulperger/SS3858/Handouts/DeltaMethod.pdf)
(from : https://engineering.linecorp.com/ja/blog/delta-method/)

-----------------------------------------------------------
そのため、$g(\mu_1, \mu_2)$は平均$g(\mu_1, \mu_2)$で分散$g ^ { \prime } \left( \mu _ { 1 } , \mu _ { 2 } \right) A g ^ { \prime } \left( \mu _ { 1 } , \mu _ { 2 } \right) ^ { T }$の正規分布で近似できる（ちょっと適当すぎるけど、許してください）。


次の計算結果をお手手で出してみよう。


```r
m1 = lfe::felm(time ~ t1 + t2 | 0 | 0 | 0, data = Transact)
result = summary(m1)
cat("回帰の結果\n")
```

```
## 回帰の結果
```

```r
result
```

```
## 
## Call:
##    lfe::felm(formula = time ~ t1 + t2 | 0 | 0 | 0, data = Transact) 
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -4652.4  -601.3     2.4   455.7  5607.4 
## 
## Coefficients:
##              Estimate Std. Error t value Pr(>|t|)    
## (Intercept) 144.36944  170.54410   0.847    0.398    
## t1            5.46206    0.43327  12.607   <2e-16 ***
## t2            2.03455    0.09434  21.567   <2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 1143 on 258 degrees of freedom
## Multiple R-squared(full model): 0.9091   Adjusted R-squared: 0.9083 
## Multiple R-squared(proj model): 0.9091   Adjusted R-squared: 0.9083 
## F-statistic(full model): 1289 on 2 and 258 DF, p-value: < 2.2e-16 
## F-statistic(proj model):  1289 on 2 and 258 DF, p-value: < 2.2e-16
```

```r
cat("デルタメソッドでの合成関数の分布の出力\n")
```

```
## デルタメソッドでの合成関数の分布の出力
```

```r
deltaMethod(m1, "t1 + t2")
```

```
##         Estimate       SE    2.5 %   97.5 %
## t1 + t2 7.496605 0.365442 6.780352 8.212858
```

期待値は合成関数にそのまま、それぞれの確率変数の期待値を合成関数に突っ込んでおしまい

```r
cat(coef(result)['t1', 'Estimate'] + coef(result)['t2', 'Estimate'])
```

```
## 7.496605
```
分散は合成関数の微分情報を共分散に掛け合わせる。

```r
g1 = deriv(~ t1 + t2, c("t1", "t2"), func = T)  # 複数関数の微分。これ元々の関数をそのまま値を返す機能もあるから、要調査
t1 = coef(result)['t1', 'Estimate']
t2 = coef(result)['t2', 'Estimate']
cov = vcov(m1)[c('t1', 't2'), c('t1', 't2')]
variance = attr(t(g1(t1, t2)), "gradient") %*% cov %*% t(attr(t(g1(t1, t2)), "gradient"))
variance
```

```
##           [,1]
## [1,] 0.1335478
```

```r
cat("標準誤差で表示すると")
```

```
## 標準誤差で表示すると
```

```r
variance**(1/2)
```

```
##          [,1]
## [1,] 0.365442
```
と求めたい値が求まった。
