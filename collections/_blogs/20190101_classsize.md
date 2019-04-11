---
layout: default
title: クラスサイズに関するサーベイ
date_post: 20190101
tags: survey
---

# クラスサイズ研究のReview Review
## クラスサイズ研究の昔の姿について Old-research
そもそもクラスサイズに関する研究は相当昔まで遡ることができ、例えばそれは戦前にまで遡ることができる(JEPのサーベイに詳しい)。
多くの地域•学校でクラスサイズに関するフィールド実験がなされ、その結果の多くはクラスサイズと成績との間には相関なしというものであった。この研究結果は当時のクラスサイズ政策に大きく影響を与え、クラスサイズ拡大の政策に寄与した。<br>
興味深いのはJEPのサーベイによれば、その背景には出生率の増加に裏打ちされた人口の増加があり多くの児童•生徒に義務教育を施す必要がある中で、どうすれば学業達成を犠牲にすることなくその目標を達成できるかという社会的要請があったという事実であろう。そのため、戦争などで人口が減少しわざわざクラスサイズを大きくする必要性がなくなると、クラスサイズ研究は急速に少なくなったという。

  <blockquote class="blockquote text-left">
    <p class="small">
      As the financial pressure on schools declined, interest in the importance of class size did as well, and class size research all but ceased for the next 15 years.<br>
      <small>
        Rockoff, J. (2009). Field experiments in class size from the early twentieth century. Journal of Economic Perspectives, 23(4), 211-30.
      </small>
    </p>
  </blockquote>


このクラスサイズに関する研究状況が改善するのには戦後になってまたしばらく待つ必要がある。1980年代に入るとある程度の生徒や学校に関するデータセットが揃ってきたこともあり、多くの研究がなされるようになる（メモ：これは感想ですが特に教育学方面で？）。<br>
そこでの解析とは多分にクラスサイズと学業達成の間の単純な関係性を観察するものであり、その意味では学力の生産関数の推定などを多分に性質を同じくするものであった。そのため、今日ではこのころの研究を振り返ることはあまりない（と思う）。

 * Goldstein, H., & Blatchford, P. (1998). Class size and educational achievement: A review of methodology with particular reference to study design. British Educational Research Journal, 24(3), 255-268.

 サーベイペーパー

 * Hanushek, E. A. (1999). Some findings from an independent investigation of the Tennessee STAR experiment and from other investigations of class size effects. Educational Evaluation and Policy Analysis, 21(2), 143-163.

  • 基本的にはサーベイペーパーなのだが、s-t ratio における1994年までのメタアナリシスなども掲載している。
  ![STratioのメタアナリシス](fig/meta_analysis_stratio.png "STratioのメタアナリシス(Hanushek, E. A. (1999)")




しかし90年代後半より、因果推論に関する関心と技術の高まりを背景に、クラスサイズと学業達成、若しくはクラスサイズとそのほかの要素の関係性を見ようという研究が多く登場した。その最もリジッドな例がテネシー州STAR実験の分析であり、またマイモニデスルールに在る外生成を用いた推定で在る。

## クラスサイズ効果についての2つの方向性 Two roads about class size effect
クラスサイズ効果については、モダンな研究としてはおおまかに２つの方法で推定されてきた。即ち、実験環境の利用した推定（RCT）と擬似的な実験環境を利用した推定（マイモニデスルール、Fuzzy RDD）である。<br>
特に前者については、多くの研究がクラスサイズの正の効果（即ち小さいクラスサイズはアウトカムに対して正の効果をもたらす）が認められるとしている。そのためクラスサイズ効果については、概ね存在が確認されていると言っていいだろう。<br>
一方で、後者については初期の研究では正の効果を報告しているものが多い一方で、効果がないとしている研究も多くあることに注意が必要である。

## RCT
### STAR実験について Star experience
#### STAR実験のおおまかな構成について
STAR実験は以下の様に実施された、大規模なクラスサイズに関するフィールド実験である。  

  <blockquote class="blockquote text-left">
  <p class="small">
    The largest class size experiment  ever conducted, it involved the participation of 79 schools, 328 classes, and roughly 6,500 students when it began in 1985. Students and teachers were randomly assigned to small or large classes (averaging 15 or 23 students, respectively) from kindergarten through third grade, and students have been followed over time.<br>
    <small>
      <br>
      &emsp;Rockoff, J. (2009). Field experiments in class size from the early twentieth century. Journal of Economic Perspectives, 23(4), 211-30.<br>
      <br>
      ToDo : この論文20世紀初頭のCSRに関する研究のサーベイなので、これを引用するのは変<br>
    </small>
  </p>
  </blockquote>

