# İşleçler

Herhangi bir işlemde, işlenenler üzerinde yapılması öngörülen işi tanımlayan özel damga, damga dizgisi vb. göstergeler, örn.  | + | /| *| ** aritmetiksel, AND | OR | NOT mantıksal işleçler olarak kullanılır. [Kaynak](https://kelimeler.gen.tr/islec-nedir-ne-demek-168827)

Python içerisinde farklı işleçler bulunmaktadır. Bunlar;
1. Aritmetik İşleçler
2. Karşılaştırma İşleçleri
3. Bool İşleçleri
4. Değer Atama İşleçleri
5. Aitlik İşleçleri
6. Kimlik İşleçleri

## Aritmetik İşleçler

Aritmetik işleçler, matematiksel işlemler yapabilmemiz sağlayan araçlar.

| İşleç |    İşlem    |
|:-----:|:-----------:|
|   +   |   Toplama   |
|   -   |   Çıkarma   |
|   *   |    Çarpma   |
|   /   |    Bölme    |
|   **  |    Kuvvet   |
|   %   |   Modülüs   |
|   //  | Taban Bölme |

Aritmetik işleçlerle bazı işlemler yapalım ve nasıl kullanıldıklarını öğrenelim.


```python
3-2
```




    1




```python
3*2
```




    6




```python
3+2
```




    5




```python
3/2
```




    1.5




```python
3**2
```




    9




```python
"Python" + "Dili"
```




    'PythonDili'




```python
"yavaş" * 2
```




    'yavaşyavaş'




```python
"/" * 5
```




    '/////'




```python
29 % 4 #Bu işleç bir sayının başka bir sayıya bölümünde kalanı vermektedir.
```




    1




```python
30 % 5
```




    0



Bir sayının çift sayı olup olmadığın gösteren uygulama yapalım.


```python
sayi = int(input("Bir sayı giriniz: "))

if sayi % 2 == 0:
    print("Girdiğiniz sayı bir çift sayıdır.")
else:
    print("Girdiğiniz sayı çift sayı değildir.")
```

    Bir sayı giriniz: 5
    Girdiğiniz sayı çift sayı değildir.


## Karşılaştırma İşleçleri

Karşılaştırma işleçleri, adında anlaşıldığı üzere karşılaştırma işlemlerini yapabilmemizi sağlayan araçlardır.

| İşleç |     İşlevi    |
|:-----:|:-------------:|
|   ==  |    Eşittir    |
|   !=  | Eşit Değildir |
|   >   |    Büyüktür   |
|   <   |    Küçüktür   |
|   >=  | Büyük Eşittir |
|   <=  | Küçük Eşittir |

Tabloda bulunan işleçlerin hepsini olmasada bazıları için küçük bir örnek ile nasıl kullanıldığına bakalım.


```python
parola = "11111"

soru = input("parolanız: ")

if soru == parola: 
    print("doğru parola!")
elif soru != parola: 
    print("yanlış parola!")
```

    parolanız: 11111
    doğru parola!



```python
sayi = int(input("Bir sayı giriniz: "))

if sayi == 5:
    print("Sayı 5'e eşittir.")
elif sayi < 5:
    print("Sayı 5'ten küçüktür.")
elif sayi > 5:
    print("Sayı 5'ten büyüktür.")
```

    Bir sayı giriniz: 5
    Sayı 5'e eşittir.


## Bool İşleçleri

Bu işleç bizlere karşılaştırılan bir nesne ile ilgili iki farklı sonuç gösterir. Bunlar **True** veya **False** değerleridir. Bu yapının nasıl olduğuna bakalım.


```python
5 == 0
```




    False




```python
5 == 5
```




    True



Eğer istersek **bool()** fonksiyonundanda faydalanabiliriz.


```python
bool(5 == 0)
```




    False



Bool işleci kendi içinde üç adet yapı bulundurmaktadır. Bunlar:

1. and
2. or 
3. not

bu yapıları tek tek inceleyelim.

### and yapısı

Bu yapı **ve** anlamına gelmektedir. Bu yapıyı kullandığımız yerde her iki durumunda doğru olması beklenir. Örnek üzerinde nasıl kullanıldığını inceleyelim.


```python
sayi = int(input("Bir sayı giriniz: "))

if sayi > 0 and sayi < 5:
    print("Giridiğiniz sayı 0 ile 5 arasında bulunmaktadır.")
elif sayi > 5 and sayi < 10:
    print("Girdiğiniz sayı 5 ile 10 arasında bulunmaktadır.")
```

    Bir sayı giriniz: 7
    Girdiğiniz sayı 5 ile 10 arasında bulunmaktadır.


### or yapısı

Bu yapı **veya** anlamına gelmektedir. Bu yapıyı kullandığımız yerde her iki durumdan sadece birisinin doğru olması beklenmektedir. Örnek üzerinde nasıl kullanıldığını inceleyelim.


```python
x = int(input("Notunuz: ")) 

if x > 100 or x < 0:
    print("Böyle bir not yok") 
elif x >= 90 and x <= 100:
    print("A aldınız.") 
elif x >= 80 and x <= 89:
    print("B aldınız.") 
elif x >= 70 and x <= 79:
    print("C aldınız.") 
elif x >= 60 and x <= 69:
    print("D aldınız.")
elif x >= 0 and x <= 59: 
    print("F aldınız.")
```

    Notunuz: 99
    A aldınız.


### not yapısı

Bu yapı **değil** anlamına gelmektedir. Bu yapıyı kullandığımız yerde durum istediğimiz duruma eşit değilse gerekli işlemleri yapmaktadır.


```python
parola = input("parola: ")

if not parola:
    print("Parola boş bırakılamaz!")
else:
    print("Parola dolu.")
```

    parola: 
    Parola boş bırakılamaz!


## Değer Atama işleçleri

| İşleç |                  İşlevi                  |
|:-----:|:----------------------------------------:|
|   =   |                Değer Atama               |
|   +=  |           Topla ve Sonucu Aktar          |
|   -=  |           Çıkar ve Sonucu Aktar          |
|   /=  |            Böl ve Sonucu Aktar           |
|   *=  |           Çarp ve Sonucu Aktar           |
|   %=  |        Kalanı Bul ve Sonucu Aktar        |
|  **=  |         Üssünü Al ve Sonucu Aktar        |
|  //=  | Taban Bölme İşlemini Yap ve Sonucu Aktar |

Tabloda bulunan işleçleri tek tek inceleyelim. 


```python
a = 5 #değer atama
```


```python
c = 5 
c += 5 #toplama işlemi
print(c)
```

    10



```python
#Yukarıda yaptığımız toplama işleminin eş değeri.
b = 5
b = b + 5
print(b)
```

    10



```python
d = 2
d -= 1 #çıkarma işlemi
print(d)
```

    1



```python
e = 4
e /= 3 #bölme işlemi
print(e)
```

    1.3333333333333333



```python
f = 5
f *= 2 #çarpma işlemi
print(f)
```

    10



```python
g = 10
g %= 3
print(g)
```

    1



```python
h = 2
h **= 3
print(h)
```

    8



```python
k = 3
k //= 2
print(k)
```

    1


## Aitlik İşleçleri

Aitlik işleçleri, bir karakter dizisi ya da sayının, herhangi bir veri tipi içinde bulunup bulunmadığını sorgulamamızı sağlayan işleçlerdir.


```python
rakamlar = "12345"
"1" in rakamlar
```




    True




```python
"7" in rakamlar
```




    False



## Kimlik İşleçleri

Python’da her şeyin (ya da başka bir deyişle her nesnenin) bir kimlik numarası (identity) vardır. Kabaca söylemek gerekirse, bu kimlik numarası denen şey esasında o nesnenin bellekteki adresini gösterir.

Bu kimlik numarasına **id()** isimli fonksiyon ile erişebiliriz.


```python
m = 5
id(m)
```




    4480324880




```python
n = 20
id(n)
```




    4480325360



> Son Güncelleme: 16 Aralık 2019 - Pazartesi
