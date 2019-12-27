## İleri Düzey Fonksiyonlar

### Lambda Fonksiyonları

Bu fonksiyonu tanımlamamıza yarayan ifade def ifadesinden farklı olarak lambda olduğu için bu fonksiyonları adı lambda fonksiyonlarıdır.

lambda fonksiyonu için bir örnek verelim:


```python
fonk = lambda param1, param2: param1 + param2
```

Tanımladığımız fonksiyon iki sayıyı toplama işlemini yapmaktadır. lambda fonksiyonlarını def ifadesi ile tanımladığımız fonksiyonlar gibi kullanabiliriz:


```python
fonk(2, 4)
```




    6



Lambda fonksiyonlarını, bir fonksiyonun işlevselliğine ihtiyaç duyduğumuz, ama konum olarak bir fonksiyon tanımlayamayacağımız veya fonksiyon tanımlamanın zor ya da meşakkatli olduğu durumlarda kullanabiliriz.

Diyelim ki bir sayının çift sayı olup olmadığını denetleyen bir fonksiyon yazmak istiyorsunuz. Bunun için şöyle bir fonksiyon tanımlayabileceğimizi biliyorsunuz:


```python
def cift_mi(sayi):
    return sayi % 2 == 0
```

Eğer cift_mi() fonksiyonuna parametre olarak verilen bir sayı çift ise fonksiyonumuz True çıktısı verecektir:


```python
 print(cift_mi(100))
```

    True


Aksi halde False çıktısı alırız:


```python
print(cift_mi(99))
```

    False


İşte yukarıdaki etkiyi lambda fonksiyonları yardımıyla da elde edebiliriz. 

Dikkatlice bakın:


```python
cift_mi_2 = lambda sayi: sayi % 2 == 0
```


```python
cift_mi_2(100)
```




    True




```python
cift_mi_2(99)
```




    False



Sözün özü, mesela şu kod:

```python
lambda x: x + 10
```

Türkçede şu anlama gelir:

 'x' adlı bir parametre alan bir lambda fonksiyonu tanımla. 
 
 Bu fonksiyon, bu 'x parametresine 10 sayısını eklesin.

Biz yukarıdaki örneklerde lambda fonksiyonunu tek bir parametre ile tanımladık. Ama elbette lambda fonksiyonlarının birden fazla parametre de alabileceğini de biliyorsunuz.

Örneğin:


```python
birlestir = lambda ifade, birlestirici: birlestirici.join(ifade.split())
```

Burada lambda fonksiyonumuz toplam iki farklı parametre alıyor: Bunlardan ilki ifade, ikincisi ise birleştirici. Fonksiyonumuzun gövdesinde ifade parametresine split() metodunu uyguladıktan sonra, elde ettiğimiz parçaları birleştirici parametresinin değerini kullanarak birbirleriyle birleştiriyoruz. Yani:


```python
birlestir('Python Programlama Dili', '-')
```




    'Python-Programlama-Dili'



### Özyinelemeli (Recursive) Fonksiyonlar

Bu fonksiyonlara, **‘kendi kendilerini yineleyen’**, veya daha teknik bir dille ifade etmek gerekirse **‘özyinelemeli’ (recursive ) fonksiyonlar** adı verilir.

Özyinelemeli fonksiyonlar için aşağıda örneği inceleyelim:


```python
def azalt(s):
    if len(s) < 1:
        return s
    else:
        print(s)
        return azalt(s[1:])
    
print(azalt('python'))
```

    python
    ython
    thon
    hon
    on
    n
    


Fonksiyonumuzu yazıp çalıştırdığımıza ve bu fonksiyonun bize nasıl bir çıktı verdiğini gördüğümüze göre fonksiyonu açıklamaya geçebiliriz.

Bu fonksiyon ilk bakışta daha önce öğrendiğimiz fonksiyonlardan çok da farklı görünmüyor aslında. Ama eğer fonksiyonun son kısmına bakacak olursanız, bu fonksiyonu daha önce öğrendiğimiz fonksiyonlardan ayıran şu satırı görürsünüz:

```python
return azalt(s[1:])
```

Gördüğünüz gibi, burada azalt() fonksiyonu içinde yine azalt() fonksiyonunu çağırıyoruz. Böylece fonksiyonumuz sürekli olarak kendi kendini yineliyor. Yani aynı fonksiyonu tekrar tekrar uyguluyor.

> Son Güncelleme: 27 Aralık 2019 - Cuma
