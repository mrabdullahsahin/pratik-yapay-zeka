# Karakter Dizileri

## Karakter Dizilerinin Öğelerine Erişmek

Karakter dizileri çok sık kullanacağımız yapılardır. Önceki bölümlerde karakter dizileri üzerinde işlemler yapmıştık. Bu bölümde daha ayrıntılı olarak inceleyeceğiz.

Karakter dizilerine birkaç farklı yol ile erişebiliriz. Örneğin:


```python
karakter = "karakter"

print(karakter)
```

    karakter


Yukarıda görüldüğü gibi karakter isimli değişkene print fonksiyonu ile erişmiş olduk ve içerisinde bulunan değerin tamamını ekrana yazdırdık.

Bir başka yol olarakta kullanıcıdan alabiliriz değeri.


```python
karakter = input("Bir kelime giriniz: ")

print(karakter)
```

    Bir kelime giriniz: kelime
    kelime


Aynı zamanda for döngüsü ile karakter dizisinin bütün değerlerine tek tek erişebiliriz. Örneğin:


```python
for deger in karakter:
    print(deger)
```

    k
    e
    l
    i
    m
    e


Yukarıdaki işlemi print fonsiyonu ile de yapabiliriz.


```python
print(*karakter, sep="\n")
```

    k
    e
    l
    i
    m
    e


Aynı zamanda karakter dizine şu şekildede erişebiliriz. nesne[öge_sırası], örnek ile inceleyelim bu durumu:


```python
karakter[0]
```




    'k'



Gördüğünüz gibi karakter nesnesinin ilk elemanına erişmek için sıfır yazdım yani burada başlangıç her daim sıfır olmaktadır. Eğer bir yazmış olsaydım ikinci karaktere ulaşmış olurdum.


```python
karakter[1]
```




    'e'



Peki büyük bir rakam yazarsam ne ile karşılaşırım, hemen bakalım:


```python
karakter[10]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-7-ad38375bdd41> in <module>
    ----> 1 karakter[10]
    

    IndexError: string index out of range


Görmüş olduğunuz gibi karakter değişkeninin uzunluğunun dışına çıkmış oldum. Yukarıda verilen hata **string index out of range** bir nesnenin var olan uzunluğunun dışına çıkıldığı zaman oluşmaktadır. Peki karakter değişkenimizin uzunluğunu nasıl öğrenebiliriz. Bunun daha önce öğrendiğimiz len() fonksiyonu ile yapabiliriz.


```python
len(karakter)
```




    6



karakter değişkenimizin içinde **kelime** yazmaktadır. Bu değerin uzunluğu altıdır. Fakat biz altıncı karaktere erişmeye çalıştığımız zaman hata ile karşılacağız:


```python
karakter[6]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-9-3c6610cc998a> in <module>
    ----> 1 karakter[6]
    

    IndexError: string index out of range


Görmüş olduğunuz gibi altıncı karaktere erişmek istediğimiz zaman hata verdi çünkü karakter dizilerine erişirken sıfır ile başlarız. Normalde saymaya birden başlarız ama burada saymaya sıfırdan başlıyoruz. Bu farkı her daim hatırlayalım.


```python
karakter[5]
```




    'e'



karakter isimli değişkenimizin elemanlarına tek tek erişelim.


```python
karakter[0]
```




    'k'




```python
karakter[1]
```




    'e'




```python
karakter[2]
```




    'l'




```python
karakter[3]
```




    'i'




```python
karakter[4]
```




    'm'




```python
karakter[5]
```




    'e'



Yukarıda belirttiğimiz **öğe_sırası** yazan yere eksi değerli bir değerde girebiliriz. Eğer -1 değerini girersek bize değişkenimizin en sonda bulunan değerini getirecektir. Eğer -2 değerini girersek sondan bir önceki değeri getirecektir.


```python
karakter[-1]
```




    'e'




```python
karakter[-2]
```




    'm'




```python
karakter[-3]
```




    'i'



Bu şekilde eksi değerlerde girebiliriz.

Peki for döngüsünü ve bu yapıyı kullanarak erişebilir miyiz? Tabiki de, hemen bir örnek ile bakalım:


```python
for deger in range(len(karakter)):
    print(karakter[deger])
```

    k
    e
    l
    i
    m
    e


Farklı bir şekilde ekranda gösterelim:


```python
for i in range(len(karakter)):
    print("Değişkenimizin {}. harfi: {}".format(i, karakter[i]))
```

    Değişkenimizin 0. harfi: k
    Değişkenimizin 1. harfi: e
    Değişkenimizin 2. harfi: l
    Değişkenimizin 3. harfi: i
    Değişkenimizin 4. harfi: m
    Değişkenimizin 5. harfi: e


## Karakter Dizilerini Dilimlemek

Karakter dizilerine parça parçada erişebiliriz yani onları meyve dilimler gibi dilimleyebiliriz. Hemen bir örnek üzerinden inceleyelim:


```python
karakter_dizisi = "Bu bir karakter dizisidir."

karakter_dizisi[0:2]
```




    'Bu'



Yukarıdaki örnekte karakter_dizisi değişkenimizin sadece ilk iki değerini getirdik.


```python
karakter_dizisi[2:7]
```




    ' bir '



Peki burada da eksi değerli değerler kullanabilir miyiz? Tabiki de, hemen bir örnek ile inceleyelim:


```python
karakter_dizisi[-4:]
```




    'dir.'



Burada nasıl bir yöntem izleyiyoruz. Nesnelere bu şekilde erişebiliyoruz: **karakter_dizisi[alınacak_ilk_öğenin_sırası:alınacak_son_öğenin_sırasının_bir_fazlası]**. Eğer istersek ilk nesneyi yazmadığımız zaman baştan başlayıp bizim belirlediğimiz değere kadar erişir.


```python
karakter_dizisi[:4]
```




    'Bu b'



Yukarıda yazdığımız kod ile aynı işe yapan kod ise:


```python
karakter_dizisi[0:4]
```




    'Bu b'



## Karakter Dizilerini Ters Çevirmek

Bir değişkenin barındırdığı karakter dizisini ters çevirmek istediğimiz zaman şunu yapmamız gerekmektedir:


```python
karakter_dizisi[::-1]
```




    '.ridisizid retkarak rib uB'



Peki sadece belirli aralıklarla ilerlemek istediğimiz zaman ne yapmalıyız?


```python
karakter_dizisi[0:7:2]
```




    'B i '



karakter_dizisi[ilk_karakter:son_karakter:atlama_sayısı]. Burada atlama sayısı yazan yere kaç adet karakter atlaya atlaya ilerlemek istiyorsanız onu yazmalısınız.

Karakter dizisini ters çevirmek için kullanabileceğimiz daha pratik bir fonksiyon mevcut o da, reversed(). Hemen bir örnek ile inceyelim:


```python
reversed(karakter_dizisi)
```




    <reversed at 0x11200d290>



reversed fonksiyonunu tek başına kullandığımız zaman bizlere bu şekilde bir değer döndürüyor. Bu fonksiyonu for döngüsü veya print fonksiyonu ile kullanmamız gerekmektedir.


```python
for i in reversed(karakter_dizisi): 
    print(i, end="")
```

    .ridisizid retkarak rib uB


```python
print(*reversed(karakter_dizisi), sep="")
```

    .ridisizid retkarak rib uB


## Karakter Dizilerini Alfabe Sırasına Dizmek

Python'da sorted() fonksiyonu ile karakter dizisini alfabetik sıraya göre dizmek mümkün.


```python
karakter_dizisi = "zebra"
sorted(karakter_dizisi)
```




    ['a', 'b', 'e', 'r', 'z']



Yukarıda aldığımız çıktıyı iki farklı yollada alabiliriz.

1. Yol


```python
print(*sorted(karakter_dizisi), sep="")
```

    aberz


2. Yol


```python
for i in sorted(karakter_dizisi): 
    print(i, end="")
```

    aberz

Sorted() fonksiyonu Türkçe karakterlerde doğru bir şekilde çalışmamaktadır. Bu durumu çözmek mümkün lakin "i" harfi için elimizle düzeltmemiz gerekmektedir çünkü ı ve i harflerini birbirinden ayıramamaktadır. Bu duruma dikkat etmekte fayda var.

## Karakter Dizileri Üzerinde Değişiklik Yapmak

Bu kısımda karakter dizilerinde istediğimiz adet karakteri değiştirmekten tutunda, baş harfi büyütmeye kadar farklı konuları inceleyeceğiz.


```python
karakter_dizisi = "elma"
```

Elimizde bulunan karakter_dizisi değişkenin baş harfini büyütmek istiyoruz diyelim:


```python
karakter_dizisi = "E" + karakter_dizisi[1:]
```


```python
print(karakter_dizisi)
```

    Elma