#### STAR実験の結果
STAR実験のデータを用いた解析では、おおまかに次の様な結果が出ている。即ち、

  1. 実験開始後クラスサイズ縮小が学力にポジティブに機能している(Krueger(1999))
  2. ただし、そのクラスサイズ縮小が効果を持ったのは、小さい学年（幼稚園及び小学校1年生や2年生）である (Hanushek(1999))
  3. 実験終了後、数年は効果を持っている(Schanzenbach(2006))
  4. また非認知能力(成長後の逮捕率と10代妊娠率)に有意な効果を持っている(Schanzenbach(2006))
  5. 大人になってからの諸々の能力（賃金、出席率、持ち家率）などにも効果を持っている。(Chetty et al. 2011)

また重要な非線形性として以下の様な点が報告されている。

  * 経験豊富な教師の方が、高い効果を持った(Schanzenbach(2006))

またSTAR実験をどう受け止めるかについては議論があり、例えばhanushekは次の様な点をあげている。

* Hanushek, E. A. (1999). Some findings from an independent investigation of the Tennessee STAR experiment and from other investigations of class size effects. Educational Evaluation and Policy Analysis, 21(2), 143-163.
  
  1. 本当に外的妥当性はあるの？
  2. 言えるのは「かなり大規模なクラスサイズ低下ならば効果がある」と言うところまでであるって言う点  
    コストが非常にかかる。
  3. 幼稚園と小学1年生での効果しか確認されてない
  4. 教員がより子供に注意を払えるようになるという意味での効果は期待できない（ちょっと意図がよくわかっていない）
  5. クラスサイズリダクションが効く層には大分差がある（恵まれない層に効く)  
    CSRはフェアな政策ではない

#### 論文リスト
全部をあげるとキリがないが、以下のものはサーベイが纏まっていたり、強く有用だったりすると思われる。

* Krueger, A. B. (1999). Experimental estimates of education production functions. The quarterly journal of economics, 114(2), 497-532.

* Finn, J. D., & Achilles, C. M. (1999). Tennessee's class size study: Findings, implications, misconceptions. Educational evaluation and policy analysis, 21(2), 97-109.

  STAR実験研究初期の教育社会学方面からのレビュー

* Hanushek, E. A. (1999). Some findings from an independent investigation of the Tennessee STAR experiment and from other investigations of class size effects. Educational Evaluation and Policy Analysis, 21(2), 143-163.

  大分批判的なレビュー

* Schanzenbach, D. W. (2006). What have researchers learned from Project STAR?. Brookings papers on education policy, (9), 205-228.
  
  後からの振り返りレビュー

* Chetty, R., Friedman, J. N., Hilger, N., Saez, E., Schanzenbach, D. W., & Yagan, D. (2011). How does your kindergarten classroom affect your earnings? Evidence from Project STAR. The Quarterly Journal of Economics, 126(4), 1593-1660.
  
  非認知や労働市場との関連など

* Konstantopoulos, S. (2011). How consistent are class size effects?. Evaluation Review, 35(1), 71-92.
  
  上記の研究のレプリケーションを実施。おおまかに上記論文は正しいという結論に。

### STAR実験以外 Other than STAR experience

STAR実験以外でRCTを行なってクラスサイズ縮小の効果について調べたというものだと、次の様な例をあげることができる。

* Bettinger, E., Doss, C., Loeb, S., Rogers, A., & Taylor, E. (2017). The effects of class size in online college courses: Experimental evidence. Economics of Education Review, 58, 68-85.
  * 引用元 6
  * 
    Data: オンライン授業 at DeVry University<br>
    EstSt: RCT<br>
    Result: <br>
      コースの達成及び大学の継続: insignificant
  * メモ <br>
    なんでクラスサイズが効果あるの？ってことを考えた時、オンラインコースだと意味がなかったっていうのはもしかしたら含意があるかも。<br>
    オンラインクラスなんて教員の配慮とかあってなきがごとくなので。。。 <br>
    ものすごい大きなデータセット（100,000 student）でやっているので、さすがに頑健だと思う。

