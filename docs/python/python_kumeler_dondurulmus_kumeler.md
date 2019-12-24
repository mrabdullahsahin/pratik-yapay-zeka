# Kümeler ve Dondurulmuş Kümeler

Bu bölümde kümeler dışında, bir de dondurulmuş kümelerden söz edeceğiz. Bu iki veri tipi birbiriyle ilişkilidir.

## Kümeler

Adından da az çok tahmin edebileceğiniz gibi kümeler, matematikten bildiğimiz “küme” kavramıyla sıkı sıkıya bağlantılıdır. Bu veri tipi, matematikteki kümelerin sahip olduğu bütün özellikleri taşır. Yani matematikteki kümelerden bildiğimiz kesişim, birleşim ve fark gibi özellikler Python’daki kümeler için de geçerlidir.

### Küme Oluşturmak

Küme oluşturmak çok kolay bir işlemdir. Örneğin boş bir kümeyi şöyle oluşturuyoruz:


```python
bos_kume = set()
```

Listeler, demetler ve sözlüklerin aksine kümelerin ayırt edici bir işareti yoktur. Küme oluşturmak için set() adlı özel bir fonksiyondan yararlanıyoruz.


```python
type(bos_kume)
```




    set



Gördüğünüz gibi, Python programlama dilinde kümeler set ifadesiyle gösteriliyor.

İçinde öğe de barındıran kümeleri ise şu şekilde oluşturuyoruz:


```python
kume = set(["elma", "armut", "kebap"])
```

Gördüğünüz gibi set() fonksiyonu içindeki öğeler bir liste içinde yer alıyor. Dolayısıyla yukarıdaki tanımlamayı şöyle de yapabiliriz:


```python
liste = ["elma", "armut", "kebap"]

kume = set(liste)
```

Elbette küme tanımlamak için mutlaka liste kullanmak zorunda değiliz. İstersek demetleri de küme haline getirebiliriz:


```python
demet = ("elma", "armut", "kebap")

kume = set(demet)
```

Hatta ve hatta karakter dizilerinden dahi küme yapabiliriz:


```python
kardiz = "Python Programlama Dili için Türkçe Kaynak" 

kume = set(kardiz)
```

Kullandığımız karakter dizisinin böyle uzun olmasına da gerek yok. Tek karakterlik dizilerden bile küme oluşturabiliriz:


```python
kardiz = "a"

kume = set(kardiz)
```

Ama sayılardan küme oluşturamayız:


```python
n = 10

kume = set(n)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-8-ffda9229f4d1> in <module>
          1 n = 10
          2 
    ----> 3 kume = set(n)
    

    TypeError: 'int' object is not iterable


Peki sözlükleri kullanarak küme oluşturabilir miyiz? Elbette, neden olmasın?


```python
bilgi = {"işletim sistemi": "GNU", 
         "sistem çekirdeği": "Linux",
         "dağıtım": "Ubuntu GNU/Linux"}

kume = set(bilgi)
```

Küme oluşturmanın son bir yönteminden daha söz edelim. En başta söylediğimiz gibi, listeler, demetler, sözlükler ve karakter dizilerinin aksine kümelerin [ ], ( ), { }, ‘ ‘ gibi ayırt edici bir işareti yoktur. Ama eğer istersek sözlükleri oluşturmak için kullandığımız özel işaretleri küme oluşturmak için de kullanabiliriz. 


```python
kume = {'Python', 'C++', 'Ruby', 'PHP'}

type(kume)
```




    set



Ancak bu yapıyı kullanarak boş bir küme oluşturamazsınız:


```python
kume = {}

type(kume)
```




    dict



Boş bir küme oluşturmak için set() fonksiyonunu kullanmanız gerekmektedir:


```python
kume = set(kume)

