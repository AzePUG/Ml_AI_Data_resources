# "Machine learning"-ə giriş

Machine learning.. Yəqin ki, son bir neçə ildə bu haqda eşitmisiniz. Ən azından,
bunu oxuyursunuzsa, demək ki, elədir. Bu haqda demək olar ki, azərbaycan dilində heç bir
resurs yoxdur. O üzdən, gəlin ilk öncə "machine learning" nədir sualına cavab tapaq.

# Machine learning nədir?

**Machine learning** - və ya daha qısa adı ilə **ML** hər hansısa bir problemi həll etməkdən ötrü
kompyuterin istifdə etdiyi alqoritm toplusudur. Smartfonunzda "Salam" yazarkən telefonun sizə avotmatik
olaraq "Necəsən?" sözünü təklif etməsindən tutmuş, Habl kosmik teleskopunun çəkdiyi şəkilləri analiz edib
yeni səma cisimlərini ayırd edə bilən sistemlərə, təyyarə bileti alarkən onun qiymətini müəyyən edən sistemdən
tutmuş, təyyarənin hansı qapıya yaxınlaşmasını deyən sistemə kimi hamısı ML-in tətbiq edildiyi sahələrdir.

Gəlin belə bir sadə misal çəkək. Tutaq ki, belə bir cədvəl verilib. Y-in növbəti qiymətini tapmaq lazımdır

| X  |   Y  |
|--- |  --- |
|1   |   2  |
|2   |   4  |
|3   |   6  |
|4   |   ?  |

Burada ? işarəsi yerində hansı rəqəm olmalıdır? Bir az düşünən kimi **8** deyəcəksiniz. Doğrudur.
Bunu necə etdiniz? **Qanunauyğunluq** axtararaq. Əvvəlcə X və Y arasındakı əlaqəni təyin edtiniz,
daha sonra isə sual işarəsinin yerinə olacaq rəqəmi tapdınız. İnsandan fərqli olaraq, kompyuterlər
bunu özbaşlarına birbaşa həll edə bilmirlər, onlara bir model lazımdır. Necə ki, uşaqlarımızı nəyəsə öyrədirik,
bənzər yanaşma da kompyuterlərə də olmaıdır.

# ML və onun növləri

ML çox geniş bir sahə olmasına baxmayaraq, tarixən onun bir neçə universal növü müəyyənləşib:
- Müəllimli öyrənmə (supervised learning)
- Müəllimsiz öyrənmə (unsupervised learning)
- Möhkəmlədilmə ilə öyrənmə (reinforcement learning)

Gəlin bir bir bunlara nəzər salaq:
* Müəllimli öyrənmə. Bu, stimul-reaksiya tipli öyrənmədir. Sistemə müəyyən sayda (yuxarıdakı misala bir də baxırıq)
X və Y verilir və sistem verilənlərin üzərində öyrənir. Daha sonra isə, sistemin görmədiyi və onun üçün yeni olan bi X
verilir və sistem əvvəl gördüklərinə əsasən Y-i tapır.
* Müəllimsiz öyrətmə. Sistem əvvəlcədən nəyin nə olduğunu bilmir. Proses zamanı özü qanunauyğunluq axtarır. Ən sadə misal kimi klassifikasiya (sinifləşdirmə) məsələsini gətirmək olar. Sistemə müxəlif hündürlüklər, və müvafiq obyektin növü verilir, dağ və ya təpə. Bilirik ki, hündürlüyü 200 metrdən yüksək olan obyektlər dağlardır. Sistem verilən hündürlükləri və obyektin növünü özü analiz edir, və özünün görmədiyi bir hündürlük ona verilən zaman onun dağ və ya təpə olduğunu deyə bilir.
* Möhkəmlətmə ilə öyrətmə. Sistem verilən mühit daxilində mühitlə qarşılıqlı əlaqədə ola-ola öyrənir. Məsələn, sürücüsüz maşınları idarə edən sistem. Burada mühit kimi bildiyimiz mühit, əlaqə kimi isə toqquşma, dönmə, sürətlənmə və digər hadisələr çıxış edir. Hər bir hadisə sistemin beynində dəyişiklik yaradır və beləcə sistem öyrənir. Daha sad\ bir misal. Uşaq vaxtı əliniz isti tavaya bir dəfə dəyəndən sonra tavadan uzaq durmanız möhkəmlətmə ilə öyrənmədir.
Hadisə kimi burda yanma, və onun nəticəsində ağrı rol alır.




# Aydındır, bəs necə edim ki, mən də ML bilim?

Bayaqkı  X-Y misalına baxaq. Qanunauyğunluğu riyazi metodla tapdıq. Evristik metodlarla (bu nə sözdür deyə bilərsiniz, bu haqda da yazı olacaq) da etmək olar, ancaq hamısının əsasında riyaziyyat durur. İlk öncə cəbr, ali riyaziyyat və statistikanı öyrənməlisiniz. Xoşbəxtlikdən, günümüzdə internet resurslarının sayı kifayət qədərdir. Aşağıdakı resurslardan istifadə edə bilərsinizŞ
- [**İntroduction to statistical learning**](http://www-bcf.usc.edu/~gareth/ISL/) pulsuz kitabından istifadə edə bilərsiniz. Alqoritmlər R proqramlaşdırma dilində olsa da, ilk öncə riyazi hissəsi ilə sırf məşğul ola bilərsiniz.
- [Con Hopkins universitetinin Machine Learning kursu](https://www.coursera.org/learn/practical-machine-learning)
- [Stanford Universitetinin Statistical Learning kursu](https://lagunita.stanford.edu/courses/HumanitiesSciences/StatLearning/Winter2016/about)

Daha sonra isə ML-in proqramlaşdırma dillərindən birini öyrənin. Python, R, Scala, Julia və s. Python üçün Udemy ən uyğun variantlardandır. Məsələn, Jose Portillanın [Python for Data Science](https://www.udemy.com/python-for-data-science-and-machine-learning-bootcamp/learn/v4/overview) kursu ilk addım kimi sizə uyğun gələcək.

Ən əsası isə, mümkün qədər çoxlu bloq, ML yönümlü xəbərlər oxumaqdır. [Burada](https://blog.feedspot.com/machine_learning_blogs/) ML mövzusunda ən faydalı bloqların toplusunu tapa bilərsiniz. Xoş öyrənmələr!
