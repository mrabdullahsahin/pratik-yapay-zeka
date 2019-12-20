# Listeler(list) ve Demetler(Tuple)

Listeler Python'daki veri tiplerinden biridir. 

## Liste Tanımlamak

Bir liste elde etmek için, öğeleri birbirinden virgülle ayırıp, bunların hepsini köşeli parantezler içine alıyoruz.


```python
liste = ["deger1","deger2","deger3"]
```

Tanımladığımız liste'nin bir liste olup olmadığını anlamak için type fonksiyonu kullanarak kontrol edelim.


```python
type(liste)
```




    list



Görmüş olduğunuz gibi tanımlamış olduğumuz liste adındaki değişken bir list tipinde.

Listeler çok farklı değerler barındırabilir. Yani sadece sayı değerleri değil aynı zamanda karakter dizisi değerleride içerebilir. Örneğin:


```python
liste = ["deger1","deger2",1,2,3,4]
```

Eğer istersek listenin içinde başka listelerde tanımlayabiliriz.


```python
liste = ["deger1","deger2",["degisken1","degisken2"],1,2,3,4]
```

liste değişkenimizin içeriğine bakalım:


```python
liste
```




    ['deger1', 'deger2', ['degisken1', 'degisken2'], 1, 2, 3, 4]



Peki listenin içerisinde bulunan değerlerin tiplerini kontrol edelim. Çünkü ikinci bir liste nasıl gözükmekte bakalım:


```python
for deger in liste:
    print("{} adlı öğenin veri tipi: {}".format(deger, type(deger)))
```

    deger1 adlı öğenin veri tipi: <class 'str'>
    deger2 adlı öğenin veri tipi: <class 'str'>
    ['degisken1', 'degisken2'] adlı öğenin veri tipi: <class 'list'>
    1 adlı öğenin veri tipi: <class 'int'>
    2 adlı öğenin veri tipi: <class 'int'>
    3 adlı öğenin veri tipi: <class 'int'>
    4 adlı öğenin veri tipi: <class 'int'>


Görmüş olduğunuz gibi listenin içerisinde bulunan diğer bir listede list tipindedir.

## list() Fonksiyonu

Bu fonksiyonu elimizde bulunan bir karakter dizisini listeye çevirmemize yarar.


```python
karakter_dizisi = "abcdefgh"
```

Bu karakter dizisini list fonksiyonu aracılığı ile bir list değişkenine çevirelim.


```python
liste = list(karakter_dizisi)
```

Liste değişkenin veri tipine bakalım:


```python
type(liste)
```




    list



liste değişkenin veri tipi list'tir. Şimdide içeriğine bakalım:


```python
liste
```




    ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h']



Eğer istersek range fonksiyonu ile de sayılardan oluşan bir listeyi hızlıca tanımlayabiliriz.


```python
sayilar = list(range(10))
```

Oluşturduğumuz sayilar listesinin veri tipine bakalım:


```python
type(sayilar)
```




    list



Şimdide sayilarin içeriğine bakalım:


```python
sayilar
```




    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]



## Listelerin Öğlerine Erişmek

Listelerin öğelerine erişebilmemiz için köşeli parantez içerisinde erişmek istediğimiz değerin sıra numarasını yazmamız gerekmektedir. Burada dikkat edilmesi gereken durum listelerdeki değerleri saymaya sıfırdan başlıyoruz.


```python
liste = ["deger1","deger2","deger3"]
```

liste değişkenin en son değerine erişelim. Bunun için iki yol mevcut.

1. Yol


```python
liste[2]
```




    'deger3'



2. Yol


```python
liste[-1]
```




    'deger3'



Karakter dizilerini dilimlemede olduğu gibi burada da listeyi dilimleyebiliriz.


```python
liste[0:2]
```




    ['deger1', 'deger2']



## Listelerin Öğelerini Değiştirmek

Listelerin öğelerini değiştirmek mümkün, bu durumu inceleyelim.


```python
renkler = ["kırmızı","beyaz","sarı","mor","kahverengi"]
```

renkler listemizin içeriğine bakalım:


```python
renkler
```




    ['kırmızı', 'beyaz', 'sarı', 'mor', 'kahverengi']



renkler değişkenimizin içerisinde bulunan sıfırıncı değeri yani kırmızı değerini gri ile değiştirelim:


```python
renkler[0] = "gri"
```

renkler listemizi tekrardan listeleyelim.


```python
renkler
```




    ['gri', 'beyaz', 'sarı', 'mor', 'kahverengi']



## Listeye Öğe Eklemek

Listelerin içerisine yeni öğeler eklemek mümkün. Bu durumu inceleyelim:


```python
renkler + ["lacivert"]
```




    ['gri', 'beyaz', 'sarı', 'mor', 'kahverengi', 'lacivert']



## Listeleri Birleştirmek