type(kume)
```




    set



Eğer oluşturduğunuz kümeyi ekrana yazdırmak isterseniz:


```python
kume
```




    {'C++', 'PHP', 'Python', 'Ruby'}



Bu arada, bir sözlüğü kümeye çevirdiğinizde, elbette sözlüğün yalnızca anahtarları kümeye eklenecektir. Sözlüğün değerleri ise böyle bir işlemin sonucunda ortadan kaybolur.

Eğer bir sözlüğü kümeye çevirirken hem anahtarları hem de değerleri korumak gibi bir niyetiniz varsa şöyle bir şey yazabilirsiniz:


```python
bilgi = {"işletim sistemi": "GNU", 
         "sistem çekirdeği": "Linux", 
         "dağıtım": "Ubuntu GNU/Linux"}
```

Bu sözlükteki anahtar-değer çiftlerini bir küme içine, çift öğeli demetler olarak yerleştirebiliriz:


```python
liste = [(anahtar, değer) for anahtar, değer in bilgi.items()] 

kume = set(liste)

kume
```




    {('dağıtım', 'Ubuntu GNU/Linux'),
     ('işletim sistemi', 'GNU'),
     ('sistem çekirdeği', 'Linux')}



### Kümelerin Yapısı

Örneğin şöyle bir küme tanımlayalım:


```python
kardiz = "Python Programlama Dili"

kume = set(kardiz)

print(kume)
```

    {'t', 'a', 'o', 'm', 'h', 'D', 'r', ' ', 'g', 'n', 'l', 'y', 'i', 'P'}


Burada bir şey dikkatinizi çekmiş olmalı. Bir öğeyi küme olarak tanımlayıp ekrana yazdırdığımızda elde ettiğimiz çıktı, o öğe içindeki her bir alt öğeyi tek bir kez içeriyor. Yani mesela “Python Programlama Dili” içinde iki adet “P” karakteri var, ama çıktıda bu iki “P” karakterinin yalnızca biri görünüyor. Buradan anlıyoruz ki, kümeler aynı öğeyi birden fazla tekrar etmez. Bu çok önemli bir özelliktir ve pek çok yerde işimize yarar. Aynı durum karakter dizisi dışında kalan öteki veri tipleri için de geçerlidir. Yani mesela eğer bir listeyi küme haline getiriyorsak, o listedeki öğeler küme içinde yalnızca bir kez geçecektir. Listede aynı öğeden iki-üç tane bulunsa bile, kümemiz bu öğeleri teke indirecektir.

### Küme Üreteçleri (SetComprehensions)

Liste üreteçlerini ve sözlük üreteçlerini kullanarak nasıl tek satırda ve hızlı bir şekilde listeler ve sözlükler üretebiliyorsak, aynı şekilde küme üreteçlerini kullanarak tek satırda ve hızlı bir şekilde kümeler de üretebiliriz.


```python
import random

liste = [random.randint(0, 10000) for i in range(1000)]
```


```python
kume = {i for i in liste if i < 100} 

print(kume)
```

    {64, 97, 3, 36, 42, 43, 44, 16, 61}


Gördüğünüz gibi, küme üreteçlerinin sözdizimi, liste ve sözlük üreteçlerinin sözdizimine çok benziyor.

### Kümelerin Metotları

Kümeler ile kullanılabilen metotlara bakalım:


```python
dir(set)
```




    ['__and__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__iand__',
     '__init__',
     '__init_subclass__',
     '__ior__',
     '__isub__',
     '__iter__',
     '__ixor__',
     '__le__',
     '__len__',
     '__lt__',
     '__ne__',
     '__new__',
     '__or__',
     '__rand__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__ror__',
     '__rsub__',
     '__rxor__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__sub__',
     '__subclasshook__',
     '__xor__',
     'add',
     'clear',
     'copy',
     'difference',
     'difference_update',
     'discard',
     'intersection',
     'intersection_update',
     'isdisjoint',
     'issubset',
     'issuperset',
     'pop',
     'remove',
     'symmetric_difference',
     'symmetric_difference_update',
     'union',
     'update']



Hemen işimize yarayacak metotları alalım:


```python
for i in dir(set):
    if "__" not in i: 
        print(i)