## 擬似的な実験的環境の利用など Quasi‐experimental
### マイモニデスルール Maimonides
#### マイモニデスルールを用いた主要な結果
Angrist and Lavy(1999)など擬似的な実験的環境を利用して推定するという研究も多くなされた。これらの研究の多くはマイモニデスルールを用いた2SLSを実行するものである。　<br>
その<b>成績</b>を対象に解析した研究の主要な結果としては、次の様な点を挙げることができる。

1. クラスサイズ縮小は成績に対してポジティブな効果を持ちうる。<br>

  正確にいうと、この点についてかなり総体的には曖昧なところが残る。<br>
  一部の研究は確かに有意性を示していている一方で、もう一部で有意でなかったという研究もある。<br>
  この点についてSchanzenbach(2014)のポリシーサーベイなどが出ており、基本的には有意なんじゃないか？という議論は出ている

  >> 結局のところ「クラスサイズポリシーが有効でない」という言説は、多くはコストベネフィット的な観点であろうと思われる。

2. 一方で、近年の研究ではマイモニデスルールの前提である閾値上での自動的なクラスサイズの増加や教員の割り当てのランダム性などに対する疑いなども出てきている。

  主だったところだと以下の研究を上げれるだろう。 <br>

  Angrist, J. D., Lavy, V., Leder-Luis, J., & Shany, A. (2017)  <br>
  Urquiola, M., & Verhoogen, E. (2009) <br>
  Barrett, N., & Toma, E. F. (2013)

#### 論文リスト

##### 主要な研究
まずマイモニデスルールを用いた（結果も含んでいる）主要な論文は以下の通り。

* Angrist, J. D., & Lavy, V. (1999). Using Maimonides' rule to estimate the effect of class size on scholastic achievement. The Quarterly Journal of Economics, 114(2), 533-575.
  
  * 
  もっとも初期にRDDを使ってうまく推定した例

    Data: イスラエルの学校データ<br>
    EstSt: マイモニデスルールを用いたIV<br>
    Result: significant（Grade5：Math•Language, Grade: Language）

* Urquiola, M. (2006). Identifying class size effects in developing countries: Evidence from rural Bolivia. Review of Economics and statistics, 88(1), 171-177.
   
   * 
   単学級のデータ使えば、クラス編成についての内生成は取り除けるからいいのでは？というアイディアを提出

   Data: ボリビアのデータ<br>
   EstSt: 
     ２つの戦略でクラスサイズの効果を図っている<br>
      1. マイモニデスルール<br>
      2. 田舎はそもそも学校選択の余地がないし、一様にSES低いからよい？  <br>

   Result: 成績：significant

* Hoxby, C. M. (2000). The effects of class size on student achievement: New evidence from population variation. The Quarterly Journal of Economics, 115(4), 1239-1285.
   * 
   クラスサイズ研究の結果についてかなり懐疑的。きちんと読めてないけど、RCTすらそこまで信用していないような記述をしている。  

   単学級のデータ使えば、クラス編成についての内生成は取り除けるからいいのでは？というアイディアを提出

   Data: コネチカット、幼稚園ー小学校<br>
   EstSt: 
    1. ToDo:州単位でのクラスサイズ？ちょっとパッと把握できなかったので後で読み直す。<br>
    2. マイモニデスルール　<br>

   Result: 成績 : <font color="Red">insignificant</font>

* Angrist, J. D., Lavy, V., Leder-Luis, J., & Shany, A. (2017). Maimonides Rule Redux (No. w23486). National Bureau of Economic Research.
  * 引用元 182
  * 
  Angrist & Lavy (1999)の今日からみた振り返り。<br>
  当時はクラスサイズの負の影響を観測できたが、今日的なデータを用いるとほぼその有意な関係性は取り出すことができない。 <br>
  もう一つ重要な発見として、クラスの数がちょうど増えるような入学者数の学校が多すぎることを報告している。<br>
   >> TODO: 唯、ちょっと理屈をしっかり把握できていないので、読み込む必要がある

