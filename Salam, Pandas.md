[Ilkin anlayışlar](#ilkin-anlayışlar)

[Pandas qoşulması](#pandas-qoşulması)

[Faylların oxunması](#faylların-oxunması)

[Filtrlər ve dilmləmə](#filtrlər-və-dilimləmə)

[Birləşdirmə](#birləşdirmə)

[Təmizləmə](#təmizləmə)


# İlkin anlayışlar

Bu dəfəki yazımda Python Data Science ekosisteminin ən vacib elementlərindən biri olan Pandas proqram kitabxanası haqqında danışacağam. Vikipediyaya inansaq, Pandas öz adını ekonometrik termin olan və riyaziyyatçılar arasında çox istifadə edilən PANel DAta Structures (panel tipli veirlənlər sturkturu) sözündən götürüb. Belə ki, bu kifayət qədər inandırıcı bir məlumatdır. Çünki, Pandas dmeək olar ki, bütün verilənlər tipi ilə işləməyə yararlıdır:

- SQL və Excel tipli verilənlər. Bunlara həm də, cədvəl tipli verilənlər deyilir (tabular data)
- Sıralı və sırasız zaman seriyaları (time series)
- Matriks tipli verilənlər
- Digər statistik tipli verilənlər

Pandas əsasən iki tip struktur ilə işləyir:
- Seriya tipli (birölçülü: `x1, x2, x3, x4, x5 ,.., xN`)
- Çərçivə tipli (çoxölçülü: birdən artıq sətir və sütun olan)

Bundan əlavə, Pandas digər proqram kitabxanası olan Numpy üzərində yazıldığı üçün demək ola bütün elm sahələrində rahatıqla istifadə edilə bilər. Ən əsası isə, open-source olmasıdır. Yəni ki, [BSD](https://opensource.org/licenses/BSD-3-Clause) lisenziyası çərçivəsində istədiyiniz kimi istifadə edə bilərsiniz.


# Pandas qoşulması

Pandasdan istifadə etmək üçün, onu ilk öncə qoşmaq lazımdır. Bunun bir neçə yolu var. Ən rahatı, Anaconda (Canopy və ya digərləri) paketindən istifadə etməkdir. Anacondanı qoşduğunuz zaman Pandasla yanaşı, elmi və statistik işlər üçün nəzərdə tutulan digər 400+ kitabxanada istifadənizdə olacaq. Digər bir yol isə **pip** istifadə etməkdir. Terminalı açıb `pip install pandas` yazmağınız kifayətdir. Onu da deyim ki, Pandasın digər kitabxanalar ilə də asılılğı olduğu üçün, Numpy və digərləri də **pip** tərəfindən qoşula bilər (olmadığı təqdirdə). Hər dəfə Pandas istifadə etdikdə, onu ilk öncə çağırmaq lazımdır.

```python
import pandas as pd
import numpy as np

```
Qeyd edim ki, *pd* və *np* sırf qəbul edilmiş qısaltmadır, siz başqa cür də edə bilərsiniz. Adətən Pandas və Numpy hər ikisi qoşa çağırılır, çünki, hesablama vaxtı sizə böyük ehtimal hər ikisi lazım olacaq. Çağırıdan sonra, Pandas və Numpy funksiyalarından **pd** və **np** prefiksi ilə rahat isfiadə edə bilərsiniz.

# Faylların oxunması

Çox vaxt Pandas istifadəsi zamanı fayl oxuma prosesi 3 tipdə olur:
* Artıq verilmiş python obyektlərinin (list, dictionary, array) Pandas obyektlərinə konverstasiyası.
* Hər hansı bir statik faylın yüklənməsi. SQL, Excel, CSV, TSV və s. 
* Hər hansı lokal olmayan faylın yüklənməsi. Ən çox APİ ilə işləyərkən lazım olur.

Hər fayl tipi üçün oxuma funksiyası ayrı olsa da onları bu cür yalançı kodla ümumiləşdirə bilərik:
```python

pd.read_filetype()

```
Əgər CSV tipli faylı oxumaq lazımdırsa, o zaman `pd.read_csv()` istifadə edə bilərsiniz. Faylların oxunması zamanı, funksiyalar əlavə arqumentlər də içərə bilərlər. Siz onları boş qoysanız, həmin arqumentlər öz ilkin qiymətlərində olacaq. Halbuki, onlardan istifadə mümkün qədər məsləhətdir.
Yox əgər hər hansı python obyektini Pandas obeyektinə çevirmək lazımdırsa, o zaman bu iki funksiya işinizə yarayar:
```python

pd.DataFrame()

pd.Series()
```
Pandas həm də, işlədiyi obyektləri fayla yaza da bilir. Bunun üçün isə sizə bu psevdo kod kömək edər:

```python

pd.to_filetype(faylın_adı)

```
Faylı yüklədikdən sonra, ilk öncə ona baxmaq lazımdır. Bunu siz `df.head(n), df.tail(n)` ilə edə bilərsiniz. Birinci obyektin ilk n sətirini, sonuncu isə son n sətirini göstərəcək. `df.shape()` sətir və sütunların sayını göstərəcək. `df.describe()` isə rəqəm tipli bütün sütunların statistik məlumatlarını göstərəcək. Həmçinin, bir sütun haqqında statistik məlumatları da almaq olar.

# Filtrlər və dilimləmə

SQLdə olduğu kimi, Pandasda da filtr tətbiqi olduqca rahatdır. Hətta, deyərdim ki daha rahatdır. Tutaq ki, bizdə **price (qiymət)** adlı sütun var, bizə də qiyməti 100 ₼ və ondan yuxarı olan sətirlər lazımdır. Bunu belə edə bilərik:

```python

df[df["price"] >= 100]
```
Burada böyük mötərizənin içindəki ifadəni `if: else` kimi başa düşmək olar. Pandas həmin ifadənin `true` qiymət aldığı sətirləri saxlayacaq. Nəzərənizdə olsun ki, ilkin obyekt dəyişmir, yalnız filtr olunur. Həmçinin, **&** və **|** işarələri **və**, **və ya** məntiqi üçün istifadə edə bilərsiniz. Məsələn, mənə qiymətin 100 ₼-dan yuxarı və\və ya 60 ₼-dan aşağı olan məhsullar lazımdır:

```python

df[df["price"] > 100 & df["price"] < 60]

df[df["price"] > 100 | df["price"] < 60]
```
Dilimləmə də olduqca rahatdır. `df.loc, df.iloc` funksiyalarını istifadə edə bilərsiniz. Loc sütun adları, iloc isə sətir indeksləri ilə işləyir. 

# Birləşdirmə

Bəzən bir neçə Pandas obyektini bu və ya digər səbələrdən dolayı birləşdirmək lazım gəlir. SQL tipli dillərdə adətən bu birləşmə istiqaməti, left, right, inner, outer ilə müəyyən olunur. Pandasda isə bir az ayrı tipdə birləşmələr yerinə yetirilə bilər:

* `df1.append(df2)` ikinci obyekti birinci obyektin sonuna birləşdirir. Sütunlar mütləq eyni olmalıdır.
* `df.concat([df1, df2], axis = 1)` df1 sütunlarını df2 sütunlarına əlavə edir. Sətirlər eyni olmalıdır.
* `df1.join(df2, on = col1, how = "inner")` SQL tipli birləşmə.

# Təmizləmə

Təmizləmə analitikanın ən vacib etaplarından biridir. Məsələn, ilk öncə həmişə çatışmayan göstəriciləri (null, N.A) tapmaq lazımdır. `df.isnull()` funksiyası verilmiş obyekti `isnull: True` məntiqinə uyğun gələn göstəricilərlə əvəz edib geri qaytarır. Bir növ True\False göstəricilərindən ibarət yeni bir obyekt görəcəksiniz. `df.isnull().sum()`  isə hər sütunda olan çatışmayan bütün göstəricilərin sayının cəmini verəcək. `df.dropna()` və ya `df.dropna(axis= 1)` edərək sətirləri və ya sütunları ata bilərsiniz. İnplace arqumentini True etdiyiniz zaman isə, veirlmiş obyekt modifikasiya ediləcək. `df.fillna("Nə isə")` funksiyası bütün çatışmayan göstəriciləri **Nə isə** sözü ilə əvəz edəcək.

Bəzən isə, hər hansı göstəricini dəyişmək lazım gəlir. `df.replace(2, "iki")` bütün 2-yə bərabər olanları **iki** sözü ilə əvəz edəcək. `df.replace([3, 4], ["üç, dörd])` isə bütün 3-ləri **üç**, 4-ləri isə **dörd** ilə əvəzləyəcək. `df.rename(columns = {"köhnəAd", "yeniAd"})` isə köhnəAd sütununun adını yeniAda dəyişəcək.


Pandasın əsas funksiyaları Cython dilində yazıldığı üçün çox sürətlidir. Funksionallığı isə onu ekosistemin çox vacib elementlərindən biri edir. [Rəsmi dokumentasiyada](https://pandas.pydata.org/pandas-docs/stable) mənim yazdıqlarımdan əlavə çox maraqlı funksiyalar ilə tanış ola bilərsiniz. Bir müddətdən sonra isə siz hətta Pandası Exceldən üstün tutacaqsınız.

Oxuduğunuz üçün təşəkkürlər, Numpy ilə tanışlıqda görüşənədək.
