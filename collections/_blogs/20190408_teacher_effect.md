---
layout: default
title: 教員の効果に関するサーベイ
date_post: 20190408
tags: survey
---

<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  displayAlign: "center",
  displayIndent: "2em",
  tex2jax: {
    inlineMath: [['$','$'], ['\\(','\\)']],
    processEscapes: true
  },
  CommonHTML: { matchFontHeight: false }
});
</script>
<script async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS_CHTML"></script>

# 教員の効果
教員が生徒の教育成果に持つ影響について考える。

### 教員免許など
教員の有効性と教員免許はどの様な関係にあるのだろうか。教員の質保証政策の一貫で教員免許の取得を厳しくすることなどが政策ターゲットになることなどがあるが、そもそも教員として資格を取得することが果たして教員としての質を高めるなんていうことはあるのか？

* 小学校 Clotfelter,Ladd, and Vigdor 2006, 2007a, 2007b; Goldhaber and Anthony 2007; Rockoff 2004)

* Clotfelter, C. T., Ladd, H. F., & Vigdor, J. L. (2010). Teacher credentials and student achievement in high school a cross-subject analysis with student fixed effects. Journal of Human Resources, 45(3), 655-681.
  * 高校生(US, North Carolina, 9th-10th)を対象にした分析（高校生を対象にしたものは少ないらしい）
  * Teacherの科目ごとのcredentials(テストスコア)は生徒の成績に正の影響を与える
  * High Credentialsな先生はSESが高い生徒が集まる学校に配分されていて、不公平かも
  * これは単年度のデータしかないんだけど、科目間の生徒の固定効果をコントロールすることでcausal effectを取り出そうとしている。



### 教員効果の測定について
教員の効果を測定する手法として、非常に頻繁に用いられるのは教員付加価値である。これは教育生産関数のインプットというより、むしろアウトプットを評価しているという点に注意しなくちゃいけない。一般に教員能力といえば子供の人的資本を促進するものだと考えるが、ここではその結果である。そのため、この教員効果がインプットにもなりうるという点は別で評価する必要がある。

多くの場合教員効果を推定するときは、次の様なモデル化を行う（Jackson, Rockoff & Staiger(2014)に従っているが、文中での意図と数式が違うと思うで勝手に直している。）。


$$A _ { ijt } = \beta X _ { ijt } + \nu _ { ijt }  \quad where \quad \nu _ { ijt } = \theta _ { j } + \mu _ { jt } + \varepsilon _ { ijt }$$

iは生徒、jは教員、tは時間を指し、Aは教育成果、Xは生徒の個人特性、$\nu$は観察不可能な要因を表す。$\nu$は教員効果$\theta$、クラスルーム効果$\mu$、その他の要因$\varepsilon$で構成されるとする。
上記式から$A _ { i t }  - \beta X _ { i t } $は教員効果$\theta$についての情報を持つがその中には今関心がないノイズである$\mu$と$\varepsilon$を含んでいる。そのため、多くの研究はsingal extraction問題を解くことで教員効果を推定している。

#### Signal Extraction for Teacher Fixed Effect
ノイズを含む信号から真の情報を抽出する問題を一般にsingal extractionと言う。
よく使う定理として次を挙げることができる。

##### signal extraction theorem 

---
$\theta$についてのpriorとして

  $$
\begin{eqnarray}
   E(\theta) &=& m \\ 
   V(\theta) &=& 1/\rho 
 \end{eqnarray}
  $$

とした時に、次の様なシグナルの集合$X = \\{x_i \| i \in I \\}$を受け取るとする。

$$
\begin{eqnarray}
  x_i &=& \theta + \epsilon_i \\\\
   where && \\
  \epsilon_i &\sim& N(0, 1/\rho_i ) \\
  Cov(\epsilon_i, \epsilon_j) &=& 0 (i \neq j)
\end{eqnarray}
$$

この時、$\theta$に関する予想は

$$
\begin{eqnarray}
   E(\theta | X) &=& \frac{\rho}{\rho ^ { \prime }} m 
    + \sum _ { i = 1, i \in I} \frac{\rho_i}{\rho ^ { \prime }} x _ { i } \\ 
   V(\theta | X) &=& 1 / \rho ^ { \prime }  \\
   where && \\
   \rho ^ { \prime } &=& \rho + \sum _ { i = 1, i \in I}  \rho _ { i } 
\end{eqnarray}
$$

となるように更新される。

直感的にはpriorも含めて情報の正確さで重み付けをしていって、fundamental variableを更新していく手続きである。

---


この時、先の教育生産関数の式は教員効果$\theta _ {j}$についての次の様なシグナルなのではないかと考えることができる。