```

    add
    clear
    copy
    difference
    difference_update
    discard
    intersection
    intersection_update
    isdisjoint
    issubset
    issuperset
    pop
    remove
    symmetric_difference
    symmetric_difference_update
    union
    update


#### clear()

Kümelerle ilgili olarak inceleyeceğimiz ilk metot clear(). Bu metodu daha önce sözlükleri çalışırken de görmüştük. Sözlüklerde bu metodun görevi sözlüğün içini boşaltmak idi. Burada da aynı vazifeyi görür:


```python
km = set("ankara")

for i in km:
    print(i)
```

    k
    a
    r
    n



```python
km.clear()

km
```




    set()



Burada önce “km” adlı bir küme oluşturduk. Daha sonra da clear() metodunu kullanarak bu kümenin bütün öğelerini sildik. Artık elimizde boş bir küme var.

#### copy()

Listeler ve sözlükleri incelerken copy() adlı bir metot öğrenmiştik. Bu metot aynı zamanda kümelerle birlikte de kullanılabilir. Üstelik işlevi de aynıdır:


```python
km = set("kahramanmaraş")

yedek = km.copy()

yedek
```




    {'a', 'h', 'k', 'm', 'n', 'r', 'ş'}



#### add()

Add kelimesi Türkçe’de “eklemek” anlamına gelir. Adından da anlaşılacağı gibi, bu metot yardımıyla kümelerimize yeni öğeler ilave edebileceğiz. Hemen bunun nasıl kullanıldığına bakalım:


```python
kume = set(["elma", "armut", "kebap"]) 

kume.add("çilek")

print(kume)
```

    {'elma', 'çilek', 'armut', 'kebap'}


Gördüğünüz gibi, add() metodunu kullanarak, kümemize çilek adlı yeni bir öğe ekledik. Eğer kümede zaten varolan bir öğe eklemeye çalışırsak kümede herhangi bir değişiklik olmayacaktır. Çünkü, daha önce de söylediğimiz gibi, kümeler her bir öğeyi tek bir sayıda barındırır.

Bu arada, yeri gelmişken kümelerin önemli bir özelliğinden daha söz edelim. Bir kümeye herhangi bir öğe ekleyebilmemiz için, o öğenin değiştirilemeyen (immutable) bir veri tipi olması gerekiyor. 

Bildiğiniz gibi Python’daki şu veri tipleri değiştirilemeyen veri tipleridir:

1. Demetler
2. Sayılar
3. Karakter Dizileri

Şu veri tipleri ise değiştirilebilen veri tipleridir: 

1. Listeler
2. Sözlükler
3. Kümeler

Dolayısıyla bir kümeye ancak şu veri tiplerini ekleyebiliriz:

1. Demetler
2. Sayılar
3. Karakter Dizileri

#### difference()

Bu metot iki kümenin farkını almamızı sağlar. Örneğin:


```python
k1 = set([1, 2, 3, 5])
k2 = set([3, 4, 2, 10])

k1.difference(k2)
```




    {1, 5}



Demek ki k1’in k2’den farkı buymuş. Peki k2’nin k1’den farkını bulmak istersek ne yapacağız?


```python
k2.difference(k1)
```




    {4, 10}



İsterseniz uzun uzun difference() metodunu kullanmak yerine sadece eksi (-) işaretini kullanarak da aynı sonucu elde edebilirsiniz:


```python
k1 - k2
```




    {1, 5}



...veya...


```python
k2 - k1
```




    {4, 10}



Hayır, “madem eksi işaretini kullanabiliyoruz, o halde artı işaretini de kullanabiliriz! ” gibi bir
fikir doğru değildir.

#### difference_update()

Bu metot, difference() metodundan elde edilen sonuca göre bir kümenin güncellenmesini sağlar. Yani? Hemen bir örnek verelim:


```python
k1 = set([1, 2, 3])
k2 = set([1, 3, 5])
k1.difference_update(k2)