##### 様々な母集団

また上記の研究を反映して色々な国/母集団でその効果の確認を行う研究がなされている。 <br>
おおまかには有意な結果を報告している。

* Dobbelsteen, S., Levin, J., & Oosterbeek, H. (2002). The causal effect of class size on scholastic achievement: distinguishing the pure class size effect from the effect of changes in class composition. Oxford Bulletin of Economics and statistics, 64(1), 17-38.
  * 
    Data : オランダ, lower-secondary school<br>
    Result : cognitive, <font color="Red">insignificant</font>

* Bonesronning, 2003 : Norway
  * 
    Data : Norway<br>
    Result : cognitive, significant

* Leuven, E., Oosterbeek, H., & Rønning, M. (2008). Quasi‐experimental estimates of the effect of class size on achievement in Norway. The Scandinavian Journal of Economics, 110(4), 663-693.
  * 
    Data : Norway, lower-secondary school<br>
    Result : cognitive, significant

* Denny, K., & Oppedisano, V. (2013). The surprising effect of larger class sizes: Evidence using two identification strategies. Labour Economics, 23, 57-65.
  * 
    Data: PISA in U.S. & England<br>
    EstSt: RDD(maimonides) & GMM<br>
    Result:<br>
      （結論がこれまでとinconsistentであることに注意）<br>
      Only in England, increasing class size may lead to improvement of mathmatics score.

* Gary-Bobo, R. J., & Mahjoub, M. B. (2013). Estimation of Class-Size Effects, Using" Maimonides' Rule" and Other Instruments: the Case of French Junior High Schools. Annals of Economics and Statistics/ANNALES D'ÉCONOMIE ET DE STATISTIQUE, 193-225.
  * 
    Data : French<br>
    Result : 進級確率, significant(grade8やgrade9になると消える)

<small>
  他Pikettyがフランスでやったりしているが、そのジャーナル掲載版が見つからず、一旦メモ。
  （mimeoとして残っているだけ？ ）
</small>

##### RDDとしての妥当性

中にはマイモニデスルールを用いたRDDの仮定に対して疑問を提出するものもある。すなわちマイモニデスルールのカットオフポイント付近での恣意的な操作が発生しうるとしている論文がいくつかある。<br>
これまで挙げてきたようなものも含めると、以下の様な論文をあげることができる。


* Urquiola, M., & Verhoogen, E. (2009). Class-size caps, sorting, and the regression-discontinuity design. American Economic Review, 99(1), 179-215.
  * 詳しいことはTDR（一回読んだんだけどメモ忘れてしまった）

* Barrett, N., & Toma, E. F. (2013). Reward or punishment? Class size and teacher quality. Economics of Education Review, 35, 41-52.
  * 引用元 21
  * どんなもの？
    Data:<br>
      ケンタッキー州、grades 5, 8, and 11.<br>
    Result: <br>
      「過去の」教員のeffectivenessが現在のクラス編成に与える影響を調査<br>
      &emsp;Background: 優秀な教員には報酬として小さいクラスを与えたり、むしろ学校管理上より大きいクラスをあてがえうる。<br>
      「過去」優秀だった教員には大きなクラスを割り振っていることを発見。クラス編成には内生性がありうる。<br>

* Angrist, J. D., Lavy, V., Leder-Luis, J., & Shany, A. (2017)

### マイモニデスルール以外について Other than maimonides

* Hoxby, C. M. (2000). The effects of class size on student achievement: New evidence from population variation. The Quarterly Journal of Economics, 115(4), 1239-1285.

## 認知能力以外にはどのようなアウトカムに影響を与えているのか？ Other outcome
ここまで記述したものは全て学力への影響を見たものであった。<br>
しかしクラスサイズの縮小や非認知能力などのcognitive以外にどのような影響を与えているか、もしくはそれが労働市場などにどのような影響を与えているかを見る研究も（当然存在する）

### 非認知能力 Noncognitive
非認知能力について調査した文献として、（目に入る範囲で）referすべき重要な文献を以下の表にまとめた。 <br>
その主要な結果をまとめると、

1. おおまかには非認知に対しては効果がありという研究
 これは単に効果がないという研究は世に出ないだけ？

