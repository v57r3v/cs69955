java c
POLS   4722:   Problem   Set   1
January   30,   2025
Due   at   5:00   PM   on   February   10,   2025
Read   the   following   instructions   carefully:
•      The   problem   set   is   due   at   5:00   PM   on   February   10,   2025.
•      Please   ask   all   questions   about   the   problem   set   on   Piazza using   the   label   pset1 that   we   created.
•      To make sure we can answer questions   precisely,   we   will   answer   questions   about   this   problemseton   Piazza   until   12:00   PM   on   February   10,   2025   .
•      Collaboration is allowed with your assigned   group   members   on   all   questions   except   for   the   bonus   individual   questions.      Collaboration   across   groups   is   not   allowed   for   all   questions.
•      For   bonus   individual   questions,   you   cannot   collaborate   with   or   discuss   them   with   anyone.    Of   course,   you   are   allowed   to   ask   questions   to   the   instructional   stafs   on   Piazza.
•      Please   read   the   submission   guidelines    (here)   carefully.         If   you   have   questions,   you   can   ask   questions   on   Piazza.   If your   submission   fails   to   follow   the   guideline,   we   may   need   to   take   of points.
•      No   late   submission   will   be   accepted   unless   students   obtain   prior   approval   from   the   instructor   at   least   one   day   before   the   due   date.
•      Grading:    Please   show   every   step   of   your   derivations.    We   grade   steps   of   derivations   as   well   as   your   ﬁnal   answers.   So, even if   you cannot solve the problem entirely, we can give you partial points to your derivations.
Even   if your   ﬁnal   answer   is   correct,   you   might   not   get   full   points   if your   derivations   are   incomplete.
•      Stylistic   Requirements:
We   take   the   format   of the   submitted   answers   seriously.      Please   make   sure   you   follow   the   following   rules.
1.    Your    “Main   Answer”   PDF   should   be   based   on   LaTeX,   Rmarkdown,   or   Quarto.
2.    The      “Main   Answer”   PDF   should   clearly   write   down   all   the   names   of the   group   members.
3.    Please   read   the   submission   guideline   for   more   details.
•      Rules   on   AI:   Please   follow   the   rules   on   the   use   of AI   explained   in   the   syllabus.
•      Bonus   Question:We   sometimes   have   bonus   individual   questions.    If   your   total   points   go   above    100,   then   those   points   will   carry      over      to      the      subsequent      problem      sets    (e.g.,    if   you    get    120    points,    20    points      can      be      added      to      the   subsequent   problem   sets).
•      Challenging   Question:
We   denote   challenging   questions   with   * marks.


1          Understanding   Potential   Outcomes   (30   points)This   problem   should   help   you   get   familiar   with   the   potential   outcomes   notation.      Try   to   keep   your   answers   brief   and   your   language   precise.         Throughout   the   problem,   you   can   assume   that   the      Stable   Unit   Treatment   Value   Assumption   (SUTVA)   holds.
1.    Explain   in   words   what   the   notation   Yi   (0)   represents.
2.    Contrast   the   meaning   of Yi   (0)   with   the   meaning   of Yi.
3.    Contrast   the   meaning   of   Yi   (0)   with   the   meaning   of   Yi   (1).    Is   it   ever   possible   to   observe   both   at   the   same   time   for   unit   i?   Why?
4.      Explain   the   notation   E{Yi   (0)   j   Ti    =   1},   where   Ti    is   a   binary   variable   that   gives   the   treatment   status   for   subject   i,   1   if treated,   0   if control.
5.    Contrast   the   meaning   of E{Yi   (0)} with   the   meaning   of E(Yi    j   Ti    = 0).
6.    Contrast   the   meaning   of E{Yi   (0)   j   Ti    =   1} with   the   meaning   of E{Yi   (0)   j   Ti    = 0}.
7.      Which   of   the   following   four   expectations   (that   you   explained   in   the   previous   questions)   can   be   identiﬁed   from   the   observed   data?Note:    Identiﬁcation   means   that   an   expression   can   be   reduced   to   a   function   that   contains   only   observed   variables   and   no   potential   outcomes.    Do   not   make   any   additional   assumptions   about   the   distributions   of   the   variables,   except   that   there   is   at   least   one   observation   with   Ti      =   1,   and   at   least   one   with   Ti      = 0   in   the   observed   data.E{Yi   (0)   j   Ti      =   1}                                                                                                                                                                                                               (1)E{Yi   (0)}                                                                                                                                                                                                                                                      (2)E(Yi      j   Ti      =   0)                                                                                                                                                      (3)E{Yi   (0)   j   Ti      = 0}                                                                                                                                                                                                               (4)