print(k1)
```

    {2}


Gördüğünüz gibi, bu metot k1’in k2’den farkını aldı ve bu farkı kullanarak k1’i yeniden oluşturdu. k1 ile k2 arasındaki tek fark 2 adlı öğe idi. Dolayısıyla difference_update() metodunu uyguladığımızda k1’in öğelerinin silinip yerlerine 2 adlı öğenin geldiğini görüyoruz.

#### discard()

Bu metot kümeden öğe silmemizi sağlayacak:


```python
hayvanlar = set(["kedi", "köpek", "at", "kuş", "inek", "deve"])
hayvanlar.discard("kedi")

print(hayvanlar)
```

    {'inek', 'deve', 'kuş', 'at', 'köpek'}


Eğer küme içinde bulunmayan bir öğe silmeye çalışırsak hiç bir şey olmaz. Yani hata mesajı almayız:


```python
hayvanlar.discard("yılan")
```

Burada etkileşimli kabuk sessizce bir alt satıra geçecektir. Bu metodun en önemli özelliği
budur. Yani olmayan bir öğeyi silmeye çalıştığımızda hata vermemesi.

#### remove()

Eğer bir kümeden öğe silmek istersek remove() metodunu da kullanabiliriz:


```python
hayvanlar.remove("köpek")
```

Peki discard() varken remove() metoduna ne gerek var? Ya da tersi.

Bu iki metot aynı işlevi yerine getirse de aralarında önemli bir fark vardır. Hatırlarsanız discard() metoduyla, kümede olmayan bir öğeyi silmeye çalışırsak herhangi bir hata mesajı almayacağımızı söylemiştik. Eğer remove() metodunu kullanarak, kümede olmayan bir öğeyi silmeye çalışırsak, discard() metodunun aksine, hata mesajı alırız:


```python
hayvanlar.remove("fare")
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-45-65ebbfa6250f> in <module>
    ----> 1 hayvanlar.remove("fare")
    

    KeyError: 'fare'


#### intersection()

intersection kelimesi Türkçe’de “kesişim” anlamına gelir. Adından da anladığımız gibi, intersection() metodu bize iki kümenin kesişim kümesini verecektir:


```python
k1 = set([1, 2, 3, 4])
k2 = set([1, 3, 5, 7])

k1.intersection(k2)
```




    {1, 3}



İki kümenin kesişimini bulmak için “&” işaretinden yararlanabiliriz:


```python
k1 & k2
```




    {1, 3}



#### intersection_update()

Bu metodun görevi, intersection() metodundan elde edilen sonuca göre bir kümenin güncellenmesini sağlamaktır:


```python
k1 = set([1, 2, 3])
k2 = set([1, 3, 5])
k1.intersection_update(k2)

print(k1)
```

    {1, 3}



```python
print(k2)
```

    {1, 3, 5}


Gördüğünüz gibi, intersection_update() metodu k1’in bütün öğelerini sildi ve yerlerine k1 ve k2’nin kesişim kümesinin elemanlarını koydu.

#### isdisjoint()

Bu metodun çok basit bir görevi vardır. isdisjoint() metodunu kullanarak iki kümenin kesişim kümesinin boş olup olmadığı sorgulayabilirsiniz. 


```python
a = set([1, 2, 3])
b = set([2, 4, 6])

a.isdisjoint(b)
```




    False



#### issubset()

Bu metot yardımıyla, bir kümenin bütün elemanlarının başka bir küme içinde yer alıp yer almadığını sorgulayabiliriz. Yani bir kümenin, başka bir kümenin alt kümesi olup olmadığını bu metot yardımıyla öğrenebiliriz. Eğer bir küme başka bir kümenin alt kümesi ise bu metot bize True değerini verecek; eğer değilse False çıktısını verecektir:


```python
a = set([1, 2, 3])
b = set([0, 1, 2, 3, 4, 5])

a.issubset(b)
```




    True



