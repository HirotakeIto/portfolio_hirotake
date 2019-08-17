---
layout: blog
title: 教員や学校の効果に関するサーベイ
date_post: 20190408
tags: survey
hidden: false
---

## 教員の効果
教員が生徒の教育成果に持つ影響について考えた論文をまとめる。例によって論文読んだ時のメモとして残しており、校正などは一切おこなっていないことをご了承ください。


<!-- ##### 回帰分析における説明割合
https://stats.stackexchange.com/questions/203540/explaining-the-variance-of-a-regression-model -->
## 教員の個人特性
* Hanushek, E. A., & Rivkin, S. G. (2006). Teacher quality. Handbook of the Economics of Education, 2, 1051-1078.
  * 教員の個人特性が子どもの教育成果に与える影響としてconsistentなものは発見されていない

* Chingos, M. M., & Peterson, P. E. (2011). It's easier to pick a good teacher than to train one: Familiar and new results on the correlates of teacher effectiveness. Economics of Education Review, 30(3), 449-465.

* Goldhaber, D., Liddle, S., & Theobald, R. (2013). The gateway to the profession: Assessing teacher preparation programs based on student achievement. Economics of Education Review, 34, 29-44.


### 経験年数
* Harris, D. N., & Sass, T. R. (2011). Teacher training, teacher quality and student achievement. Journal of public economics, 95(7-8), 798-812.
  * 経験年数
  * 過去の調査のサーベイは綺麗で見やすい。彼によると2000年以降、パネルデータでstudentFEを採用した研究は８個ある。
    モダンな小学校国語：多くの研究が有意と報告、小学校算数：有意も非有意もある、中学校国語：有意も非有意もある、中学校算数：多くが有意と報告。

* Papay, J. P., & Kraft, M. A. (2015). Productivity returns to experience in the teacher labor market: Methodological challenges and new evidence on long-term career improvement. Journal of Public Economics, 130, 105-119.

* Wiswall, M. (2013). The dynamics of teacher quality. Journal of Public Economics, 100, 61-78.
  * "I find that for mathematics achievement there are high returns to later career teaching experience, about twice as much dispersion in initial teacher quality as previously estimated, and a pattern of negative selection where high quality teachers are more likely to exit."

* Ost, B. (2014). How do teachers improve? The relative importance of specific and general human capital. American Economic Journal: Applied Economics, 6(2), 127-51.
  * 教員のqualityがキャリアでどのように変容するか？それがgeneralなhuman capitalなのか、specific curriculum familiarityにすぎないかを識別して、specific experienceは直近の経験の方が昔の経験に比べてよっぽど高いことを示している。

### 教員給与

### 教員免許など
教員の有効性と教員免許はどの様な関係にあるのだろうか。教員の質保証政策の一貫で教員免許の取得を厳しくすることなどが政策ターゲットになることなどがあるが、そもそも教員として資格を取得することが果たして教員としての質を高めるなんていうことはあるのか？

* 小学校 Clotfelter,Ladd, and Vigdor 2006, 2007a, 2007b; Goldhaber and Anthony 2007; Rockoff 2004)

* Clotfelter, C. T., Ladd, H. F., & Vigdor, J. L. (2010). Teacher credentials and student achievement in high school a cross-subject analysis with student fixed effects. Journal of Human Resources, 45(3), 655-681.
  * 高校生(US, North Carolina, 9th-10th)を対象にした分析（高校生を対象にしたものは少ないらしい）
  * Teacherの科目ごとのcredentials(テストスコア)は生徒の成績に正の影響を与える
  * High Credentialsな先生はSESが高い生徒が集まる学校に配分されていて、不公平かも
  * これは単年度のデータしかないんだけど、科目間の生徒の固定効果をコントロールすることでcausal effectを取り出そうとしている。


## 教授方法の影響
多くの研究で言われている流れとして、教員の履歴書上の特性は教育成果に対して重要ではなく、その一方て教授方法とかそのプロセスは非常に重要なのではないかということがある（Aslam & Kingdom、HanushekのTQ論文とか）。

* Goldhaber, D. D., & Brewer, D. J. (1997). Why don't schools and teachers seem to matter? Assessing the impact of unobservables on educational productivity. Journal of Human Resources, 32(3), 505-524.

