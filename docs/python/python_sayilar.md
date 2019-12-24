# Sayılar

Python'da üç tür sayı bulunmaktadır:

1. Tam Sayılar (integer)
2. Kayan Noktalı Sayılar (floating point numbers veya kısaca float)
3. Karmaşık Sayılar (complex numbers)

Eğer bir veri type(veri) sorgulamasına int cevabı veriyorsa o veri bir tam sayıdır. Eğer bir veri type(veri) sorgulamasına float cevabı veriyorsa o veri bir kayan noktalı sayıdır. Eğer bir veri type(veri) sorgulamasına complex cevabını veriyorsa o veri bir karmaşık sayıdır.

Mesela şunlar birer tam sayıdır: 15, 4, 33

Şunlar birer kayan noktalı sayıdır: 3.5, 6.6, 2.3

Şunlarsa birer karmaşık sayıdır: 3+3j, 5+2j, 19+10j

| Fonksiyon |                   Görevi                   |    Örnek   |
|:---------:|:------------------------------------------:|:----------:|
|   int()   |      Bir veriyi tam sayıya dönüştürür      |  int("2")  |
|  float()  | Bir veriyi kayan noktalı sayıya dönüştürür |  float(2)  |
| complex() |    Bir veriyi karmaşık sayıya dönüştürür   | complex(2) |


## Sayıların Metotları

### Tam Sayıların Metotları

Tam sayıların hangi metotlar ve nitelikleri olduğuna bakalım:


```python
[i for i in dir(int) if not i.startswith("_")]
```




    ['bit_length',
     'conjugate',
     'denominator',
     'from_bytes',
     'imag',
     'numerator',
     'real',
     'to_bytes']



#### bit_length()

Bilgisayarlar ancak ve ancak sayılarla işlem yapabilir. Bilgisayarların işlem yapabildiği sayılar da onlu sistemdeki sayılar değil, ikili sistemdeki sayılardır. Yani 0’lar ve 1’ler. ,

İşte herhangi bir tam sayının kaç bit’lik bir yer kapladığını öğrenmek için, tam sayıların metotlarından biri olan bit_length() metodundan yararlanacağız:


```python
sayi = 10
sayi.bit_length()
```




    4



Demek ki 10 sayısı bellekte dört bitlik bir yer kaplıyormuş. Yani bu sayının ikili sistemdeki karşılığı olan 1010 sayısı dört basamaktan oluşuyormuş.

bit_length() metodunu doğrudan sayılar üzerine uygulayamıyoruz. Yani:


```python
10.bit_length()
```


      File "<ipython-input-4-2c75d808345c>", line 1
        10.bit_length()
                    ^
    SyntaxError: invalid syntax



Eğer direk sayı üzerinde kullanmak istiyorsak şöyle yapmalıyız:


```python
(10).bit_length()
```




    4



### Kayan Noktalı Sayıların Metotları

Kayan noktalı sayıların hangi metotlar ve nitelikleri olduğuna bakalım:


```python
[i for i in dir(float) if not i.startswith("_")]
```




    ['as_integer_ratio',
     'conjugate',
     'fromhex',
     'hex',
     'imag',
     'is_integer',
     'real']



#### as_integer_ratio()

Bu metot, birbirine bölündüğünde ilgili kayan noktalı sayıyı veren iki adet tam sayı verir bize. Örnek üzerinden açıklayalım:


```python
sayı = 4.5

sayı.as_integer_ratio()
```




    (9, 2)



9 sayısını 2 sayısına böldüğümüzde 4.5 sayısını elde ederiz. İşte as_integer_ratio() metodu, bu 9 ve 2 sayılarını bize ayrı ayrı verir.

#### is_integer()

Bir kayan noktalı sayının ondalık kısmında 0 harici bir sayının olup olmadığını kontrol etmek için bu metodu kullanıyoruz. Örneğin:


```python
(12.0).is_integer()
```




    True




```python
(12.5).is_integer()
```




    False



### Karmaşık Sayıların Metotları

Gelelim karmaşık sayıların metot ve niteliklerine...


```python
[i for i in dir(complex) if not i.startswith("_")]
```




    ['conjugate', 'imag', 'real']



#### imag

Bir gerçek bir de sanal kısımdan oluşan sayılara karmaşık sayılar (complex) adı verildiğini biliyorsunuz. Örneğin şu bir karmaşık sayıdır:

12+4j

İşte imag adlı nitelik, bize bir karmaşık sayının sanal kısmını verir:


```python
c = 12+4j

c.imag
```




    4.0