Bu örnekte True çıktısını aldık, çünkü a kümesinin bütün öğeleri b kümesi içinde yer alıyor. Yani a, b‘nin alt kümesidir.

#### issuperset()

Matematik derslerinde gördüğümüz “kümeler” konusunda hatırladığınız “b kümesi a kümesini kapsar” ifadesini bu metotla gösteriyoruz.


```python
a = set([1, 2, 3])
b = set([0, 1, 2, 3, 4, 5])

b.issuperset(a)
```




    True



Burada, “b kümesi a kümesini kapsar,” sonucunu elde ediyoruz. Yani b kümesi a kümesinin bütün elemanlarını içinde barındırıyor.

#### union()

union() metodu iki kümenin birleşimini almamızı sağlar. Hemen bir örnek verelim:


```python
a = set([2, 4, 6, 8])
b = set([1, 3, 5, 7])

a.union(b)
```




    {1, 2, 3, 4, 5, 6, 7, 8}



union() metodu yerine “|” işaretini de kullanabiliriz:


```python
a | b
```




    {1, 2, 3, 4, 5, 6, 7, 8}



#### update()

Bu metot, bir kümeyi güncellememizi sağlar.


```python
kume = set(["elma", "armut", "kebap"])

yeni = [1, 2, 3]

kume.update(yeni)

print(kume)
```

    {1, 2, 3, 'armut', 'kebap', 'elma'}


#### symmetric_difference()

Kümelerin ikisinde de bulunmayan öğeleri aynı anda almamızı sağlar.


```python
a = set([1, 2, 5])
b = set([1, 4, 5])

a.symmetric_difference(b)
```




    {2, 4}



#### symmetric_difference_update()

Daha önce difference_update ve intersection_update gibi metotları öğrenmiştik. symmetric_difference_update() metodu da bunlara benzer bir işlevi yerine getirir:


```python
a = set([1,2, 5])
b = set([1,4, 5])

a.symmetric_difference_update(b)

print(a)
```

    {2, 4}


Gördüğünüz gibi, a kümesinin eski öğeleri gitti, yerlerine symmetric_difference() metoduyla elde edilen çıktı geldi. Yani a kümesi, symmetric_difference() metodunun sonucuna göre güncellenmiş oldu...

#### pop()

Kümelerin öğelerini silip ekrana basıyor:


```python
a = set(["elma", "armut", "kebap"])

a.pop()
```




    'elma'



Peki bu metot hangi ölçüte göre kümeden öğe siliyor? Herhangi bir ölçüt yok. Bu metot, küme öğelerini tamamen rastgele siliyor.

## Dondurulmuş Kümeler (Frozenset)

Öğeleri üzerinde değişiklik yapılamayan bir küme oluşturmak isterseniz set() yerine frozenset() fonksiyonunu kullanabilirsiniz. Dilerseniz hemen bununla ilgili bir örnek verelim:


```python
dondurulmus = frozenset(["elma", "armut", "ayva"])
```

Dondurulmuş kümeleri bu şekilde oluşturuyoruz. Şimdi bu dondurulmuş kümenin metotlarına bakalım:


```python
dir(dondurulmus)
```




    ['__and__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__ne__',
     '__new__',
     '__or__',
     '__rand__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__ror__',
     '__rsub__',
     '__rxor__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__sub__',
     '__subclasshook__',
     '__xor__',
     'copy',
     'difference',
     'intersection',
     'isdisjoint',
     'issubset',
     'issuperset',
     'symmetric_difference',
     'union']



Gördüğünüz gibi, add(), remove(), update() gibi, değişiklik yapmaya yönelik metotlar listede yok.

Dondurulmuş kümeler ile normal kümeler arasında işlev olarak hiçbir fark yoktur. Bu ikisi arasındaki fark, listeler ile demetler arasındaki fark gibidir.

> Son Güncelleme: 24 Aralık 2019 - Salı