2. そこでの非認知というのは質問紙から構成された心理学的な尺度の研究は少ないがFredrickssonやDee and Westのものなど

3. 基本的には単年度の定点観測のデータ(VAにはなっていない)

<span class="tables">

|  Name  |  EstimationStrategy  | Data(Nation & Grade & level) | Output(significant) | Hetero |
| ---- | ---- | ---- | ---- | ---- |
|Dee, T. S., & West, M. R. (2011)|OLS, variation between subject at a class room|U.S. 8th grade, individuals , NELS:88|学力(significant?)<BR>非認知<BR>&nbsp;&nbsp;質問紙回答（授業へのやる気系,&nbsp;significant）<BR>&nbsp;&nbsp;卒業率など(数年後,&nbsp;significant)<BR>賃金(10年後,&nbsp;significant)<BR>*&nbsp;ちょっとアウトカムが多くて把握しきれない|
|Chetty et al. 2011|RCT-ols|アメリカ、テネシー州, 幼稚園-1st~3rd, individuals|*&nbsp;大人になってから(27歳)の成果を測定<BR>賃金(significant)<BR>大学出席率(significant)<BR>持ち家率(significant)<BR>貯蓄(significant)|
|Fredricksson et al.  2013|Maimonides|スウェーデン, grade4-6, individuals, 1967~1982年|•&nbsp;cognitive(IQ)&nbsp;&&nbsp;non-cognitive&nbsp;&nbsp;(significant,&nbsp;13&nbsp;years&nbsp;old)<BR>&nbsp;&nbsp;&nbsp;&nbsp;数学<BR>&nbsp;&nbsp;&nbsp;&nbsp;スウェーデン語<BR>&nbsp;&nbsp;&nbsp;&nbsp;Non&nbsp;Cog(effort&nbsp;motivation,&nbsp;aspirations,&nbsp;self-confidence,&nbsp;sociability,&nbsp;absenteeism,&nbsp;and&nbsp;anxiety)<BR>&nbsp;&nbsp;•&nbsp;Academic&nbsp;achievement&nbsp;&nbsp;(significant,&nbsp;16&nbsp;years&nbsp;old)<BR>&nbsp;&nbsp;•&nbsp;Wage&nbsp;(significant,&nbsp;27-42&nbsp;years&nbsp;old)|

</span>

#### 論文リスト

* Chetty, R., Friedman, J. N., Hilger, N., Saez, E., Schanzenbach, D. W., & Yagan, D. (2011). How does your kindergarten classroom affect your earnings? Evidence from Project STAR. The Quarterly Journal of Economics, 126(4), 1593-1660.
  * 引用数 907
  * 
    Data: Star<br>
    EstSt: RCT<br>
    Result: <br>
      大学の進学率：ポジティブ<br>
      経験豊富の教師に受けた生徒：ポジティブ


* Dee, T. S., & West, M. R. (2011). The non-cognitive returns to class size. Educational Evaluation and Policy Analysis, 33(1), 23-46.
  * 引用元 133
  * 
    Data:  NELS88(中学)<br>
    EstSt: DID (ToDo:詳しく読む)<br>
    Result: <br>
      非認知：ポジティブ<br>
      収益率はやはり4−6%ぐらい。


* Fredriksson, Peter, Björn Öckert, and Hessel Oosterbeek. "Long-term effects of class size." The Quarterly Journal of Economics 128.1 (2012): 249-285.
  * 引用元 182
  * 
    Data: Sweden, primaryschool<br>
    EstSt: IV for maimonides rule<br>
    Result: <br>
    以下のものたちに対して有意<br>

      * Wage (27-42 years old)
      * cognitive(IQ) & non-cognitive (13 years old)
      * Academic achievement (16 years old)

### 労働市場 Labor Market

* Chetty, R., Friedman, J. N., Hilger, N., Saez, E., Schanzenbach, D. W., & Yagan, D. (2011)

* Fredriksson, Peter, Björn Öckert, and Hessel Oosterbeek. "Long-term effects of class size." The Quarterly Journal of Economics 128.1 (2012)

* Fridericsonのショートレビュー
  <blockquote>
    Previous attempts have been plagued by lack of precision (Chetty et al. 2011), unavailability of directly linked data on labor market outcomes (Krueger 2003; Schanzenbach 2007), or strong identifying assumptions (Dearden, Ferri, and Meghir 2002; Dustmann, Rajah, and van Soest 2003)
  </blockquote>

