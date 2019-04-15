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
教員が生徒の教育成果に持つ影響について考えた論文をまとめる。例によって論文読んだ時のメモとして残しており、校正などは一切おこなっていないことをご了承ください。


<!-- ##### 回帰分析における説明割合
https://stats.stackexchange.com/questions/203540/explaining-the-variance-of-a-regression-model -->

## 教授方法の影響
* Algan, Yann, Pierre Cahuc, and Andrei Shleifer. 2013.   “Teaching   Practices   and   Social   Capital.”   American Economic Journal: Applied Economics 5(3): 189–210
  <!-- * 何でこんないいジャーナルに載っているんだ？ -->
  * 学校での指導方法が生徒の信念（協力への志向性みたいなもの）に影響をあたえる
  * 基本的な推定はOLSに学校固定効果などを追加するだけのもの

* Bietenbeck, J. (2014). Teaching practices and cognitive skills. Labour Economics, 30, 143-153.
  * within-student between-subject approach

* Hidalgo-Cabrillana, A., & Lopez-Mayan, C. (2018). Teaching styles and achievement: Student and teacher perspectives. Economics of Education Review, 67, 184-206.
  * within-student between-subject approach 

* Schwerdt, G., & Wuppermann, A. C. (2011). Is traditional teaching really all that bad? A within-student between-subject approach. Economics of Education Review, 30(2), 365-379.
  * 

* Van Klaveren, C. (2011). Lecturing style teaching and student performance. Economics of Education Review, 30(4), 729-739.
  * 教員が教室の前で立って講義している時間と、パーソナルに教えている時間とどっちが有効かを比較。
  * 教員が教室の前で立って講義している時間は特に学力に影響は与えなかった。
  * within-student between-subject approach 

## 教員免許など
教員の有効性と教員免許はどの様な関係にあるのだろうか。教員の質保証政策の一貫で教員免許の取得を厳しくすることなどが政策ターゲットになることなどがあるが、そもそも教員として資格を取得することが果たして教員としての質を高めるなんていうことはあるのか？

* 小学校 Clotfelter,Ladd, and Vigdor 2006, 2007a, 2007b; Goldhaber and Anthony 2007; Rockoff 2004)

* Clotfelter, C. T., Ladd, H. F., & Vigdor, J. L. (2010). Teacher credentials and student achievement in high school a cross-subject analysis with student fixed effects. Journal of Human Resources, 45(3), 655-681.
  * 高校生(US, North Carolina, 9th-10th)を対象にした分析（高校生を対象にしたものは少ないらしい）
  * Teacherの科目ごとのcredentials(テストスコア)は生徒の成績に正の影響を与える
  * High Credentialsな先生はSESが高い生徒が集まる学校に配分されていて、不公平かも
  * これは単年度のデータしかないんだけど、科目間の生徒の固定効果をコントロールすることでcausal effectを取り出そうとしている。

* Monazza Aslam∗, Geeta Kingdon
教員固定効果

## 教員付加価値
### 教員付加価値を用いた教員効果の測定について
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
  && where  \\
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
   && where \\
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

もし教員効果$\theta _ {j}$に対するpriorが期待値0及び分散$V(\theta)$であり、上記シグナルをt期分受け取ると上記のsignal extraction定理より(そのシグナルの集合を$s_j = \\{s_{jt} \| t \in T \\}$と書くことにする)、

\begin{eqnarray}
   E(\theta | s_j ) &=& \sum_{t, t \in T} s_{jt} \frac{ \frac{1}{V(v_{jt})} }{ \frac{1}{V(\theta)} + \sum_{t, t \in T}\frac{1}{ V(v_{jt})} }
\end{eqnarray}

と教員jの効果$\theta$の期待値を書くことができる。

多くの場合は得られたデータから、$V(\theta)$や$V(v_{jt})$を無理やり（？）計算して妥当性の高いpriorを構成した後、期待値を計算することが多い。

###### Lefgren&Sims(2012)でのさらなる縮約
さらに、Lefgren&Sims(2012)などはシグナルをさらに集約して、
\begin{eqnarray}
s_{j} = \theta _ {j} + \frac{\sum_{t, t \in T} v_{jt}}{ \|\| T \|\| }
\end{eqnarray}
と書いて、$V(\frac{\sum_{t, t \in T} v_{jt}}{\|T\|}) = \frac{V(v_j)}{\|T\|}$と書くことで($V(v_j)$というものをどっかから調達してくるということ)、