* Jackson, C. K., & Bruegmann, E. (2009). Teaching students and teaching each other: The importance of peer learning for teachers. American Economic Journal: Applied Economics, 1(4), 85-108.
  * 生徒が自身の担任のピアの教員から受ける影響を推定

  * リフレクションプロブレムの問題をどうやってクリアするか

    * 使う変数は外生的に決まる変数

    " To avoid the reflection problem (Charles F. Manski 1993), we use two measures of peer quality that are not determined by contact with peers: observable peer characteristics that change exogenously, such as experience and certification test scores; and unobservable peer quality based on teacher-specific, time-invariant, value-added estimates from pre-sample data."

    まあこれはわかる。でもピアの定義にはいまだに内生性が残りうる。（後述するが）ある教員のピアの定義は、所属する学校の所属する学年の教員。つまりセレクションが発生しうるところとして、「学校」と「学年」がある。

    （悩み）次にそのセレクションを除くための固定効果を考えるんだけど、ここをもっとシステマティックに出せないかな、、、と。今のところ職人的な気がする。うううむ。「ある学校に入るのは教員と学校のマッチング」だから、教員固定効果と学校固定効果を入れることがとりあえず必然って感じかな。そんでさらに、time-variant factorにも対応するために、後述の教員学校固定効果や学校年度効果に拡張するって感じかな。

    * セルフセレクションの問題には教員学校固定効果で対処

    "To ensure that we do not use changes in peer quality due to teacher self-selection, we identify the changes in the performance of a teacher's students that are correlated with changes in the composition of her peers within the same school by including teacher-school fixed effects."

    "（私訳）教員のセルフセレクションによるピアの変動を用いないことを保証するため、教員学校固定効果を入れることによって同じ学校の中で教員ピアの変動と相関する生徒たちのパフォーマンスの変動を用いた。"
    
    うーん、セルフセレクションっていうのは「できれば（性質の良い）ピアの学校で教えたいと教員は思う」とかそういう話か？ともかく、ピアの変動は、教員の同じ学校の中でのre-assign、peerの（これは学校に関わらない）re-assignによってのみ起きるってことだな。

    なんで教員固定効果だけじゃダメなんだろう、、、と考えたが、教員が自ら「良い」学校に転職すればピアも良くなるし生徒も良くなるという内生性が発生すると。

    * 教員がランダムアサインではない可能性に対しては学校年度固定効果で対処

    例えばハリケーンを学校が襲って、「良い」教員が学校から退出するとする。同時に子供のパフォーマンスも落ちるとする。こんなような関係があるかもしれないよね。他にも、学校が突然「良い」教員ばっか雇用し始めるとかね。そのため学校年度固定効果で対処。
  
    * 学校学年効果はコントロールできていない
    
    そのため「ある年に突然、ある学年に良い教員を集めた！」みたいなことが起きてたら、バイアス発生。でもそんなことがないのは検証済みだよ。

  * ここでのピアの定義は同じ学校の同じ学年をピアの定義としている。これがかなり重要な想定で、普通に考えたらピアの影響なんて同じ学年だけではなく同じ学校の教員からも受けるはず。それにも関わらず（推定上の都合で）ピアの定義を狭めている。そのためここで分析されるピア効果は、実際のピア効果のlower boundであることに注意しよう。

  * スピルオーバー効果は強いし、特に経験浅い教員だとよりよい同僚を持つことの効果は高いとさ。

* Schwerdt, G., & Wuppermann, A. C. (2011). Is traditional teaching really all that bad? A within-student between-subject approach. Economics of Education Review, 30(2), 365-379.
  * time of lecture–style teachingの時間を増やすことで学力に良い影響
  * variation between subjectを学校固定効果含みで用いている（単年度データだからかな）
  * time of lecture–style teachingが教員の観察不可能な要因とco-foundしているかもしれないから、ある程度の仮定の上で、そのbiasを算出（面白そうなので読みたいが、ちょっとと今は後回し.下記のKlaveren（2011)でも同じことやっているな。。。）

* Van Klaveren, C. (2011). Lecturing style teaching and student performance. Economics of Education Review, 30(4), 729-739.
  * 教員が教室の前で立って講義している時間と、パーソナルに教えている時間とどっちが有効かを比較。
  * 教員が教室の前で立って講義している時間は特に学力に影響は与えなかった。
  * within-student between-subject approach 
  * 気になる：

    "We can evaluate the selection bias due to unobserved teacher characteristics using the approach of Altonji, Elder, and Taber (2005). ""

  * 気になる：

    ”Can measurement error explain the results?”
    実際に変な回答によるバイアスの発生具合をシミュレーションによって分析（これもsignal extractionっぽい）.

  * 効果がなかった論文だからなのか色々調べていて、その方法がいちいち興味深い。

