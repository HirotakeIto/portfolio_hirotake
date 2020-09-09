---
layout: blog
title: TeacherPractice論文のためのメモ
date_post: 20190614
tags: survey
hidden: true
---

# どうやって論文を導入しているか
* Do teaching practices matter for students’ academic achievement? A case of linguistic activity - RYuichi Tanaka, et all
(導入)

  - Education is one of the key factors for the economic growth of nations.
    - One such typical policy measure is to improve teaching practices in classrooms.
  - we need to answer the question of how these teaching practices can improve educational outcomes of students in schools.
  - The main purpose of this study is to explore empirically how teaching practices matter for students academic achievements.
    - we focus on the effect of students linguistic activities led by teachers to promote logical thinking through linguistic communication.
    - In this study, using unique student-level test score data of one municipality in Japan, and controlling for school fixed effects and the potential endogeneity of linguistic activity variables. 

  - This study is related to a strand of the literature on the effect of school resources on academic achievements in schools.
    - スクールリソースの効果を分析するのは難しいけど、Rockoff (2004)とかChetty et al. (2014)みたいに教員の重要性は相変わらずだよね
  - It would be natural to see teaching practices as one of the determinants of teacher quality.

  (分析内容)
  - school fixed effect
  - variation of linguistic activity at the student level, this activity measure may be correlated to the individual unobserved heterogeneity captured by ϵji in Eq. (1). To deal with this potential endogeneity problem, we employ an instrumental variable method. Our



*　Is traditional teaching really all that bad? A within-student between-subject approach
  biased estimates if unobserved school characteristics, ν,and Lecture are correlated. This can be the case if the choice of the teaching practice is partly determined by the school and if there exists sorting of high ability students or effective teachers into schools.


* S.L. Comi et al. / Economics of Education Review 56 (2017) 24–39
Estimation of Eq. (1) by OLS yields biased estimates if the un- observed factors are correlated with the variables in the ICT vec- tor. This may be the case when neither teachers nor students are randomly distributed across schools (and across classes within schools) or when the adoption of ICT teaching practices is influ- enced by teachers’ unobserved characteristics that also affect stu- dent achievement. Endogenous sorting may arise because fami- lies choose specific schools for their children, also on the basis of the teacher’s quality and reputation.

*　Aslam
The key empirical challenge in identifying teacher　effects arises due to the potential non-random matching
of students to schools and, within schools, to particular　teachers. For instance, if higher-ability students sort into classes with better qualified/trained/experienced teachers within their grade or if teachers possessing these characteristics are systematically assigned to teach the classes with higher performing pupils, a positive coefficient on a given teacher characteristic could not be interpreted as causal. Our approach to address such endogeneity is to estimate a pupil fixed effects equation of achievement using cross-section data.


-　Do Teachers Matter for Academic Achievement of　Students? Evidence from Administrative Panel Data 
This paper examines empirically the effect of teachers on students' academic outcomes. Using large administrative panel data of reading and math test scores of students in public elementary schools in a large municipality in Japan, we estimate the distribution of teacher fixed effects controlling for student, school, and year fixed effects. Our results show that variation of teacher fixed effects is substantial: improvement of teacher fixed effect by one standard deviation raises student’s z-score by 0.23 standard deviation for reading and by 0.32 standard deviation for math. We find that teacher’s experience and class size matter for students’ achievement of both reading and math. The first several years of teaching experience result in improvement of students’ outcomes. Small class size results in high students’ performance. The magnitude of class size effect is comparable to ones in Angrist and Lavy (1999). Finally, the magnitude of the teacher effect is equal to the class size effect with reduction of 3.1 students for reading and 5.9 students for math test scores


* 教員の効果が年度ごとに違うモデル
次の様なモデルを考える。

$$
\begin{eqnarray}
  A _ { icjt } &=& \beta X _ { icjt } + \nu _ { icjt }  \quad where \quad \nu _ { icjt } = \theta _ { jt } + \mu _ { ct } + \varepsilon _ { icjt } \\
   \\
  && i: individuals \\
  && c: class \\
  && j: teacher \\
  && t: time \\
\end{eqnarray}
$$

このうち、$$A _ { icjt }, X _ { icjt }$$ は観察可能であるとする。
この時、上記式を推定して得ることができる、
$$
\begin{eqnarray}
  s _ { icjt } = A _ { icjt } - \hat{\beta} X _ { icjt }
\end{eqnarray}
$$
を$$\theta _ { jt }$$のシグナルであると考える(そのシグナルの集合を$s_{jt} = \{s_{icjt} \| i \in I_{jt} \}$と書くことにする)。signal extraction theoremを考えたいが、signal extraction theoremではシグナル間に相関がないことを前提にしている。そのため、シグナルをクラスごとに集約し($s_{jct}$とかく)、クラス間に相関がない仮定することで解決を図る。

実際にはシグナルを次の様に集約する。

$$ 
\begin{eqnarray}
s_{jct} &=& \frac{\sum_{i, i \in I_{cjt}} s_{icjt}}{\|I_{cjt}\|} \\
         &=& \theta _ {jt} + \mu _ {ct} + \frac{\sum_{i, i \in I_{cjt}} \varepsilon_{icjt}}{\|I_{cjt}\|} \\
         &=& \theta _ {jt} + v_{ct} \\
\\
Note: Var(v_{ct}) &=&  Var(\mu) + Var(\varepsilon) / \|I_{cjt}\|
\end{eqnarray}
$$

そして、得られたシグナルを用いて次に教員効果$$\theta _ { jt }$$の期待値を計算する。

$$ 
\begin{eqnarray}
   E(\theta_{jt} | s_j ) &=& \sum_{c, c \in C_{jt}} s_{jct} \frac{ \frac{1}{V(v_{ct})} }{ \frac{1}{V(\theta)} + \sum_{t, t \in T}\frac{1}{ V(v_{ct})} }
\end{eqnarray}
$$

以上より教員効果$$\theta _ { jt }$$の期待値を構成できたが実は求めていないものとして、$ Var(\mu), Var(\varepsilon), Var(
\theta)$がある。これは適当なpriorを構成するのだが、多くの場合次の様に行う。

* $Var(\theta)$: 「同じ先生が担当している隣のクラス」の共分散
* $Var(\mu)$: シグナルの分散から個人ごとの分散と教員の分散を引く
* $Var(\varepsilon)$: $Var(s _ { icjt }-\bar{s _ { icjt }})$（個人ごとのシグナルとシグナルのクラス平均の差の分散）




  