### 日本での研究

日本語のペーパーは以下の様なものをあげることができる。
特に重要なのは、Hojo, M. (2013)•Akabayashi, Hideo, and Ryosuke Nakamura(2014)•伊藤他(2017)などだろうが、
そこまでリジッドに有意であったという報告は少ないように思える。

<span class="tables">

|  Name  |  EstimationStrategy  | Data(Nation & Grade & level) | Output(significant) | Hetero |
| ---- | ---- | ---- | ---- | ---- |
|二木美苗. (2013).|Maimonides|Japan, 8th grade, individuals, TIMSS2003|Math(insignificant)<BR>Science(insignificant)<BR>Non-cognitive(質問紙)<BR>&nbsp;&nbsp;高い意欲(NonCog)<BR>&nbsp;&nbsp;自信(NonCog)<BR>&nbsp;&nbsp;有用性(NonCog)<BR>&nbsp;&nbsp;帰属性(NonCog)<BR>&nbsp;&nbsp;興味(NonCog)<BR>&nbsp;&nbsp;意欲(NonCog)<BR>&nbsp;&nbsp;混乱(NonCog)|
|Hojo, M. (2013)|Maimonides rule, piecewise-linear specification(estimated by spline completion)|Japan, 4th grade, individuals, TIMSS 2003|Mathematics(significant,&nbsp;??ほんまけ)<BR>Science(significant,&nbsp;??ほんまけ)&nbsp;|
|妹尾渉, 篠崎武久, & 北條雅一. (2013).|OLS in Unit class school|Japan, 6th • 9th, individuals, 全国学力・学習状況調査（平成 19 年度実施）|Japanese(significant)<BR>Math(significant)|
|Akabayashi, Hideo, and Ryosuke Nakamura(2014)|Maimonodes Rule, Value Added|Yokohama(National Achievement Test 2008 , Yokohama Achievement Test 2009), 6 grade, 9 grade, school level|Japanese&nbsp;language&nbsp;(significant&nbsp;only&nbsp;at&nbsp;6grade)<BR>Math&nbsp;(insignificant)|
|妹尾渉, 北條雅一, 篠崎武久, & 佐野晋平. (2014)|Maimonides Rule|Japan, 6th • 9th grade, individuals, 全国学力・学習状況調査 |Japanese(insignificant&nbsp;at&nbsp;only&nbsp;6th&nbsp;grade)<BR>Math(insignificant)|
|妹尾渉. (2016)|MultiLevel|Japan ,6th • 9th grade, individuals, 全国学力・学習状況調査 2013|Math(significant)<BR>Japanese(significant)|
|伊藤他(2017)|方法：実質RCT(全ての学校がクラスサイズルールに従っている)-階層ベイズ|日本(中部地方の位置中規模市), 小学4年〜中学3年|学業成績(国語・数学,&nbsp;significant)<BR>非認知<BR>&nbsp;&nbsp;&nbsp;&nbsp;友人関係(insignificant)<BR>&nbsp;&nbsp;&nbsp;&nbsp;教師との関係(insignificant?)<BR>&nbsp;&nbsp;&nbsp;&nbsp;向社会的行動(significant)<BR>&nbsp;&nbsp;&nbsp;&nbsp;ソーシャルサポート(友人or教師)(significant)<BR>&nbsp;&nbsp;&nbsp;&nbsp;メンタルヘルス(significant)|

* Hojoの研究について備忘。"spline regression approach" と書いているが、これはクラスサイズに係る係数推定量が一様で無いことを許容するモデルを組むことを考えた時に（具体的には任意の値Tよりもクラスサイズが大きいダミーとクラスサイズの交差項を入れる。）、その任意の値Tをspline補完で決めるというアプローチの様である("breakpoint in the spline"って言っているから、スプライン補完ですらなくて単なるbest fitを探しているだけ？よくわからない)。

</span>

### 教員の質 Teacher qualty
CSR(Class size reduction policy)は、実は内実にジレンマを孕みうる。
すなわちCSRで子供一人当たりの教員の数を増やすと教員の採用数を挙げなきゃいけなくなるため、むしろレベルの低い教員を採用する必要が出てくる、といったジレンマである。<br>
その文脈では、以下の様な文献が知られてる。


