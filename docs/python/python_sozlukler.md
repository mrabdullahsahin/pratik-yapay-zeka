# Sözlükler

Sözlük ingilizcede **dictionary** demektir. Sözlükler, Python'da bulunan diğer bir veri tipidir. Sözlük, Python programlama dilinin son derece kullanışlı ve işe yarar araçlarından bir tanesidir.

## Sözlük Tanımlamak

Sözlük dediğimiz şey en basit haliyle şöyle görünür ve tanımlanır:


```python
sozluk = {}
```

Bu örnek boş bir sözlüktür. İsterseniz yukarıdaki veri tipinin gerçekten de bir sözlük olduğunu
kanıtlayalım:


```python
type(sozluk)
```




    dict



## Sözlüklerin Yapısı

Sözlükler; anahtar ve değer çiftlerinin birbirleriyle eşleştirildiği bir veri tipidir. Dolayısıyla sözlükler bu anahtar ve değer çiftleri arasında birebir ilişki kurar.

Sözlükler iki adet değerden oluşur. Bunlar. key ve value değerleridir. Sözlük tanımlarken bu yapıyı temel alarak tanımlarız.

<div align="left">
<img src="https://raw.githubusercontent.com/practicalAI/images/master/images/01_Python/dictionaries.png" width="320">
</div>

Sözlüklerin Python programlama dilindeki teknik karşılığı dict ifadesidir. type(sözlük) sorgusu <class ’dict’> çıktısı verdiğine göre, sözlük adlı değişkenin gerçekten de bir sözlük olduğunu söyleyebiliyoruz.


```python
sozluk = {"kitap" : "book",
          "bilgisayar" : "computer",
          "programlama": "programming",
          "dil"        : "language",
          "defter"     : "notebook"}
```

Yukarıda tanımlamış olduğumuz sözlükte görünüşte 10 adet değer var gibi gözükebilir. Fakat öyle değil. Tanımladığımız sözlükte toplam 5 adet değer bulunmaktadır. "kitap" : "book" değeri bir değerdir aslında. len() fonksiyonu ile kontrol edelim.


```python
len(sozluk)
```




    5



Eğer istersek sözlükleri, içlerinde başka sözlükleri barındıracak şekilde de tanımlayabiliriz: 


```python
kisiler = {"Ahmet Özkoparan": {"Memleket": "İstanbul", 
                               "Meslek" : "Öğretmen",
                               "Yaş" : 34},
           "Mehmet Yağız"   : {"Memleket": "Adana",
                               "Meslek"  : "Mühendis",
                               "Yaş"     : 40},
           "Seda Bayrak"    : {"Memleket": "İskenderun",
                               "Meslek"  : "Doktor",
                               "Yaş"     : 30}}
```

Kisiler sözlüğünde Mehmet kişisinin memleketine erişmemiz için şöyle bir kod yazmamız gerekmektdir:


```python
print(kisiler["Mehmet Yağız"]["Memleket"])
```

    Adana


## Sözlük Öğelerine Erişmek

Yukarıda tanımladığımız sözlüğün içerisinde bulunan kitap öğesine erişelim:


```python
print(sözlük["kitap"])
```

    book


Yukarıdaki örnekten anladığımız gibi, sözlük öğelerine erişmek için şöyle bir formül kullanıyoruz:

**sözlük[sözlük_öğesinin_adı]**

Sözlüğün bütün elemanlarına şu kod ile ulaşabiliriz:


```python
for i in sozluk: 
    print(sozluk[i])
```

    book
    computer
    programming
    language
    notebook


## Sözlüklere Öğe Eklemek

Tıpkı listeler gibi, sözlükler de büyüyüp küçülebilen bir veri tipidir. Yani bir sözlüğü ilk kez tanımladıktan sonra istediğimiz zaman bu sözlüğe yeni öğeler ekleyebilir veya varolan öğeleri çıkarabiliriz. Biz şimdi bir sözlüğe nasıl öğe ekleyeceğimizi inceleyeceğiz.

Diyelim ki elimizde şöyle boş bir sözlük var:


```python
sozluk = {}
```

Bu listeye öğe eklemek için şöyle bir formül kullanacağız:

**sozluk[anahtar] = değer**

Bu formülü bir örnek üzerinden somutlaştıralım:


```python
sozluk["Ahmet"] = "Adana"
```

Böylece sözlüğe, anahtarı “Ahmet”, değeri ise “Adana” olan bir öğe eklemiş olduk. Sözlüğümüzün son durumunu kontrol edelim:


```python
print(sozluk)
```

    {'Ahmet': 'Adana'}


Gördüğünüz gibi, “Ahmet” öğesi sözlüğe eklendi. Artık bu öğeye normal yollardan ulaşabiliriz:


```python
print(sozluk["Ahmet"])
```

    Adana


## Sözlük Öğeleri Üzerinde Değişiklik Yapmak

Sözlükler değiştirilebilir veri tipleridir. Dolayısıyla sözlükler üzerinde rahatlıkla istediğimiz değişikliği yapabiliriz.

Sözlükler üzerinde değişiklik yapma işlemi, biraz önce öğrendiğimiz, sözlüklere yeni öğe ekleme işlemiyle aynıdır. Dikkatlice bakın:


```python
notlar = {'Seda': 98, 
          'Ege': 95, 
          'Mehmet': 77, 
          'Zeynep': 100, 
          'Deniz': 95, 
          'Ahmet': 45}
```

Sözlüğümüz bu. Şimdi bu sözlükteki ‘Ahmet’ adlı kişinin 45 olan notunu 65 olarak değiştirelim:


```python
notlar["Ahmet"] = 65
```


```python
print(notlar)
```

    {'Seda': 98, 'Ege': 95, 'Mehmet': 77, 'Zeynep': 100, 'Deniz': 95, 'Ahmet': 65}


Gördüğünüz gibi Ahmet’in notu 65 olarak değişmiş...

## Sözlük Üreteçleri (DictionaryComprehensions)

Liste üreteçlerinde olduğu gibi, sözlük üreteçleri sayesinde tek satırda ve hızlı bir şekilde sözlükler üretebiliriz.

Diyelim ki elinizde şöyle bir isim listesi var:


```python
isimler = ["ahmet", "mehmet", "fırat", "zeynep", "selma", "abdullah", "cem"]
```

Amacınız, bu isimleri ve her bir ismin kaç harften oluştuğunu gösteren bir sözlük elde etmek. İşte bu görev için de sözlük üreteçlerinden yararlanabilirsiniz:


```python
sozluk = {i: len(i) for i in isimler}

sozluk
```




    {'ahmet': 5,
     'mehmet': 6,
     'fırat': 5,
     'zeynep': 6,
     'selma': 5,
     'abdullah': 8,
     'cem': 3}



Bildiğiniz gibi sözlükler, her biri birbirinden : işareti ile ayrılan birtakım anahtar-değer çiftlerinden oluşuyor. İşte yukarıdaki sözlük üreteci yapısında biz : işaretinin sol tarafına isimler adlı listedeki her bir öğeyi; sağ tarafına da bu öğelerin uzunluklarını bir çırpıda ekliyoruz.

> Son Güncelleme: 24 Aralık 2019 - Salı