2          Data   Analysis   Question   (60   points   +   Bonus   10   points)In the lectures, we learned   two   modes   of randomization   based   inference,   i.e.,   Neymanian   and   Fisherian   inference.   Both   approaches   rely   on   the   act   of   physical   randomization   as   the      “reasoned   basis   for   inference”   (Fisher,   1935).   In   this   problem,   we   apply   these   two   inferential   approaches   to   a   ﬁeld   experiment   about   electoral   irregularities   in   Ghana.      Before   you   begin,   please   read   the   following   article.
Ichino,   Nahomi,   and   Matthias   Schu…ndeln.      2012.    “Deterring   or   displacing   electoral   irregularities?    Spillover   efects   of observers   in   a   randomized   ﬁeld   experiment   in   Ghana.”    Journal    of Politics,   Vol.    74,   No.    1,   pp.
292–307.In   this   experiment,   the   authors   examine   whether   the   presence   of election   observers   reduces   fraudulent   voter   registration      by      randomly      determining   the      locations      of   election      observers.       Ghana    has    230      constituencies      and   approximately 4800 electoral areas, which are subunits of constituencies.    Throughout the paper and this   problem   set, the   unit   of treatment   assignment   and   analysis   is this   electoral   area.    The   authors   ﬁnd that   sending   observers   to   an   electoral   area   reduces   the   fraudulent   voter   registration   of   the   area.    However,   they   also   ﬁnd   that   a   large   portion   of such   reduction   is   ofset   by   an   increase   in   fraudulent   registration   in   its   neighboring   electoral   areas.We   will   use   the   data   set   analyzed   in   the   original   article.    The   data   ﬁle   is    ghana   .csv   and   the   key   variables   and   their   descriptions   are   shown   here.   Each   row   corresponds   to   one   electoral   area   and   the   data   set   includes   868   electoral   areas.
•      fraud:   the   level   of fraud   at   an   electoral   area
•   Tela   :   whether   an   electoral   area   got   observers   (1=yes,   0=no)
•   ELA:   ID   for   each   electoral   area   (868   unique   IDs)
•   block:   block   used   for   block   randomization   (13   blocks)
•      assignedTin10C:   the   number   of treated   electoral   areas   within   10   kms
•   totalELAin10C   :   the   total   number   of electoral   areas   within   10   kms
Please   answer   the   following   questions.
Note:    For   the   sake   of   this   problem   set,   we   assume   a   variety   of   treatment   assignment   mechanisms   that   difer   from   the   one   used   in   the   original   paper.
Question   2.1In contrast to the actual experimental   design,   we   begin   by   assuming   that   the   treatment   assignment   is   completely   randomized.       That      is,      we      assume   that   when      assigning   the   treatment,    the   total      number      of   treated      areas   was   ﬁxed   and   researchers   randomly   selected   77   electoral   areas   out   of 868   and   assigned   them   to   the   treatment   group.   In   addition,   we   can   assume   that   there   is   no   interference   between   electoral   areas.    Under   this   setting,   compute   the   estimated   sample   average   treatment   efect   and   its      (conservative)   95%   conﬁdence   interval   using   Neyman’s   approach.      Please   give   a   brief substantive   interpretation.
Question   2.2Next,   under   the   assumption   of   complete   randomization,   compute   the   two-sided   p-value   for   the   sharp   null   hy-   pothesis   of no   treatment   efect   using   Fisher’s   approach.   Use   the   diference   in   average   outcomes   under   treatment   and control   as your test statistic.   You   may   approximate   this p-value   using   Monte   Carlo   simulation.    Describe the   key   diferences   between   Neyman’s   and   Fisher’s   approaches   regarding   the   null   hypotheses.


