# Hata Yakalama

Geliştirdiğimiz programlarda kullanıcı bazen istenilenin dışında bilgiler girebilir. Böyle durumlarda hatalar ile karşılaşacaktır. Bu hatalarda kullanıcının anlayamacağını şekilde karmaşık çıktılar verebilir. Böyle olunca bu hatalar yaşanabileceğin için hataları kullanıcının anlayabileceği ve nerede hata yaptığını ona açık bir şekilde belirten bir yapı oluşturmamız gerekmektedir. Bu kısımda bu durumu ayrıntılı bir şekilde inleceyeceğiz.

## Hata Türleri

Hataları üç farklı başlık altında inceleyeğiz:

1. Programcı Hataları(Error)

2. Program Kusuları(Bug)

3. İstisnalar(Exception)

### Programcı Hataları(Error)

Başlıktanda anlaşılacağı üzere programcının yapmış olduğu hatalardır. Bunlar yazım hataları ve tanımlama hataları gibi hatalardan oluşurlar. Bir örnek ile inceleyelim:


```python
print "Merhaba Dünya"
```


      File "<ipython-input-1-267fc15c875c>", line 1
        print "Merhaba Dünya"
                            ^
    SyntaxError: Missing parentheses in call to 'print'. Did you mean print("Merhaba Dünya")?



Yukarıdaki örnekte görüldüğü üzere print fonksiyonu için parantezleri yazmadığımız için hata oluştu. Bu tür hatalar programcı hatalarıdır.

### Program Kusurları(Bug)

Program kusurları çoğu zaman hata vermeden çalışır fakat ürettiği sonuçlar istediğimiz gibi değildir. Örnek vermek gerekirse formül gerektiren bir programda eğer formülü yanlış yazmışsanız program çalışır yalnız sonuç hatalı olur. Bu durumu bir örnek ile inceleyelim.


```python
sayi1 = input("Toplama işlemi için ilk sayıyı girin: ") 
sayi2 = input("Toplama işlemi için ikinci sayıyı girin: ")

print(sayi1, "+", sayi2, "=", sayi1 + sayi2)
```

    Toplama işlemi için ilk sayıyı girin: 1
    Toplama işlemi için ikinci sayıyı girin: 2
    1 + 2 = 12


Yukarıdaki örnekte görüldüğü üzere program iki sayıyı toplamak yerine onları yan yana yazdırmaktadır. Biz kullanıcıdan sayıları alırken int türüne dönüşümlerini sağlamadığımız için hata oluştu.

### İstisnalar(Exception)

İstisnalar, bir programın çalışması sırasında ortaya çıkan, normalden farklı, istisnai durumlardır. Matematiksel bir işlem yapılması gereken bir yerde kullanıcı eğer harfsel bir veri girerse hataya sebep olur. Bu durumu inceleyelim:


```python
sayi1 = int(input("Bir sayı giriniz: "))
sayi2 = int(input("Bir sayı giriniz: "))

print("Sonuç: ",sayi1 / sayi2)
```

    Bir sayı giriniz: 1
    Bir sayı giriniz: a



    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-3-5310f8e3b775> in <module>
          1 sayi1 = int(input("Bir sayı giriniz: "))
    ----> 2 sayi2 = int(input("Bir sayı giriniz: "))
          3 
          4 print("Sonuç: ",sayi1 / sayi2)


    ValueError: invalid literal for int() with base 10: 'a'


Örnektede görüldüğü gibi kullanıcı sayısal bir veri girmesi gerekirken harfsel bir veri girdiği için programda hata oluştu.

Bir başka örnekte matematikte bulunan istisnai durumlar. Sayıların 0'a bölünme durumu bir hatadır. Bu durumu inceleyelim.


```python
sayi1 = int(input("Bir sayı giriniz: "))
sayi2 = int(input("Bir sayı giriniz: "))

print("Sonuç: ",sayi1 / sayi2)
```

    Bir sayı giriniz: 1
    Bir sayı giriniz: 0



    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-4-5310f8e3b775> in <module>
          2 sayi2 = int(input("Bir sayı giriniz: "))
          3 
    ----> 4 print("Sonuç: ",sayi1 / sayi2)
    

    ZeroDivisionError: division by zero