Peki karakter_dizisi içerisinden istediğimiz kısmı çıkarıp yerine başka bir kelime ekleyelim.


```python
karakter_dizisi = karakter_dizisi[0:2] + "kart"
print(karakter_dizisi)
```

    Elkart


## Üç Önemli Fonksiyon

Python'da işlerimizi kolaylaştıran veya unuttuğumuz bilgileri hatırlamamızı sağlayan bazı fonksiyonlar şimdi bunları öğrenelim.

### dir()

Bu fonksiyon bizlere Python'da bulunan nesneler hakkında bilgi vermektedir. Bu fonksiyon aracılığı ile karakter dizileri(str) hakkında bilgi alalım.


```python
dir(str)
```




    ['__add__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getitem__',
     '__getnewargs__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__mod__',
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__rmod__',
     '__rmul__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'capitalize',
     'casefold',
     'center',
     'count',
     'encode',
     'endswith',
     'expandtabs',
     'find',
     'format',
     'format_map',
     'index',
     'isalnum',
     'isalpha',
     'isascii',
     'isdecimal',
     'isdigit',
     'isidentifier',
     'islower',
     'isnumeric',
     'isprintable',
     'isspace',
     'istitle',
     'isupper',
     'join',
     'ljust',
     'lower',
     'lstrip',
     'maketrans',
     'partition',
     'replace',
     'rfind',
     'rindex',
     'rjust',
     'rpartition',
     'rsplit',
     'rstrip',
     'split',
     'splitlines',
     'startswith',
     'strip',
     'swapcase',
     'title',
     'translate',
     'upper',
     'zfill']



dir() fonksiyonu karakter dizileri ile beraber kullanabileceğimiz fonksiyonları bizlere göstermektedir. Aynı şekilde int türündekiler içinde bakabiliriz. 


```python
dir(int)
```




    ['__abs__',
     '__add__',
     '__and__',
     '__bool__',
     '__ceil__',
     '__class__',
     '__delattr__',
     '__dir__',
     '__divmod__',
     '__doc__',
     '__eq__',
     '__float__',
     '__floor__',
     '__floordiv__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getnewargs__',
     '__gt__',
     '__hash__',
     '__index__',
     '__init__',
     '__init_subclass__',
     '__int__',
     '__invert__',
     '__le__',
     '__lshift__',
     '__lt__',
     '__mod__',
     '__mul__',
     '__ne__',
     '__neg__',
     '__new__',
     '__or__',
     '__pos__',
     '__pow__',
     '__radd__',
     '__rand__',
     '__rdivmod__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__rfloordiv__',
     '__rlshift__',
     '__rmod__',
     '__rmul__',
     '__ror__',
     '__round__',
     '__rpow__',
     '__rrshift__',
     '__rshift__',
     '__rsub__',
     '__rtruediv__',
     '__rxor__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__sub__',
     '__subclasshook__',
     '__truediv__',
     '__trunc__',
     '__xor__',
     'bit_length',
     'conjugate',
     'denominator',
     'from_bytes',
     'imag',
     'numerator',
     'real',
     'to_bytes']



dir() ile kullanacağınız bir yapının ne tür yapılarla beraber kullanılabildiğini öğrenebilirsiniz.

### enumerate()

Enumerate ingilizcede "numaralamak, numaralandırmak" olarak geçmektedir. Yani bir karakter dizisinin değerlerini numaralandırmamıza yaramaktadır.


```python
print(*enumerate(karakter_dizisi))
```

    (0, 'E') (1, 'l') (2, 'k') (3, 'a') (4, 'r') (5, 't')


Bir değişkenin içerisinde barındırdığı değerleri tek tek numaralandırabilmemizi sağlıyor. Eğer böyle bir ihtiyacınız olursa bu fonksiyon işinizi hızlı bir şekilde yapabilmenizi sağlar. 

### help()

Herhangi bir fonksiyon, metot veya nesne hakkında interneti kullanmadan hızlı bir şekilde ingilizce olarak bilgi almak isterseniz bu fonksiyon işinizi görecektir. Örneğin:


```python
help(len)
```

    Help on built-in function len in module builtins:
    
    len(obj, /)
        Return the number of items in a container.
    


Görmüş olduğunuz gibi help fonksiyonu bizlere len fonksiyonunun ne olduğunu ve nasıl kullanılabildiğini göstermektedir.

> Son Güncelleme: 18 Aralık 2019 - Çarşamba
