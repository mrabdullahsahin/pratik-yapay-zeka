# format() Metodu

Bu metod kullanıcıya daha güzel çıktılar verebilmemiz konusunda işlerimizi kolaylaştırmaktadır. Bir örnek üzerinden inceleyelim:


```python
print("{} ve {} iyi bir ikilidir.".format("Django", "Python"))
```

    Django ve Python iyi bir ikilidir.


Yukarıdaki örnekte olduğu gibi istediğimiz şekilde çıkıtıyı ayarlayıp daha sonra çıktıda boşluklara gelmesi gereken yerleri tek tek dolduruyoruz. Peki kullanıcıdan bilgi aldığımız zaman nasıl olacak, bir örnek üzerinden bakalım:


```python
deger = input("Bir değer giriniz: ")

print("Girmiş olduğunuz deger {}, umarım bu bir sayı değildir.".format(deger))
```

    Bir değer giriniz: kelime
    Girmiş olduğunuz deger kelime, umarım bu bir sayı değildir.


Biraz daha karmaşık bir örnek üzerinden bakalım format metoduna:


```python
kalkış = input("Kalkış yeri: ") 
varış = input("Varış yeri: ") 
isim_soyisim = input("İsim ve soyisim: ") 
bilet_sayısı = input("Bilet sayısı: ")

print("""{} noktasından {} noktasına, 14:30 hareket saatli 
sefer için {} adına {} adet bilet ayrılmıştır!""".format(kalkış,
                                                         varış,
                                                         isim_soyisim,
                                                         bilet_sayısı))
```

    Kalkış yeri: Konya
    Varış yeri: İstanbul
    İsim ve soyisim: Abdullah
    Bilet sayısı: 1
    Konya noktasından İstanbul noktasına, 14:30 hareket saatli 
    sefer için Abdullah adına 1 adet bilet ayrılmıştır!


Eğer istersek şu şekilde bir kullanımda mevcut:


```python
"{0} {1}".format("Python", "Django")
```




    'Python Django'



Bir başka kullanım:


```python
"{1} {0}".format("Python", "Django")
```




    'Django Python'



Diğer bir örnek:


```python
"{0} {1} ({1} {0})".format("Python", "Django")
```




    'Python Django (Django Python)'



Parantez içerisinde sayı kullanmak yerine isimde kullanabiliriz.


```python
print("{dil} ve {web} dersleri".format(dil="python", web="django"))
```

    python ve django dersleri


{} işaretleri arasında bazı sayılar kullanarak, karakter dizileri üzerinde hizalama işlemleri de yapabiliriz.

- "> sağa yaslama"
- "< sola yaslama" 
- "^ ortalama"


```python
print("|{:>15}|".format("python"))
```

    |         python|


Burada bu > işaret karakterin sağa yaslanacağını ve 15 sayısı ise işlemin 15 karakterlik bir alanda gerçekleştirileceğini belirtmektedir.


```python
print("|{:<15}|".format("python"))
```

    |python         |


Bir diğer örnek:


```python
print("|{:^15}|".format("python"))
```

    |    python     |


## Biçimlendirme Karakterleri

format ile birlikte bazı harfleri kullanabiliriz.

### s

Bu harf karakter dizilerini temsil eder.


```python
print("{:s} ve {:s} iyi bir ikilidir!".format("Python", "Django"))
```

    Python ve Django iyi bir ikilidir!


### c

Bu harf 0 ile 256 arası sayıların ASCII tablosundaki karşılıklarını temsil eder:


```python
print("{:c}".format(65))
```

    A


### d

Bu harf sayıları temsil eder:


```python
print("{:d}".format(1453))
```

    1453


### o

Bu harf onlu düzendeki sayıları sekizli düzendeki karşılıklarına çevirir:


```python
print("{:o}".format(1453))
```

    2655


### x

Bu harf onlu düzendeki sayıları onaltılı düzendeki karşılıklarına çevirir:


```python
print("{:x}".format(1453))
```

    5ad


### X

Tıpkı x harfinde olduğu gibi, bu harf de onlu düzendeki sayıları onaltılı düzendeki karşılıklarına çevirir:


```python
"{:X}".format(1453)
```




    '5AD'



### b

Bu işaret, onlu düzendeki sayıları ikili düzendeki karşılıklarına çevirir:


```python
"{:b}".format(2)
```




    '10'



### f

Bu işaret, karakter dizileri içindeki kayan noktalı sayıları temsil etmek için kullanılır.


```python
print("Dolar %f TL olmuş..." %1.4710)
```

    Dolar 1.471000 TL olmuş...


Bir başka örnek:


```python
print("{:.2f}".format(50))
```

    50.00


> Son Güncelleme: 19 Aralık 2019 - Perşembe
