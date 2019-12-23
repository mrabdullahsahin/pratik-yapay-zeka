## Listelerin Metotları

Listelerin barındırdığı metotları dir() fonksiyonu aracılığı ile listeleyelim:


```python
dir(list)
```




    ['__add__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__delitem__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getitem__',
     '__gt__',
     '__hash__',
     '__iadd__',
     '__imul__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__reversed__',
     '__rmul__',
     '__setattr__',
     '__setitem__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'append',
     'clear',
     'copy',
     'count',
     'extend',
     'index',
     'insert',
     'pop',
     'remove',
     'reverse',
     'sort']



### append()

append kelimesi İngilizcede ‘eklemek, ilave etmek, iliştirmek’ gibi anlamlara gelir. Bu metodu, bir listeye öğe eklemek için kullanıyoruz. Listeye yeni öğe eklemek için iki farklı yol kullanabiliriz.

1. Yol


```python
liste = ["elma", "armut", "çilek"] 
liste.append("kiraz")
print(liste)
```




    ['elma', 'armut', 'çilek', 'kiraz']



2. Yol


```python
liste = ["elma", "armut", "çilek"] 
liste = liste + ["kiraz"]
print(liste)
```




    ['elma', 'armut', 'çilek', 'kiraz']



append() metodunu kullanarak bir listeye birden fazla öğe ekleyemezsiniz:


```python
liste = [1, 2, 3]
liste.append(4, 5, 6)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-6-e4d572564cdb> in <module>
          1 liste = [1, 2, 3]
    ----> 2 liste.append(4, 5, 6)
    

    TypeError: append() takes exactly one argument (3 given)


Bu sebeple, ekleyeceğiniz listenin öğeleri üzerinde bir for döngüsü kurmanız gerekir:


```python
liste = [1, 2, 3] 

for i in [4, 5, 6]: 
    liste.append(i)
    
print(liste)
```

    [1, 2, 3, 4, 5, 6]


### extend()

extend kelimesi İngilizcede ‘genişletmek, yaymak’ gibi anlamlara gelir. İşte extend() adlı metot da kelime anlamına uygun olarak listeleri ‘genişletir’.


```python
liste1 = [1, 3, 4] 
liste2 = [10, 11, 12] 
liste1. extend(liste2)

print(liste1)
```

    [1, 3, 4, 10, 11, 12]


### insert()

insert kelimesi ‘yerleştirmek, sokmak’ gibi anlamlara gelir. insert() metodu da bu anlama uygun olarak, öğeleri listenin istediğimiz bir konumuna yerleştirir.


```python
liste = ["elma", "armut", "çilek"]
liste.insert(0, "kiraz")

print(liste)
```

    ['kiraz', 'elma', 'armut', 'çilek']


Gördüğünüz gibi insert() metodu iki parametre alıyor. **İlk parametre**, öğenin hangi konuma yerleştirileceğini, **ikinci parametre** ise yerleştirilecek öğenin ne olduğunu gösteriyor. Yukarıdaki örnekte “kiraz” öğesini listenin 0. konumuna, yani listenin en başına yerleştiriyoruz.

### remove()

Bu metot listeden öğe silmemizi sağlar. Örneğin:


```python
liste = ["elma", "armut", "çilek"]

liste.remove("elma")

liste
```




    ['armut', 'çilek']



### reverse()

Bu metot listelerin öğelerini ters çevirebilmemizi sağlar. Örneğin:


```python
liste = ["elma", "armut", "çilek"]

liste.reverse()

liste
```




    ['çilek', 'armut', 'elma']



### pop()

Tıpkı remove() metodu gibi, bu metot da bir listeden öğe silmemizi sağlar:


```python
liste = ["elma", "armut", "çilek"]

