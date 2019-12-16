# Döngüler(Loops)

Bir durumun/sürecin tekrar tekrar kullanılmasını sağlayan yapıya döngü(loops) denir.

Python'da iki adet döngü bulunmaktadır;
1. While
2. For

## While Döngüsü

While döngüsünü örnekler üzerinden öğrenelim.


```python
a = 1

while a < 5:
    a += 1
    print("Sayı 5'ten küçüktür.")
```

    Sayı 5'ten küçüktür.
    Sayı 5'ten küçüktür.
    Sayı 5'ten küçüktür.
    Sayı 5'ten küçüktür.


Yukarıda bulunan örnekte aşağıdaki adımlar gerçekleşmiştir:
    
- Adım 1: a değişkenine 1 değerini ata.
- Adım 2: a sayısı 5 değerinden küçük ise döngünün içine gir. Eğer a sayısı 5 değerinden büyük ise **Adım 6**'ya git.
- Adım 3: a değerini 1 artır.
- Adım 4: ekrana "Sayı 5'ten küçüktür." yazdır.
- Adım 5: **Adım 2**'ye git.
- Adım 6: Çıkış.

While döngüsünün daha iyi anlaşılması için çift sayıları ekrana yazdıran bir uygulama yapalım.


```python
sayi = 0

while sayi < 19: 
    sayi += 1
    if sayi % 2 == 0: 
        print(sayi)
```

    2
    4
    6
    8
    10
    12
    14
    16
    18


## For Döngüsü

**while** döngüsü ile yapamayacağınız veya yaparken çok zorlanacağınız şeyleri **for** döngüsü yardımıyla çok kolay bir şekilde halledebilirsiniz.


```python
harfler = "abcd"

for harf in harfler:
    print(harf)
```

    a
    b
    c
    d


Örnekte olduğu gibi for döngüsü bir nesnenin içinde dolaşabilmemizi ve nesnenin sahip olduğu değerlere ayrı ayrı erişebilmemizi sağlar.

Peki aynı işlemi while döngüsü ile yazalım ve karşılaştıralım.


```python
a = 0

while a < len(harfler):
    print(harfler[a])
    a += 1
```

    a
    b
    c
    d


For döngüsü ile yaptığımız işlemin aynısını while ile de yapabildik fakat biraz daha uzun sürdü. Bu yüzden for ile yapabileceğimiz bir işlemi while ile yapmamak daha iyi olacaktır.

## İlgili Araçlar

Döngüler kendilerinin yanına bazı fonksiyonlar alabilmektedir. Bu fonksiyonları inceleyelim.

### range Fonksiyonu

range fonksiyonunu belirli bir aralıkta bulunan sayıları göstermek için kullanıyoruz.


```python
for i in range(0,5):
    print(i)
```

    0
    1
    2
    3
    4


range(ilk_sayi,son_sayi) fonksiyonu şeklinde kullanılır. Burada ilk_sayi aralığa dahil edilirken, son_sayi aralığa dahil edilmez. Eğer biz 1'den 5'e kadar olan sayıları ekrana yazdırmak istiyorsak range fonksiyonu şu şekilde olmalıdır.


```python
for i in range(0,6):
    print(i)
```

    0
    1
    2
    3
    4
    5


Yukarıdaki örneklerde sayılar hep birer birer arttı. Peki artış miktarını değiştirmek istiyorsak nasıl bir yol izlemeliyiz. O zaman range fonksiyonunu şu şekilde **range(ilk_sayi,son_sayi,artis_miktari)** kullanmalıyız. Burada artış miktarına istediğimiz sayıyı yazabiliriz. Hemen birkaç örnek ile inceleyelim.


```python
for i in range(5,0,-1):
    print(i)
```

    5
    4
    3
    2
    1


Bir başka örnek;


```python
for i in range(0,10,2):
    print(i)
```

    0
    2
    4
    6
    8


ve bir örnek daha.


```python
for i in range(0,20,5):
    print(i)
```

    0
    5
    10
    15


range fonksiyonunun, print fonksiyonu ile kullanımana birkaç örnek verelim;


```python
print(*range(10))
```

    0 1 2 3 4 5 6 7 8 9


ve range fonksiyonu için son örneğimiz:


```python
print(*range(10), sep=", ")
```

    0, 1, 2, 3, 4, 5, 6, 7, 8, 9


### pass Deyimi

pass kelimesi ingilizce'de geçmek anlamına gelir. Bu deyimi döngülerle birlikte kullandığımız zaman o yapı göz ardı edilecektir.


```python
sayi = int(input("Bir sayı giriniz: "))    
    
if sayi < 0:
    pass
else:
    print(sayi)
```

    Bir sayı giriniz: -1


Yukarıdaki örnekte girmiş olduğumuz sayının değeri -1, if bloğuna geldiği zaman baktı sayı 0'dan küçük içeri girdi fakat biz pas geç dediğimiz için herhangi bir işlem yapmadı.

### break Deyimi

break kelimesi ingilizce'de kırmak anlamına gelir. Bu deyimi döngülerle birlikte kullandığımız zaman döngüyü kırar ve dışarı çıkar yani işlem devam etmesi gerekse bile biz break yazdığımız için break deyiminin olduğu yerde işlemleri keser ve dışarı çıkar.


```python
while True:
    parola = input("Lütfen bir parola belirleyiniz:") 
    
    if len(parola) < 5:
        print("Parola 5 karakterden az olmamalı!")
    else:
        print("Parolanız belirlendi!")
        break
```

    Lütfen bir parola belirleyiniz:123456
    Parolanız belirlendi!


Eğer yukarıda bulunan örnekte break deyimini yazmamış olsaydık, parolamızı istenildiği gibi belirlediğimiz halde döngü devam edecekti.

### continue Deyimi

continue kelimesi ingilizce'de devam et anlamına gelmektedir. Bu deyimi döngülerde kullandığımız zaman istenilen şart gerçekleşse bile döngüde işleme devam edilir.


```python
while True:
    s = input("Bir sayı girin: ") 
    
    if s == "iptal":
        break

    if len(s) <= 3:
        continue
    
    print("En fazla üç haneli bir sayı girebilirsiniz.")
```

    Bir sayı girin: 3
    Bir sayı girin: 2
    Bir sayı girin: 1
    Bir sayı girin: iptal


Yukarıdaki örnekte kullanıcı 3'e eşit veya daha küçük sayılar girdiği sürece döngü devam edecek çünkü continue ifadesi bulunmaktadır. Eğer iptal ibaresini girersek döngü kırılmış olacak ve döngüden dışarı çıkılacak.

> Son Güncelleme: 16 Aralık 2019 - Pazartesi