#### real

real adlı nitelik bize bir karmaşık sayının gerçek kısmını verir:


```python
c = 12+4j
    
c.real
```




    12.0



## Aritmetik Fonksiyonlar

Python programlama dili, bize sayılarla rahat çalışabilmemiz için bazı fonksiyonlar sunar. Bu fonksiyonları kullanarak, karmaşık aritmetik işlemleri kolayca yapabiliriz.

Bu fonksiyonları inceleyelim:

### abs()

Bu fonksiyon bize bir sayının mutlak değerini verir:


```python
abs(-2)
```




    2



### divmod()

Bu fonksiyon, bir sayının bir sayıya bölünmesi işleminde bölümü ve kalanı verir:


```python
divmod(10, 2)
```




    (5, 0)



10 sayısı 2 sayısına bölündüğünde ‘bölüm’ 5, ‘kalan’ ise 0 ‘dır.

Aslında divmod() fonksiyonu şu kodlarla aynı işi yapıyor:


```python
14 // 3, 14 % 3
```




    (4, 2)



### max()

Bir liste içerisinde bulunan en büyük değeri getirir. Değer dedik çünkü karakter dizilerinin bulunduğu listelerde de en uzun karakter dizisini getirir.

Sayı listesi üzerinde deneyelim:


```python
liste = [882388, 260409, 72923, 692476, 131925, 259114, 47630, 84513, 25413, 614654,
 239479, 299159, 175488, 345972, 458112, 791030, 243610, 413702, 565285,
 773607, 131583, 979177, 247202, 615485, 647512, 556823, 242460, 852928,
 893126, 792435, 273904, 544434, 627222, 601984, 966446, 384143, 308858,
 915106, 914423, 826315, 258342, 188056, 934954, 253918, 468223, 262875,
 462902, 370061, 336521, 367829, 147846, 838385, 605377, 175140, 957437,
 105779, 153499, 435097, 9934, 435761, 989066, 357279, 341319, 420455,
 220075, 28839, 910043, 891209, 975758, 140968, 837021, 526798, 235190,
 634295, 521918, 400634, 385922, 842289, 106889, 742531, 359913, 842431,
 666182, 516933, 22222, 445705, 589281, 709098, 48521, 513501, 277645,
 860937, 655966, 923944, 7895, 77482, 929007, 562981, 904166, 619260,
 616293, 203512, 67534, 615578, 74381, 484273, 941872, 110617, 53517,
 402324, 156156, 839504 , 625325, 694080, 904277, 163914, 756250, 809689,
 354050, 523654, 26723, 167882, 103404, 689579, 121439, 158946, 485258,
 850804, 650603, 717388, 981770, 573882, 358726, 957285, 418479, 851590,
 960182, 11955, 894146, 856069, 369866, 740623, 867622, 616830, 894801]
```


```python
max(liste)
```




    989066



Karakter dizisi üzerinde deneyelim:


```python
isimler = ["ahmet", "mehmet", "necla", "sedat", "abdullah", "gıyaseddin", "sibel", "can", "necmettin", "savaş", "özgür"]
```

max() fonksiyonu ile en uzun karakteri getirelim:


```python
print(max(isimler, key=len))
```

    gıyaseddin


Gördüğünüz gibi, max() fonksiyonu key adlı özel bir parametre daha alıyor. Bu parametreye biz ‘len’ değerini verdik. Böylece max() fonksiyonu liste içindeki öğeleri uzunluklarına göre sıralayıp en uzun öğeyi bize sundu.

### min()

Bu fonksiyon, max() fonksiyonun yaptığı işin tam tersini yapar. Yani bu fonksiyonu kullanarak bir dizi içindeki en küçük sayıyı bulabilirsiniz:


```python
min(liste)
```




    7895



Bu fonksiyonuda karakter dizileri üzerinde kullanabiliriz:


```python
print(min(isimler, key=len))
```

    can


### sum()

Bu fonksiyon bir dizi içinde yer alan bütün sayıları birbiriyle toplar. Örneğin:


```python
a = [10, 20, 43, 45 , 77, 2, 0, 1]

sum(a)
```




    198



Eğer bu fonksiyonun, toplama işlemini belli bir sayının üzerine gerçekleştirmesini istiyorsanız şu kodu yazabilirsiniz:


```python
sum(a, 10)
```




    208



sum() fonksiyonuna bu şekilde ikinci bir parametre verdiğinizde, bu ikinci parametre toplam değere eklenecektir.

> Son Güncelleme: 24 Aralık 2019 - Salı