* Mueller, S. (2013). Teacher experience and the class size effect—Experimental evidence. Journal of Public Economics, 98, 44-52.
  * 引用数 34
  * 
    Data: Star実験<br>
    Estst: RCT？<br>
    Result: <br>
    教師の経験がクラスサイズ効果とどう関係があるか？を調べている。<br>
      BackGround: <br>クラスサイズの縮小は教師の採用数を増やすため、教員の経験年数というqualityを考えられているものを下げる必要がある。<br>
    レベルの高い教師（経験年数の高い教師のこと）の時に、よりクラスサイズは効果をもつ

* Sapelli, C., & Illanes, G. (2016). Class size and teacher effects in higher education. Economics of Education Review, 52, 19-28.
  * 引用元 7
  * 
    Data: FACEAPUC（チリ大学） <br>
    EstSt: IV for maimonides rule<br>
    Result: <br>
      CSRを実施すると、教員の数を増やすと教員の質も悪くなる。<br>
      <blockquote>
          "This tradeoff implies that as class size increases, at first the negative class size effect is smaller than that of introducing a first time teacher." <br>
          first time theacher : 初任
      </blockquote>

* Angrist, J. D., Battistin, E., & Vuri, D. (2017). In a small moment: Class size and moral hazard in the Italian mezzogiorno. American Economic Journal: Applied Economics, 9(4), 216-49.  
(完全に未読)moral hazard が云々

## ではなぜCSRは効果を持ちうるのだろうか？ Why is CSR policy effective?
    
そもそもCSRがなぜ効果を持ちうるかという点については十分な検証がなされていないのが現状である。<br>
上記にも述べた通りCSRの現代的研究は時代性を帯びており、そのメカニズム自体を考える前に検証が始まっているのかもしれない。<br>
私見ではあるが、CSRはSTratioなど<b>学校の中で</b>教員がなぜ生徒にとって重要なのかを考える材料の一つであるように思う.<br>
<br>
プリミティブではあるがCSRが効く理由としてはLazearのモデルをあげる研究が多い。下記に記すのはそのような言及をしている研究である。

* Mueller, S. (2013). Teacher experience and the class size effect—Experimental evidence. Journal of Public Economics, 98, 44-52.


* Schanzenbach, D. W. (2006). What have researchers learned from Project STAR?. Brookings papers on education policy, (9), 205-228. 

解釈のみ<br>

  1. Lazear model
  2. 非認知スキルの向上にCSRは役に立っている

* Bandiera, O., Larcinese, V., & Rasul, I. (2010). Heterogeneous class size effects: New evidence from a panel of university students. The Economic Journal, 120(549), 1365-1398.

  * 引用数 128
  *
   Data: data：administrative data on individual students from a leading UK university, for the academic years 1999/00 to 2003/4.

    イギリスの大学のデータを用いてクラスサイズの学業達成への影響を調査。
    クラスサイズに効果はある、という結論に。
    特に着目したのはその非線型性。次の様な非線型性が確認された
      * すごい小さいクラス→大きいクラスではクラスサイズ効果あり
      * 真ん中のサイズではクラスサイズ効果なし
      * 大きいクラスではクラスサイズ効果あり
    これはクラスサイズの働き方にいくつかメカニズムがあることを示唆している。(音の聞こえ方とか??)
    またこの非線型性はクラスサイズに関数クラス編成にも影響を与えるね。

<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.0/css/bootstrap.min.css" integrity="sha384-9gVQ4dYFwwWSjIDZnLEWnxCjeSWFphJiwGPXr1jddIhOegiu1FwO5qRGvFXOdJZ4" crossorigin="anonymous">
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>  
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.0/js/bootstrap.min.js" integrity="sha384-uefMccjFJAIv6A+rW+L4AHf99KvxDjWSu1z9VI8SKNVmz4sk7buKt/6v9KI65qnm" crossorigin="anonymous"></script>

<script>
  // tableにクラス追加
  $("span.tables > table").addClass("table table-hover table-responsive");
  $("span.tables > table > thead").addClass("table-secondary");
</script>