```python
diller1 = ["Python","Java","C#"]
diller2 = ["Go","C++","Fortran"]
```

Elimizde iki adet liste mevcut. Bu listeler yazılım dillerini barındırmaktadır. Bu listeleri birleştirelim.


```python
programlama = diller1 + diller2
```

Yeni oluşturduğumuz bu değişkenin veri tipine bakalım.


```python
type(programlama)
```




    list



Tanımladığımız değişkenin türü list, şimdide içeriğine bakalım:


```python
programlama
```




    ['Python', 'Java', 'C#', 'Go', 'C++', 'Fortran']



## Listeden Öğe Çıkarmak

Bir listeden öğe silmek için del adlı ifadeden yararlanabilirsiniz. Örneğin:


```python
del programlama[-1]
```

Listemizin içeriğine bakalım:


```python
programlama
```




    ['Python', 'Java', 'C#', 'Go', 'C++']



## Listeleri Silmek

Python’da listeleri tamamen silmek de mümkündür. Listeden öğe çıkarma işleminde olduğu gibi del fonksiyonu silmede kullanılmaktadır. Örneğin:


```python
del programlama
```

## Listeleri Kopyalamak

Listeleri kopyalarken dikkat edilmesi gereken çok önemli bir husus mevcut. İlk önce bu hususa değinelim daha sonra doğru yönteme bakalım.


```python
liste_1 = ["a","b","c"]
```

Bir başka değişkene liste_1 değişkenimizi kopyalayalım.


```python
liste_2 = liste_1
```

liste_2 değişkenimizin içeriğini kontrol edelim.


```python
liste_2
```




    ['a', 'b', 'c']



liste_2 içerisinde bir değişiklik yapalım.


```python
liste_2[0] = "e"
```

liste_2 değişkenimizin içeriğini kontrol edelim.


```python
liste_2
```




    ['e', 'b', 'c']



Görmüş olduğunuz gibi liste_2 değişkenimizin içeriği değişti. Peki liste_1 değişkenimizin içeriğinde durum nasıl:


```python
liste_1
```




    ['e', 'b', 'c']



liste_1 değişkenin içeriğinin değişmiş olması pek beklediğimiz bir durum değil. Bu durumun sebebi: Yazılım dillerinde oluşturduğumuz her değişkende RAM üzerinde bir alanda saklanmaktadır. Bu alan her değişken için farklıdır. Fakat bizim daha yeni yaptığımız kopyalama yönteminde RAM üzerinde bulunan alanı kopyalamış olduk. Peki bu iki değişkenin RAM üzerinde gösterdiği adreslere bakalım.


```python
id(liste_1)
```




    4559703968




```python
id(liste_2)
```




    4559703968



Görmüş olduğunuz gibi iki değişkende RAM üzerinde aynı noktayı göstermektedir. Peki liste kopyalamanın en doğru şekli nasıl, hadi inceleyelim:


```python
liste1 = ["a","b","c"]
```

liste1 değişkenimizi bir başka değişkene aktaralım.


```python
liste2 = liste1[:]
```

liste2 değişkenimizin içeriğini kontrol edelim.


```python
liste2
```




    ['a', 'b', 'c']



Şimdi liste2 üzerinde bir değişiklik yapalım.


```python
liste2[0] = "d"
```

liste2 değişkenin içeriğini kontrol edelim.


```python
liste2
```




    ['d', 'b', 'c']



liste1 değişkeninin içeriğini kontrol edelim:


```python
liste1
```




    ['a', 'b', 'c']



liste2 üzerinde yapmış olduğumuz değişken liste1 değişkenini etkilememiştir.

## Liste Üreteçleri (List Comprehensions)

Liste üreteçleri, adında anlaşıldığı üzere liste üretmeye yarayan yapıdır. Örnek üzerinden inceleyelim:


```python
liste = [i for i in range(10)]
```

Yukarıda bulunan kod satırları ile 0'dan 10'a kadar sayıların bulunduğu bir liste oluşturmaktadır. Yazmış olduğumuz bu kodun uzun versiyonunu yazalım:


```python
liste = []

for i in range(10): 
    liste += [i]
```

Yazmış olduğumuz uzun kod ile kısa kod aynı işi yapmaktadır. Biri kolaylık sunmaktadır.

Bir başka örnek üzerinden inceleyelim. 0'dan 10'a kadar olan sayılar içerisinde 2'ye tam bölülenleri listeleyelim.


```python
liste = [i for i in range(10) if i % 2 == 0]
```

Yazmış olduğumuz bu kodun normal versiyonunu yazalım:


```python
liste = []

for i in range(10):
    if i % 2 == 0: 
        liste += [i]
```

# Demetler

Demetler, özellikle görünüş olarak listelere çok benzeyen bir veri tipidir. Bu veri tipi de, tıpkı listeler gibi, farklı veri tiplerini içinde barındıran kapsayıcı bir veri tipidir.