* Aslam, M., & Kingdon, G. (2011). What can teachers do to raise pupil achievement?. Economics of Education Review, 30(3), 559-574.
  * within-student between-subject approach（と思われる）
  * 教員のresume上の特徴はあまり影響ないけど、teaching processとかは教育成果に影響を与える。

* Bietenbeck, J. (2014). Teaching practices and cognitive skills. Labour Economics, 30, 143-153.

  * within-student between-subject approach

* De Witte, K., & Van Klaveren, C. (2014). How are teachers teaching? A nonparametric approach. Education Economics, 22(1), 3-23.
  * モダンティーチングが効果を持つ。
  * DEAモデル（Data Envelopment Analysis)

* Lavy, V. (2015). What makes an effective teacher? Quasi-experimental evidence. CESifo Economic Studies, 62(1), 88-125.
  * traditional teaching style(the instilment of knowledge and comprehension)はgirl & LowSESの子供により強くpositiveな影響を持った
  * modern teachingがサブグループことに大きさ異なるがpositiveな効果があった。
  * なのでtraditional teachingとmodern teachingは共存して、どういう子供に対してそのデータを用いて行くかが重要
  * The identification strategy I use in this paper is most closely related to that of Ammermueller and
Pischke (2009), who use a school-fixed-effects framework to estimate peer effect based on within-school
and across-class variation in peer ability. 
  * Quasi-experimentalと言っているが、何がそれに値するのかよくわからん（普通のwithin school での分析に見える）

* Algan, Yann, Pierre Cahuc, and Andrei Shleifer. 2013.   “Teaching Practices and Social Capital.”   American Economic Journal: Applied Economics 5(3): 189–210
  <!-- * 何でこんないいジャーナルに載っているんだ？ -->
  * 学校での指導方法が生徒の信念（協力への志向性みたいなもの）に影響をあたえる
  * 基本的な推定はOLSに学校固定効果などを追加するだけのもの

* Zakharov, A., Carnoy, M., & Loyalka, P. (2014). Which teaching practices improve student performance on high-stakes exams? Evidence from Russia. International Journal of Educational Development, 36, 13-21.
  * 未読

* Comi, S. L., Argentin, G., Gui, M., Origo, F., & Pagani, L. (2017). Is it the way they use it? Teachers, ICT and student achievement. Economics of Education Review, 56, 24-39.
  * ICTを用いた教育実践の効果（ICT-related teaching practices）
  * ICTの実践方法によって効果が異なり、結局のところ教員がうまくICTを利活用できることであったりすることが重要だろうという結論。
  * within-student between-subject estimator

* Hidalgo-Cabrillana, A., & Lopez-Mayan, C. (2018). Teaching styles and achievement: Student and teacher perspectives. Economics of Education Review, 67, 184-206.
  * 教員と生徒両方の授業方法についての報告をしよう
    * 教員が報告した授業方法：生徒の学力への影響はなし
    * 生徒が報告した授業方法：modern teachingはpositiveな影響を持って、traditional teachingはnegative
  * within-school approach <br>
    （イントロより） <br> 
    「子供の教育成果に対する授業方法の因果効果を得るのは難しい課題である。それは２つのセレクションに対処することを要求する。すなわち、学校間のsortingと学校内のsortingである。私たちの分析手法は学校内のクラス間の授業方法についての及びテストスコア変動を使って、ランダムに発生するとは言えないような生徒や教員の学校間のsortingに対処している。しかし、学校内でのsortingに対処するのは簡単ではない。授業の方法は科目というよりむしろクラスごとに違うものであり、そのため私たちは生徒内変動を用いることができない。またクラスごとに異なる先生（伊藤：原文にはtutorとあるが先生とは別？そんなわけないよね）がいるから、先生内のバリエーションを使うことも難しい。そのため私たちは学校内のsortingがどれくらい結果に対して問題になるかを評価するような分析をを行なった。私たちは学校内で教員のセレクションが発生している証拠を見つけることはできなかった。（省略）。しかし私たちは完全に観察不可能な異質性に対処できたとは言えず、結果的に推定値をcausalだとすることには慎重になる必要がある」

  * 例えば次の様に行った後、within–school selectionがどの程度発生しているかを図ろうとしている。

    "Even after controlling for the endogenous selection of students to schools, unobserved traits of the student (μics) and the teacher (ηcs) may additionally create within–school endogeneity issues and lead to a biased estimate of γ."
    
    この後”3.1. Within–school selection of students, teachers and teaching style”でその程度を測定していて、これは重要なので読んでおく。