$$ 
\begin{eqnarray}
   E(\theta | s_j ) 
   &=& s_{j} \times \frac{ \frac{1}{\frac{V(v_j)}{\|T\|}}}{ \frac{1}{V(\theta)} + \frac{1}{\frac{V(v_j)}{\|T\|}} } \\
   &=& s_{j} \times \frac{V(\theta)}{V(\theta) + \frac{V(v_j)}{\|T \|}}
\end{eqnarray}
$$ 

と教員効果を構成している。

（
ただし初期の研究では、クラスの効果と教員の効果を分けていない研究も結構ある。
> The earliest studies by Hanushek and Murnane, as well as work by Nye et al. (2004), did not distinguish between classroom and teacher effects. This limitation is essentially what separates these early studies from more recent work, beginning with Rockoff (2004), Rivkin et al. (2005), and Aaronson et al. (2007). In nearly all studies in this literature, teacher effects are assumed to be fully persistent or fixed across classrooms. We discuss recent papers that relax this assumption below.

）

* Kane, T. J., & Staiger, D. O. (2008). Estimating teacher impacts on student achievement: An experimental evaluation (No. w14607). National Bureau of Economic Research.

* Lefgren, L., & Sims, D. (2012). Using subject test scores efficiently to predict teacher value-added. Educational Evaluation and Policy Analysis, 34(1), 109-121.
  個人的には一番丁寧かつ、subject別ではない取り出しみたいな取り組みをしていて面白かった。

* Chetty R, Friedman JN, Rockoff JE. 2013a. Measuring the impacts of teachers I: evaluating bias in teacher value-added estimates. NBER Work. Pap. 19423
  * 上記の定式化では教員効果を時間を通じて一定としていた。しかしそれはあまりに単純化にすぎるのではないか、ということで時間変動する教員効果を取り出している。教員効果がautocovarianceするような設定にして、直近のテストスコアが教員効果をより強く構成するようなモデルを組んだ。
  * 教員効果の1SDの上昇は0.14もの効果を持つ。
  > Our VA model implies that a 1 standard deviation (SD) improvement in teacher VA raises normalized test scores by approximately 0.14 SD in math and 0.1 SD in English, slightly larger than the estimates in prior studies which do not account for drift.
  * 教員効果がcausalかどうかを考えるために実験を行なった。推定した教員効果を用いたVAを用いた予測がどれくらいforecast errorを出すかを検討することで、causalityを検証した
  * ほか、event studyなどを行なって、良い教員が入った学校や出て行った学校のテストスコアが落ちることなどを確認した。


* Jackson, C. K., Rockoff, J. E., & Staiger, D. O. (2014). Teacher effects and teacher-related policies. Annu. Rev. Econ., 6(1), 801-825.

良いサーベイ。


### 教員付加価値は教員の価値を表現し得ているのか？
chetty(2013, a)によれば教員付加価値に本質的な意味があるか否かという立場には次の観点があるとしている。すなわち、
1. 過去のデータから得られたに過ぎない教員付加価値は本当に教員のcausal impactを表しているのか？
すなわち上記推定式の仮定は成り立たず、教員と生徒間のsortingを反映しているだけではないのか。
2. テストスコアを上昇させるのが得意な教員を見つけているだけでは？
学力についての教員効果はテストスコアを伸ばしているに過ぎず、真に重要なアウトプットに対して効果はなかったのではないのか？

という問題を抱えている。chetty論文がすごいのはこの2つに同時に解決を与えた研究を行ったというところで、正直、これら２つはすでにクリアされている。

* Rothstein 2010

#### 表現できているとしている立場
* Gordon, Kane, and Staiger 2006
* Hanushek 2009

#### 表現できていない立場
* Baker et al. 2010
* Corcoran 2010

