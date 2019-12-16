# Kullanıcıdan Bilgi Almak

Kullanıcıdan bilgi almak, geliştirdiğimiz yazılımların kullanıcıya özgü bilgiler üretmesi için elzem bir durumdur. Bu yüzden python içerisinde bulunan ve kullanıcıdan bilgi almamıza yarayan bir fonksiyondur.

## input() fonksiyonu


```python
isim = input("İsminiz nedir? ")
```

    İsminiz nedir? Abdullah



```python
print("Merhaba", isim, end="!\n")
```

    Merhaba Abdullah!


Gördüğünüz gibi input() fonksiyonu etkileşimli bir yazılım üretmemiz konusunda kolaylık sağlıyor. Peki bu fonksiyonu kullanarak bir adet toplama işlemi yaptıralım;


```python
sayi1 = input("1. Sayıyı giriniz?: ")
```

    1. Sayıyı giriniz?: 1



```python
sayi2 = input("2. Sayıyı giriniz: ")
```

    2. Sayıyı giriniz: 0



```python
toplam = sayi1 + sayi2
```


```python
print("Toplam işleminin sonucu: ",toplam)
```

    Toplam işleminin sonucu:  10


Yukarıda bulunan işlemi incelediğimiz taktirde bir hatanın olduğunu görüyoruz. Bu hata toplama işlemi yerine iki adet cümleyi yan yana yazdırma işlemi yapmış olması. Peki bu durumun sebebi ne, neden iki sayıyı toplamak yerine bu iki sayıyı yan yana yazdırdı. Burada bakmamız gereken yapı, girdiğimiz sayıların tipinin sayı mı olduğu yoksa cümlemi olduğu. Hadi bu bakalım.


```python
type(sayi1)
```




    str




```python
type(sayi2)
```




    str




```python
type(toplam)
```




    str



Yukarıda da gördüğünüz gibi sayi1, sayi2 ve toplam değişkenlerinin tipi string. Bu durumda bizim kullanıcıdan aldığımız değerlerin tiplerini dönüştürmemiz gerekmektedir. Şİmdi de bu konuyu öğrenelim.

## Tip Dönüşümleri

Tip dönüşümleri, değişkenlerin farklı tiplere dönüştürülmesini sağlar.

### int()

Bu yapı değişkenimizi int tipine dönüştürmemizi sağlar.


```python
str_sayi = "1"
int_sayi = int(str_sayi)
print("str_sayi: ",type(str_sayi))
print("int_sayi: ",type(int_sayi))
```

    str_sayi:  <class 'str'>
    int_sayi:  <class 'int'>


string tipindeki değişkeni int() fonksiyonu ile int tipine dönüştürdük. Böylece bu değişkeni matematiksel işlemlerde kullanabiliriz.

### str()

Bu yapı değişkenimizin tipini str tipine dönüştürmemizi sağlar.


```python
sayi = 5
karakter = str(sayi)
print("sayinin tipi: ",type(sayi))
print("karakterin tipi: ",type(karakter))
```

    sayinin tipi:  <class 'int'>
    karakterin tipi:  <class 'str'>


### float()

Bu yapı değişkenimizi float tipine dönüştürmemizi sağlar. Bu tür bildiğiniz üzere kayan noktalı sayılar oluyor. Örnek vermek gerekirse 1,5 gibi.


```python
a = 42
print(a)
type(a)
```

    42





    int




```python
a = float(a)
print(a)
type(a)
```

    42.0





    float



### complex()

Bu yapı değişkenimizi complex tipine dönüştürmemizi sağlar. Bu tür bildiğiniz üzere karmaşık sayılar oluyor. Örnek vermek gerekirse 15+0j gibi.


```python
type(15+0j)
```




    complex



Bu kısımda öğrendiklerimiz ile yukarıda yapmaya çalıştığımız, kullanıcıdan iki adet sayı alıp bunları toplama işlemini yapalım.


```python
sayi1 = int(input("1. sayıyı giriniz: "))
```

    1. sayıyı giriniz: 1



```python
sayi2 = int(input("2. sayıyı giriniz: "))
```

    2. sayıyı giriniz: 1



```python
toplam = sayi1 + sayi2
```


```python
print("Toplam: ",toplam)
```

    Toplam:  2


## format() Metodu

Bu fonksiyon, print fonksiyonunu daha etkili kullanabilmemiz ve bazı işlemleri daha etkili yapmamız sağlar. Hemen bir örnek ile inceleyelim.


```python
dil1 = "Python"
dil2 = "Java"

print("{} ve {} bir progralama dilidir.".format(dil1,dil2))
```

    Python ve Java bir progralama dilidir.


Bu yapıyı kullanıcıdan aldığımız bilgileri print fonksiyonu ile ekranda gösterebiliriz.

> Son Güncelleme: 16 Aralık 2019 - Pazartesi