* Bessho, S. I., Noguchi, H., Kawamura, A., Tanaka, R., & Ushijima, K. (2019). Evaluating remedial education in elementary schools: Administrative data from a municipality in Japan. Japan and the World Economy, 50, 36-46.
  * 傾向スコアマッチング

* Tanaka, R., & Ishizaki, K. (2018). Do teaching practices matter for students’ academic achievement? A case of linguistic activity. Journal of the Japanese and International Economies, 50, 26-36.
  * 学校固定効果


<!--     Obtaining the causal effect of the teaching styles on student achievement is challenging. It requires dealing with two sources of selection: between–school sorting and within–school sorting. Our empirical strategy relies on the between–class within–school variation in teaching practices and test scores to account for the non–random selection of students and teachers between schools. Dealing with the within–school sorting however is not straightforward. Teaching practices vary at the class level rather than at the subject level and so we cannot rely on within–student variation. We cannot exploit either within–teacher variation since each class has a different tutor. Thus we conduct a thorough analysis to asses to what extent within–school sorting may be an issue for the results. We do not find evidence of within–school selection of teachers, students and teaching styles. Additionally we include a broad set of student and teacher variables in the specification in order to minimize the bias from potential unobserved traits. However, we cannot rule–out completely the presenceof unobserved variables, and consequently we refrain from interpretingour estimates as causal. -->


## 教員付加価値
### 教員付加価値を用いた教員効果の測定について
教員の効果を測定する手法として、非常に頻繁に用いられるのは教員付加価値である。これは教育生産関数のインプットというより、むしろアウトプットを評価しているという点に注意を払う必要がある。すなわち、一般に教員能力といえば子供の人的資本を促進するものだと考えるが、ここではその結果である。そのため、この教員効果がインプットにもなりうるという点は別で評価する必要がある(→教員付加価値のcausal impactを評価する一連の研究)。

多くの場合教員効果を推定するときは、次の様なモデル化を行う（Jackson, Rockoff & Staiger(2014)に従っているが、文中での意図と書かれている数式が違うと思うので勝手に直している。）。


$$A _ { ijt } = \beta X _ { ijt } + \nu _ { ijt }  \quad where \quad \nu _ { ijt } = \theta _ { j } + \mu _ { jt } + \varepsilon _ { ijt }$$

iは生徒、jは教員、tは時間を指し、Aは教育成果、Xは生徒の個人特性、$\nu$は観察不可能な要因を表す。$\nu$は教員効果$\theta$、クラスルーム効果$\mu$、その他の要因$\varepsilon$で構成されるとする。
上記式から$A _ { i t }  - \beta X _ { i t } $は教員効果$\theta$についての情報を持つがその中には今関心がないノイズである$\mu$と$\varepsilon$を含んでいる。そのため、多くの研究はsingal extraction問題を解くことで教員効果を推定している。

#### Signal Extraction for Teacher Fixed Effect
ノイズを含む信号から真の情報を抽出する問題を一般にsingal extractionと言う。
よく使う定理として次を挙げることができる。


##### signal extraction 定理を用いた教員付加価値の推定
--- 
**signal extraction 定理**\\
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

* Chetty, R., Friedman, J. N., & Rockoff, J. E. (2014). Measuring the impacts of teachers I: Evaluating bias in teacher value-added estimates. American Economic Review, 104(9), 2593-2632.
  * 上記の定式化では教員効果を時間を通じて一定としていた。しかしそれはあまりに単純化にすぎるのではないか、ということで時間変動する教員効果を取り出している。教員効果がautocovarianceするような設定にして、直近のテストスコアが教員効果をより強く構成するようなモデルを組んだ。
  * 教員効果の1SDの上昇は0.14もの効果を持つ。
  > Our VA model implies that a 1 standard deviation (SD) improvement in teacher VA raises normalized test scores by approximately 0.14 SD in math and 0.1 SD in English, slightly larger than the estimates in prior studies which do not account for drift.
  * 教員効果がcausalかどうかを考えるために実験を行なった。推定した教員効果を用いたVAを用いた予測がどれくらいforecast errorを出すかを検討することで、causalityを検証した
  * ほか、event studyなどを行なって、良い教員が入った学校や出て行った学校のテストスコアが落ちることなどを確認した。

* Fleche, S. (2017). Teacher quality, test scores and non-cognitive skills: Evidence from primary school teachers in the UK.
  * なんかわからんがこれも学力及び非認知能力両方への影響を見ている。

* Jackson, C. K. (2012). Non-cognitive ability, test scores, and teacher quality: Evidence from 9th grade teachers in North Carolina (No. w18624). National Bureau of Economic Research.
  * 非認知能力（absences, suspensions, grades, and on-time grade progression）に対する影響を見ている。
  * その教員効果は長期的にもpositiveな影響（高校卒業、大学入学）を持っている。
  * 特に英語教員の効果が重要（英語というか国語だよね、これは）