## Demet Tanımlamak

Demet tanımlamanın birkaç yolu bulunmaktadır.

1. Yol


```python
demet = ("a","b",1,2)
```

Oluşturduğumuz bu değişkenin demet olup olmadığını anlamak için type fonksiyonu ile bakalım:


```python
type(demet)
```




    tuple



2. Yol


```python
demet = "a","b","c",1,2
```

Oluşturduğumuz bu değişkenin veri tipine bakalım:


```python
type(demet)
```




    tuple



İçeriğine bakalım:


```python
demet
```




    ('a', 'b', 'c', 1, 2)



3. Yol


```python
demet = tuple("abcd12345")
```

veri tipine bakalım:


```python
type(demet)
```




    tuple



İçeriğine bakalım:


```python
demet
```




    ('a', 'b', 'c', 'd', '1', '2', '3', '4', '5')



## Tek Öğeli Bir Demet Tanımlamak

Tek öğeli bir demet tanımlayalım:


```python
demet = ("a")
```

Tanımladığımız değişkenin demet olup olmadığına bakalım:


```python
type(demet)
```




    str



Tanımladığımız değişken bir karakter dizisi(str). Peki tek öğeli bir demet nasıl tanımlayabiliriz:

1. Yol


```python
demet = ("a"),
```

2. Yol


```python
demet = "a",
```

veri tipini kontrol edelim:


```python
type(demet)
```




    tuple



Yukarıda bulunan iki yöntem ile de demet tanımlayabilirsiniz.

## Demetlerin Öğelerine Erişmek

Demetlerin öğelerine erişebilmek listelerde olduğu gibi köşeli parantez içerisinde erişmek istediğimiz değerin sıra numarasını yazmamız yeterli:


```python
demet = ("deger1","deger2","deger3")
```


```python
demet[0]
```




    'deger1'




```python
demet[-1]
```




    'deger3'



## Demetlerle Listelerin Birbirinde Farkı

Demetlerle Listeler birbirine çok benzerler. Fakat çok belirgin farkları bulunmaktadır.

Demetler değiştirilemez(immutable) iken listeler değiştirilebilir(mutable) veri türüdür.


```python
demet = ("a","b","c","d")
```

demet değişkenimizin ilk değerini değiştirmeye çalışalım:


```python
demet[0] = "f"
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-73-0a94098063ff> in <module>
    ----> 1 demet[0] = "f"
    

    TypeError: 'tuple' object does not support item assignment


Görmüş olduğunuz gibi demet değişkenin ilk değerini değiştirmeye çalıştığımız zaman değiştiremeyeceğimizi belirtti.

Eğer programın akışı esnasında üzerinde değişiklik yapmayacağınız veya değişiklik yapılmasını istemediğiniz birtakım veriler varsa ve eğer siz bu verileri liste benzeri bir taşıyıcı içine yerleştirmek istiyorsanız, listeler yerine demetleri kullanabilirsiniz. Ayrıca demetler üzerinde işlem yapmak listelere kıyasla daha hızlıdır. Dolayısıyla, performans avantajı nedeniyle de listeler yerine demetleri kullanmak isteyebilirsiniz.

Bir demetin üzerinde değişiklik yapmak istiyorsak, onu yeniden tanımlamalıyız.


```python
demet = ('a', 'b')
demet = demet + ('c',)
```


```python
demet
```




    ('a', 'b', 'c')



## Demetlerin Kullanım Alanları

Bu veri tipi özellikle programların ayar (conf) dosyalarında bu veri tipi sıklıkla kullanılır. Örneğin Python tabanlı bir web çatısı (framework ) olan Django’nun settings.py adlı ayar dosyasında pek çok değer bir demet olarak saklanır. Mesela bir Django projesinde web sayfalarının şablonlarını (template) hangi dizin altında saklayacağınızı belirlediğiniz ayar şöyle görünür:


```python
TEMPLATE_DIRS = ('/home/projects/djprojects/blog/templates',)
```

Burada, şablon dosyalarının hangi dizinde yer alacağını bir demet içinde gösteriyoruz. Bu demet içine birden fazla dizin adı yazabilirdik. Ama biz bütün şablon dosyalarını tek bir dizin altında tutmayı tercih ettiğimiz için tek öğeli bir demet tanımlamışız. Bu arada, daha önce de söylediğimiz gibi, demetlerle ilgili en sık yapacağınız hata, tek öğeli demet tanımlamaya çalışırken aslında yanlışlıkla bir karakter dizisi tanımlamak olacaktır. Örneğin yukarıdaki TEMPLATE_DIRS değişkenini şöyle yazsaydık:


```python
TEMPLATE_DIRS = ('/home/projects/djprojects/blog/templates')
```

Aslında bir demet değil, alelade bir karakter dizisi tanımlamış olurduk...

> Son Güncelleme: 20 Aralaık 2019 - Cuma