Program hata olarak division by zero yani sıfıra bölünme hatası verdi. Bu gibi durumları yakalayıp programımızı bu tür hatalardan temizlememiz gerekmektedir. Şimdide bunları nasıl yapabileceğimizi görelim.

## try..... except.....

Hata Türleri kısmında hataların neler olduğundan bahsettik. Bu bölümde bu hataların nasıl yakalanacağını inceleyeceğiz. Yukarıda hata ile karşılaştığımız programları tek tek düzeltelim.


```python
try:
    sayi1 = int(input("Bir sayı giriniz: "))
    sayi2 = int(input("Bir sayı giriniz: "))
    print("Sonuç: ",sayi1 / sayi2)
except ValueError:
    print("Lütfen sadece sayı giriniz!")
```

    Bir sayı giriniz: 1
    Bir sayı giriniz: a
    Lütfen sadece sayı giriniz!


Yukarıda çözdüğüm kod parçasını inceleyelim. 

try: 

    Bu bloğa hata olması beklenen kodları yazmamız gerekmektedir.
    
except Hata_adi:

    Bu bloğa kullanıcıya gösterilmesini istediğimiz mesajı yazıyoruz.

Şimdide sıfıra bölünme hatası durumunu çözelim.


```python
try:
    sayi1 = int(input("Bir sayı giriniz: "))
    sayi2 = int(input("Bir sayı giriniz: "))

    print("Sonuç: ",sayi1 / sayi2)
except ZeroDivisionError:
    print("Herhangi bir sayı sıfıra bölünemez.")
```

    Bir sayı giriniz: 1
    Bir sayı giriniz: 0
    Herhangi bir sayı sıfıra bölünemez.


Peki hem sıfıra bölünme hatası yaşanabilecek hem de değer hatası olabilmesi durumunda ne yapmamız gerekiyor. Bu durumu iki farklı yol ile çözebiliriz:

**1. Yol**


```python
try:
    sayi1 = int(input("Bir sayı giriniz: "))
    sayi2 = int(input("Bir sayı giriniz: "))

    print("Sonuç: ",sayi1 / sayi2)
except ZeroDivisionError:
    print("Herhangi bir sayı sıfıra bölünemez.")
except ValueError:
    print("Lütfen sadece sayı giriniz.")
```

    Bir sayı giriniz: 1
    Bir sayı giriniz: 0
    Herhangi bir sayı sıfıra bölünemez.


**2. Yol**


```python
try:
    sayi1 = int(input("Bir sayı giriniz: "))
    sayi2 = int(input("Bir sayı giriniz: "))

    print("Sonuç: ",sayi1 / sayi2)
except (ZeroDivisionError, ValueError):
    print("Bir hata ile karşılaşıldı.")
```

    Bir sayı giriniz: a
    Bir hata ile karşılaşıldı.


## try..... except..... as.....

Bu yapıda hatanın adını değilde hatanın tam olarak ne olduğunu hataya dair açıklamayı öğrenebiliyoruz. Örnek üzerine inceleyelim:


```python
try:
    sayi1 = int(input("Bir sayı giriniz: "))
    sayi2 = int(input("Bir sayı giriniz: "))

    print("Sonuç: ",sayi1 / sayi2)
except ValueError as hata:
    print(hata)
```

    Bir sayı giriniz: 1
    Bir sayı giriniz: a
    invalid literal for int() with base 10: 'a'


Gördüğünüz gibi hatanın adını değilde direk hatanın tam olarak ne olduğunu açıklamasını ekranda gösterdik.

## try..... except..... else.....

Yazdığımı programlarda birçok farklı hata ile karşılaşabiliriz. Hataları farklı bir şekilde karşılayıp farklı kullanıcı mesajları vermek isteyebiliriz. Bu durum genelde pek tavsiye edilmez çünkü kodumuz çok parçalı olacağından dolayı. Fakat biz yinede bu durumuda inceleyelim:


```python
try:
    bölünen = int(input("bölünecek sayı: ")) 
    bölen = int(input("bölen sayı: "))
except ValueError:
    print("Lütfen sadece sayı girin!")
else: 
    try:
        print(bölünen/bölen)
    except ZeroDivisionError:
        print("Bir sayıyı 0'a bölemezsiniz!")
```

    bölünecek sayı: 1
    bölen sayı: 0
    Bir sayıyı 0'a bölemezsiniz!


Yukarıdaki kod bloğundanda anlaşıldığı üzere sıfıra bölünme durumunu farklı bir alanda yakalayıp kontrol ediyor ve buna uygun bir mesaj veriyoruz kullanıcıya. Bu durumu kullanıcı açısından düşündüğümüz zaman güzel bir şey fakat hatalar birkaç tane olmadığı için böyle bir şey yapmamız kodumuzun çok parçalı olmasına ve çalıştığımız proje büyüdükçe kontrol zorlaşacağı için bu durumu pek tavsiye edilmez.

## try..... except..... finally.....

Bu kod yapısında hata olsun veya olmasın her daim finally bloğu çalıştırılır. Bir örnek üzerinden inceleyelim:


```python
try:
    sayi1 = int(input("Bir sayı giriniz: "))
    sayi2 = int(input("Bir sayı giriniz: "))

    print("Sonuç: ",sayi1 / sayi2)
except ZeroDivisionError:
    print("Herhangi bir sayı sıfıra bölünemez.")
finally:
    print("Finally her zaman çalışır.")
```

    Bir sayı giriniz: 1
    Bir sayı giriniz: 0
    Herhangi bir sayı sıfıra bölünemez.
    Finally her zaman çalışır.


## raise

Bazen yazdığımız programlarda hata oluşmayacak olsa bile biz bu tür durumlarda bir hata mesajı göstermek isteyebiliriz. Bir örnek ile inceleyelim:


```python
bölünen = int(input("bölünecek sayı: ")) 
if bölünen == 5:
    raise Exception("5 sayısını kullanamazsınız.")
    
bölen = int(input("bölen sayı: ")) 
print(bölünen/bölen)
```

    bölünecek sayı: 5



    ---------------------------------------------------------------------------

    Exception                                 Traceback (most recent call last)

    <ipython-input-14-d3500b3eb850> in <module>
          1 bölünen = int(input("bölünecek sayı: "))
          2 if bölünen == 5:
    ----> 3     raise Exception("5 sayısını kullanamazsınız.")
          4 
          5 bölen = int(input("bölen sayı: "))


    Exception: 5 sayısını kullanamazsınız.


Burada raise kelimesinden sonra bulunan Exception anahtar kelimesinin yerine istediğimizi yazamayız. Onun yerine sadece Python içinde bulunan hata belirten anahtar kelimelerini kullanabiliriz. Bu kelimelere örnek vermek gerekirse NameError, TypeError, ZeroDivisionError, vb...

## Bütün Hataları Yakalamak

Geliştirdiğimiz programda beklediğimiz hataların dışında beklemediğimiz hatalar ile de karşılaşabiliriz. Bu durumu önlemek için beklediğimiz hataların dışından bulunan bütün hatalarıda yakalamamız gerekmektedir. Bir örnek ile inceleyelim:


```python
try:
    sayi1 = int(input("Bir sayı giriniz: "))
    sayi2 = int(input("Bir sayı giriniz: "))

    print("Sonuç: ",sayi1 / sayi2)
except ZeroDivisionError:
    print("Herhangi bir sayı sıfıra bölünemez.")
except ValueError:
    print("Lütfen sadece sayı giriniz.")
except:
    print("Bir hata ile karşılaşıldı.")
```

    Bir sayı giriniz: 1
    Bir sayı giriniz: 2
    Sonuç:  0.5


## Diğer Hatalar

Python içerisinde bulunan diğer hataların neler olduğunu öğrenmek isterseniz eğer <a href="https://docs.python.org/3/library/exceptions.html" target="_blank"> <strong>buradan</strong></a> öğrenebilirsiniz.

> Son Güncelleme: 17 Aralık 2019