* Hanushek, E. A., & Rivkin, S. G. (2012). The distribution of teacher quality and implications for policy. Annu. Rev. Econ., 4(1), 131-157.
  * サーベイ
* Jackson, C. K., Rockoff, J. E., & Staiger, D. O. (2014). Teacher effects and teacher-related policies. Annu. Rev. Econ., 6(1), 801-825.
  * 良いサーベイ。

* Jacob, B. A., & Lefgren, L. (2008). Can principals identify effective teachers? Evidence on subjective performance evaluation in education. Journal of labor Economics, 26(1), 101-136.

* Carrell, S. E., & West, J. E. (2010). Does professor quality matter? Evidence from random assignment of students to professors. Journal of Political Economy, 118(3), 409-432.


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
学校費は教育関連支出において大きなウェイトを占めるのにもかかわらず、コールマンレポートによって学校の支出は教育達成に影響を与えていないことを報告していらい、学校はどのように子供に影響を持っているかは重要な関心の対象になってきた。

* Assessing the Variance in Pupil Attainment: How Important is the School Attended?
David Wilkinson, Alex Bryson, Lucy Stokes

  学校の重要性の報告


* The Failure of Input‐based Schooling Policies
  "Hanushek (2003) reviews the more recent literature published on this question, and his conclusions echo those of Coleman et al. (1966) ."（Jackson）
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

* Meyer, E., & Van Klaveren, C. (2013). The effectiveness of extended day programs: Evidence from a randomized field experiment in the Netherlands. Economics of Education Review, 36, 1-11.
  * 授業時間を増やすことの影響を調査 → しかし効果はなかった模様
  * フィールド実験

* Freeman, R. B., & Viarengo, M. (2014). School and family effects on educational outcomes across countries. Economic Policy, 29(79), 395-446.
  * 学校固定効果を推定した結果、その固定効果は学校施策や教員のteachingなどとの相関が強いことを報告している。

* Bloom,   Nicholas,   Renata   Lemos,   Raffaella   Sadun,   and   John   Van   Reenen.   2015.   “Does   Management Matter in Schools?” Economic Journal125(584): 647–74

  * 教員を含んだ学校システムの中で重要な事実を記述しようとするサーベイ。

### 学校の支出
* The Effects of School Spending on Educational and Economic Outcomes: Evidence from School Finance Reforms 
C. Kirabo Jackson  Rucker C. Johnson  Claudia Persico
  * 裁判所による学校改革命令（SFR）を外生的なショックとして捉えて分析（何か予測してIVとして利用しているのかな）
  * 学校支出増加が教育達成及び、将来的な労働市場での評価を改善していることを発見
  * 同じSFRを使った研究だとCard and Payne (2002)： significant、Hoxby (2001)：mixed、Downes and Figlio（1998）：insiginificant、Guryan（2001）、Papke（2005）、Roy（2011）：significant in only a stateと効果のほどはvagueだったけど、この研究はかなり手法を洗練させていてしっかりした結果を出したということなのかな。
  * メカニズムとして、ST比の改善と教員の給与の増加と支出の増加が関連あることを発見
  * 学校支出の増加と、disadvantaged studentの増加は相関があった：ここをコントロールしていないから、過去の研究（コールマンレポート）とかは有意な関係性を発見できなかったのでは？



## その他
* Can Principals Identify Effective Teachers? Evidence on Subjective Performance Evaluation
  * 上司による評価は本当に当てになるのか？

* Cordero, J. M., Cristobal, V., & Santín, D. (2018). Causal inference on education policies: a survey of empirical studies using PISA, TIMSS and PIRLS. Journal of Economic Surveys, 32(3), 878-915.
  * PISA, TIMSS and PIRLS に関する分析まとめ

* Gilpin, G., & Kaganovich, M. (2012). The quantity and quality of teachers: Dynamics of the trade-off. Journal of Public Economics, 96(3-4), 417-429.

* 自分用メモ：
  * 戸田市の進学データとかを用いて、教員のその後の影響を調べる。
  * クラスルームエフェクトを推定するために、日本の中学校のデータを用いればいいんじゃないの？用は中学校の教員は複数箇所に配分されているんだから、、、\\
  → これで教員効果の年変動を計測できるのでは？ \\
  → サンプルが少なすぎる問題は複数科目を同時に打ち込むことで解決できるような。。。