## 学校の影響
* Woessmann, L. (2016). The importance of school systems: Evidence from international differences in student achievement. Journal of Economic Perspectives, 30(3), 3-32.
  * 学校の影響について広範に見たサーベイ \\
    * 国際比較した時の教育生産関数を観察する。単純に推定した係数を見ている時と、国レベルに集計して説明割合(accounted variance)を観察して、家庭環境や学校制度の重要性を指摘する一方で、学校のリソースは重要ではないとしている \\
    （ただこれ別に国レベルにしているから、学校制度がほぼ国を言い当てているだけでは？と思ったりする。）
    * Woessmann (2003b, 2005b), Fuchs and Woessmann (2007), and Woessmann et al. (2009). などの類似研究がある。
    * この指摘は少し面白い
      > While most of the international achievement datasets are cross-sectional, Singh (2015) uses a longitudinal dataset that observes individual students at ages 5 and 8 in four developing countries. The findings show that the large cross-country learning gaps between low-performing Peru and high-performing Vietnam (apparent earlier in Table 1) are virtually nonexistent at school-entry age.

      学校入学時には国際的なレベルでの学力差はないらしい。
    * Instruction Timeに関する研究 \\
      指導時間は重要な影響を持っているという指摘。Lavy（2015, within-student between-subject identification), Rivkin and Schiman (2015, within-student between-subject identification) ...またこの辺の研究はbetween subjectを利用しているものが多いのも特徴。 Andrietti (2015)はDIDを用いている。
      Schneeweis(2011)や Ammermueller(2013) などはInstruction TimeがSESによるacievment gapを埋める役割もあると指摘。
    * 教員の「質」 \\
      教員の質とはなんぞや、ということであるがいくつか検討されてきている。
        * 教員の学力、リテラシー：Hanushek,  Piopiunik, and Wiederhold (2014) 、Bietenbeck, Piopiunik, and Wiederhold (2015, a within-student between-subject approach)
        * 教員のサラリー：Dolton and Marcenaro-Gutierrez (2011) 
        * teaching practice: Schwerdt and Wuppermann(2011, within-student between-subject identification ),　Bietenbeck(2014, within-student between-subject identification) , Algan, Cahuc, and Shleifer (2013, cross-sectional model with school fixed effect、AEJ) \\
        これらはmodernなteachingとtraditionalなteachingを分ける傾向があって、traditionalなteachingなテストの成績や事実把握などへの効果を持つのに対して、modernなteachingは論理的思考やセルフコンフィデンスなどに良い影響を持つ可能性を示唆している。
    * School Systems:
      * External Exams: Hanushek and Woessmann(2011a, cross section), Jürges, Schneider, and Büchel (2005, DID),  Lüdemann (2011, DID)
      * School Autonomy: Hanushek, Link, and Woessmann (2013), 
      * Private Competition: West and Woessmann (2010, exogenous variation in the share of private schools across countries)
      * Tracking: Hanushek and Woessmann (2006), Ammermueller (2013), Piopiunik  (2014) 


* Ammermueller,    Andreas,    and    Jörn-Steffen    Pischke. 2009.  “Peer  Effects  in  European  Primary  Schools:  Evidence  from  the  Progress  in  Interna-tional  Reading  Literacy  Study.”  Journal  of  Labor  Economics 27(3): 315–48.

* Freeman, R. B., & Viarengo, M. (2014). School and family effects on educational outcomes across countries. Economic Policy, 29(79), 395-446.
  * 学校固定効果を推定した結果、その固定効果は学校施策や教員のteachingなどとの相関が強いことを報告している。

* Bloom,   Nicholas,   Renata   Lemos,   Raffaella   Sadun,   and   John   Van   Reenen.   2015.   “Does   Management Matter in Schools?” Economic Journal125(584): 647–74

教員を含んだ学校システムの中で重要な事実を記述しようとするサーベイ。
  


## その他
* Can Principals Identify Effective Teachers? Evidence on Subjective Performance Evaluation
上司による評価は本当に当てになるのか？

* 自分用メモ：
  * 戸田市の進学データとかを用いて、教員のその後の影響を調べる。
  * クラスルームエフェクトを推定するために、日本の中学校のデータを用いればいいんじゃないの？用は中学校の教員は複数箇所に配分されているんだから、、、\\
  → これで教員効果の年変動を計測できるのでは？ \\
  → サンプルが少なすぎる問題は複数科目を同時に打ち込むことで解決できるような。。。