Question   2.3Instead   of   complete   randomization,   we   now   assume   block      (stratiﬁed)   randomization   of   treatment   assignment.   Under this alternative design, 868 constituencies are divided into   13   blo代 写POLS 4722: Problem Set 1Matlab
代做程序编程语言cks deﬁned by   the   block variable.    Assume   further   that   within   each   block,   the   pre-speciﬁed   number   of electoral   areas   are   randomly   treated.Propose   an   unbiased   estimator   of the   sample   average   treatment   efect.   Assume   that   there   are   J blocks,   each   of which   has   a   total   of Nj    units   (Nj1    treated   units   and   Nj    - Nj1    control   units)   and   that   within   each   block   the   complete   randomization   of treatment   assignment   is   used.      Please   formally   prove   its   unbiasedness.
Note:      We      can      assume      there      is      at      least      one      treated      and      one      control      unit      in      each      block.       We    maintain    this
assumption   for   the   rest   of questions   in   which   we   consider   block   randomization.
Question   2.4Please derive a   (conservative) variance estimator for the unbiased estimator   of   the sample average treatment efect   you   proposed   in   Question   2.3   under   block   randomization.      Please   formally   prove   that   your   variance   estimator   is   conservative.As      part      of   your      proof,      you      can      use   the      expression      of   the      conservative   variance      estimator      under      complete   randomization   without   proofs   (we   learned   it   in   the   class).    That   is,   without   proof,   you   can   use   the   result   that,   within   each   block,   the   Neyman   variance   estimator   is   conservative.
Question   2.5
We   again   assume   the   block   randomization   of treatment   assignment   as   explained   in   Question   2.3.Using   the   estimators   proposed   in      Questions      2.3   and      2.4,      compute   a   point   estimate   of   the   sample   average   treatment   efect   and   its   (conservative)   95%   conﬁdence   interval.      Give   a   substantive   interpretation   of the   results.   How   do   the   results   difer   from   those   obtained   in   Question   2.1?
Question   2.6Under   the   block   randomization   scheme   described   in      Question      2.3,   we   compute   the   p-value   for   the   sharp   null   hypothesis   of   no   efect   using   Fisher’s   framework   in   this   problem.         Consider   the   following   test   statistic,   which   represents   a   weighted   average   of within-block   diference-in-means,
where   Nj    is   the   number   of units   in   block j,   and   N   is   the   total   number   of units.
Compute   the   two-sided p-value   for   the   sharp   null   hypothesis   of no   efect   using   the   above   test   statistic.   Question   2.7*         (Bonus   Individual   Problem;   10   points)
While we   assumed   away the interference in the   previous   questions,   we   now   consider   a   simple   approach   to   analyze   interference.We   relax   the   assumption   of no   interference   by   writing   the   potential   outcome   of electoral   area   i   as   Yi   (Ti   ,   Wi   )   where Ti      represents whether electoral area i receives   the   treatment,   and   Wi    is the   number   of treated   observations   among   its      “neighbors."    In   the   current   application,   we   deﬁne   the   neighbors   of   an   electoral   area   as   the   electoral   areas   that   are   located   within   a      10km   distance,   following   one   of   the   choices   the   authors   of   the   original   article   made.    This   new   potential   outcomes   allows   for   the   violation   of the   SUTVA   because   unit   i’s   outcome   is   affected not   only   by   its   own   treatment   Ti    but   also   by   the   number   of treated   neighbors   Wi.




Our   causal   estimands   are   the   average   direct   and   indirect   efects,   which   are   deﬁned   as,   
where   w   and   w,    are   some   constants.
Please   answer   the   following   questions.
Note:   This   is   a   bonus   individual   problem,   so   this   problem   covers   topics   more   advanced   than   what   we   cover   in   the   class.
Question   2.7.1For simplicity, we keep the assumption that the treatment assignment was block randomized using variable block.   We   use   Gi      to   denote   a   block   indicator   for   unit   i,   and   Vi      to   denote the total   number   of units within   10km   of unit   i.      For   simplicity,   we   also   additionally   assume   that   neighbors   of unit   i   are   also   within   the   same   block   Gi.    Note,   however,   that   this   assumption   does   not   imply   that   all   units   in   block   Gi    are   neighbors   to   each   other.
Then,   because   of the   block   randomization,   we   haveYi (t,   w)   丄丄   (Ti   ,   Wi   )   j   Vi   ,   Gi   ,                  for   all   (t,   w)                                                                                                                                                                              (7)
which   means   that   within   each   block,      the   treatment   variable      Ti      and   the   number   of   treated   neighbors      Wi      are   independent   of the   potential   outcomes   Yi   (t,   w)   conditional   on   the   total   number   of neighbors   Vi.
However, we usually do not   have   the   following   conditional   independence   even   under   the   block   randomization.   Yi (t,   w)   丄丄   (Ti   ,   Wi   )   j   Gi   ,                  for   all   (t,   w)
which   does   not   condition   on   the   total   number   of neighbors   Vi.   Please   explain   why.
Question   2.7.2
Under   the   block   randomization,   researchers   might   be   interested   in   the   following   linear   regression   model.   