$$ s_{ijt} = A _ { ijt } - \beta X_{ ijt } =  \theta _ {j} + \mu _ {jt} + \varepsilon _ {ijt}$$


ただし先ほどのsignal extractionのセットアップだとシグナルのノイズ間に相関がないというセットアップだったので、このままでは使えない。そのため、次の様なセットアップに書き直す（害はない）。教員jがt期に担当している生徒を$I_{jt}$と書けば、

$$ 
\begin{eqnarray}
s_{jt} &=& \frac{\sum_{i, i \in I_{jt}} s_{ijt}}{\|I_{jt}\|} \\
         &=& \theta _ {j} + \mu _ {jt} + \frac{\sum_{i, i \in I_{jt}} \varepsilon _ {ijt}}{\|I_{jt}\|} \\
         &=& \theta _ {j} + v_{jt}
\end{eqnarray}
 $$

という教員効果$\theta _ {j}$についてのシグナルを毎期受け取ると考えることができる。

もし教員効果$\theta _ {j}$に対するpriorが期待値0及び分散$var(\theta)$であり、上記シグナルをt期分受け取ると上記のsignal extraction定理より(そのシグナルの集合を$s_j = \\{s_{jt} \| t \in T \\}$と書くことにする)、

\begin{eqnarray}
   E(\theta | s_j ) &=& \sum_{t, t \in T} s_{jt} \frac{ \frac{1}{var(v_{jt})} }{ \frac{1}{var(\theta)} + \frac{1}{\sum_{t, t \in T} var(v_{jt})} }
\end{eqnarray}

と教員jの効果$\theta$の期待値を書くことができる。

多くの場合は得られたデータから、$var(\theta)$や$var(v_{jt})$を無理やり（？）計算して妥当性の高いpriorを構成した後、期待値を計算することが多い。

###### Lefgren&Sims(2012)でのさらなる縮約
さらに、Lefgren&Sims(2012)などはシグナルをさらに集約して、
\begin{eqnarray}
s_{j} = \theta _ {j} + \frac{\sum_{t, t \in T} v_{jt}}{\|T\|}
\end{eqnarray}
と書いて、$var(\frac{\sum_{t, t \in T} v_{jt}}{|T|}) = \frac{var(v_j)}{|T|}$と書くことで($var(v_j)$というものをどっかから調達してくるということ)、

$$ 
\begin{eqnarray}
   E(\theta | s_j ) 
   &=& s_{j} \times \frac{ \frac{1}{\frac{var(v_j)}{|T|}}}{ \frac{1}{var(\theta)} + \frac{1}{\frac{var(v_j)}{|T|}} } \\
   &=& s_{j} \times \frac{var(\theta)}{var(\theta) + \frac{var(v_j)}{|T|}}
\end{eqnarray}
$$ 

と教員効果を構成している。

（
ただし初期の研究では、クラスの効果と教員の効果を分けていない研究も結構ある。
> The earliest studies by Hanushek and Murnane, as well as work by Nye et al. (2004), did not distinguish between classroom and teacher effects. This limitation is essentially what separates these early studies from more recent work, beginning with Rockoff (2004), Rivkin et al. (2005), and Aaronson et al. (2007). In nearly all studies in this literature, teacher effects are assumed to be fully persistent or fixed across classrooms. We discuss recent papers that relax this assumption below.

）

* Kane, T. J., & Staiger, D. O. (2008). Estimating teacher impacts on student achievement: An experimental evaluation (No. w14607). National Bureau of Economic Research.

* Chetty R, Friedman JN, Rockoff JE. 2013a. Measuring the impacts of teachers I: evaluating bias in teacher value-added estimates. NBER Work. Pap. 19423

* Lefgren, L., & Sims, D. (2012). Using subject test scores efficiently to predict teacher value-added. Educational Evaluation and Policy Analysis, 34(1), 109-121.
  個人的には一番丁寧かつ、subject別ではない取り出しみたいな取り組みをしていて面白かった。

* Jackson, C. K., Rockoff, J. E., & Staiger, D. O. (2014). Teacher effects and teacher-related policies. Annu. Rev. Econ., 6(1), 801-825.

良いサーベイ。

* ECONOMETRIC METHODS OF SIGNAL EXTRACTION by D.S.G. POLLOCK
シグナル抽出に関するサーベイ



それで教員の評価をするときは多くは次の式を推定する。
  * We observe teachers with a finite number of classrooms and students, and estimates of teacher effects will therefore contain estimation error. Researchers typically use an empirical Bayes ap- proach to incorporate this into teacher effect estimates (see Kane & Staiger 2008, Chetty et al. 2013a). 

  THE FAILURE OF INPUT-BASED SCHOOLING POLICIES