liste.pop()
```




    'çilek'



Ancak bu metot, remove() metodundan biraz farklı davranır. pop() metodunu kullanarak bir liste öğesini sildiğimizde, silinen öğe ekrana basılacaktır. Bu metot parametresiz olarak kullanıldığında listenin son öğesini listeden atar. Alternatif olarak, bu metodu bir parametre ile birlikte de kullanabilirsiniz. Örneğin:


```python
liste.pop(0)
```




    'elma'



Bu komut listenin 0. öğesini listeden atar ve atılan öğeyi ekrana basar.

### sort()

Diyelim ki elimizde şöyle bir liste mevcut:


```python
kisiler = ['Ahmet', 'Mehmet', 'Ceylan', 'Seyhan', 'Mahmut', 'Zeynep', 'Abdullah', 'Kadir', 'Kamil', 'Selin', 'Senem', 'Sinem', 'Tayfun', 'Tuna', 'Tolga']
```

Bu listedeki isimleri mesela alfabe sırasına dizmek için sort() metodunu kullanabiliriz:


```python
kisiler.sort()
kisiler
```




    ['Abdullah',
     'Ahmet',
     'Ceylan',
     'Kadir',
     'Kamil',
     'Mahmut',
     'Mehmet',
     'Selin',
     'Senem',
     'Seyhan',
     'Sinem',
     'Tayfun',
     'Tolga',
     'Tuna',
     'Zeynep']



Bu metot elbette yalnızca harfleri alfabe sırasına dizmek için değil sayıları sıralamak için de kullanılabilir:


```python
sayilar = [1, 0, -1, 4, 10, 3, 6]
sayilar.sort()

sayilar
```




    [-1, 0, 1, 3, 4, 6, 10]



Listelerin sort() metodu Türkçe karakterleri düzgün sıralayamaz. Eğer Türkçe karakterleri sıralamamız gereken bir program yazıyorsak bizim sort() metodunun işleyişine müdahale etmemiz gerekir. Bu durumu hatırlamakta fayda var.

### index()

Bu metot bir liste öğesinin liste içindeki konumunu söyler bize:


```python
liste = ["elma", "armut", "çilek"] 
liste.index("çilek")
```




    2



### count()

Bu metot bir öğenin o veri tipi içinde kaç kez geçtiğini söyler:


```python
liste = ["elma", "armut", "elma", "çilek"] 

liste.count("elma")
```




    2



### copy()

Bu metot bir listeyi kopyalayabilmemizi sağlar:


```python
liste1 = ["ahmet", "mehmet", "özlem"]
liste2 = liste1.copy()
liste2
```




    ['ahmet', 'mehmet', 'özlem']



### clear()

Bu metodun görevi bir listenin içeriğini silmektir.

Diyelim ki elimizde şöyle bir liste var:


```python
liste = [1, 2, 3, 5, 10, 20, 30, 45]
```

Bu listenin içini boşaltmak için clear() metodunu kullanabiliriz:


```python
liste.clear()

liste
```




    []



Bu metodun del sözcüğünden farklı olduğunu dikkat edin. clear() metodu listenin içeriğini boşaltırken, del sözcüğü listeyi olduğu gibi ortadan kaldırır.

## Demetlerin Metodları

Demetlerin barındırdığı metotları dir() fonksiyonu aracılığı ile listeleyelim:


```python
dir(tuple)
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
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__rmul__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'count',
     'index']



### index()

Bu metot bir demet öğesinin demet içindeki konumunu söyler bize:


```python
demet = ("elma", "armut", "çilek")

demet.index("elma")
```




    0



Listelerin ve karakter dizilerinin index() metoduyla ilgili belirttiğimiz her şey demetlerin index() metodu için de geçerlidir.

### count()

Bu metot bir öğenin o demet içinde kaç kez geçtiğini söyler:


```python
demet = ("elma", "armut", "elma", "çilek")

demet.count("elma")
```




    2



Karakter dizilerinin ve listelerin count() metoduyla ilgili belirttiğimiz her şey demetlerin count() metodu için de geçerlidir.

> Son Güncelleme: 23 Aralık 2019 - Pazartesi