Under the assumption of this linear model, which parameters correspond to our causal estimands τdirect and τindirect. Please formally prove your argument using the conditional independence (equation (7)) we examined in the previous question.
Question 2.7.3
After removing all observations that have no neighbor within 10km, fit a linear regression model (equation (8)) to estimate our causal estimands τdirect and τindirect. To account for standard errors clustered at the block level, you can use R function vcovCL in the sandwich package. Please read the CRAN page (https://cran.r-project.org/web/packages/sandwich/) to learn how package sandwich works.
Report point estimates and 95% confidence intervals for our causal estimands τdirect and τindirect. Please give a brief substantive interpretation.
3          Application   of   Methods   (10   points)In this problem, you will   ﬁnd   an   application   of the   randomized   experimental   method   and   examine   its   design   and   analysis.   Please   ﬁnd   one   paper   that   uses   a   randomized   experiment   (it   can   be   a   survey,   lab,   or   ﬁeld   experiment).   It   should   satisfy   the   following   criteria.
1.    It   should   be   from   the   following   three   journals;    American    Political   Science    Review,    American    Journal    of   Political   Science,   or   Journal   of Politics.
2.    The      paper      should      have      a      publicly      available      replication      ﬁle.       For    the      above   three   journals,      they      require   authors   to   upload   replication   ﬁles   to   the   following   archives   in   recent   years.    So,   if   you   pick   a   paper   from   recent   years,   it   should   be   straightforward   to   ﬁnd   a   replication   ﬁle.
•      American   Political   Science   Review:   https://dataverse.harvard.edu/dataverse/the_review
•      American   Journal   of Political   Science:   https://dataverse.harvard.edu/dataverse/ajps
•      Journal   of Politics: https://dataverse.harvard.edu/dataverse/jop
3.      Each      group      should      ﬁnd      a      diferent      paper.       To    make    sure    every    group    ﬁnds      a      diferent      paper,    as    soon   as   your   group   ﬁnds      a   paper,      please   write      it      down      in   this      Google      Spreadsheet:    https://docs.google.   com/spreadsheets/d/1d9-5mly5GbGKgy5KpL8ik6frUGjjjMKjUsA4_Q8HZc4/edit?gid=0#gid=0.         We      use   the      “ﬁrst   come   ﬁrst   served”   rule.
4.      You   cannot   choose   papers   that   are   discussed   in   lectures   or   sections.
This   is   a   great   opportunity   for   you   to   learn   what   top   researchers   do   in   practice.
Note:    There    is   no    “one    correct”    answer   to   many   of   the   following   questions.         We   will   evaluate   your   answers   primarily   based   on   how   well   you   apply   concepts   we   learn   in   the   class   to   investigate   an   experiment   you   choose.
Question   3.1
Please   ﬁrst   explain   the   overall   research   question   of the   paper,   the   data   and   contexts   of the   study,   and   the   main   ﬁndings.Then,   please   describe   the   experimental   design   in   detail.    Is   it   complete,   Bernoulli,   block,   or   cluster   random-   ization?   If the   authors   use   a   diferent,   more   complex, treatment   assignment   mechanism,   how   do they justify   and   explain   their   treatment   assignment   mechanism?
Question   3.2Summarize   what   approaches   researchers   use   to   analyze   the   experimental   data.         For   example,   do   they   use   the   diference-in-means estimator?    Or   do they   use   a   linear regression   approach?      Do they   use   Fisher’s randomization   inference   to   compute   the   p-value?
Question   3.3
What   methodological   limitations   do   the   authors   discuss?         What   methodological   limitations   do    you    think   the   experiment   has?







         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
