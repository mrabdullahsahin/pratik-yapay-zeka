# Sözlüklerin Metotları

## keys()

Sözlükleri tarif ederken, sözlüklerin anahtar-değer çiftlerinden oluşan bir veri tipi olduğunu söylemiştik. Bir sözlüğü normal yollardan ekrana yazdırırsanız size hem anahtarları hem de bunlara karşılık gelen değerleri verecektir. Ama eğer bir sözlüğün sadece anahtarlarını almak isterseniz keys() metodundan yararlanabilirsiniz:


```python
sozluk = {"a": 0, 
          "b": 1, 
          "c": 2, 
          "d": 3}

print(sozluk.keys())
```

    dict_keys(['a', 'b', 'c', 'd'])


Gördüğünüz gibi, sözlük.keys() komutu bize bir dict_keys nesnesi veriyor. Bu nesneyi programınızda kullanabilmek için isterseniz, bunu listeye, demete veya karakter dizisine dönüştürebilirsiniz:


```python
liste = list(sozluk.keys())

liste
```




    ['a', 'b', 'c', 'd']




```python
demet = tuple(sozluk.keys())

demet
```




    ('a', 'b', 'c', 'd')




```python
kardiz = "".join(sozluk.keys())

kardiz
```




    'abcd'



## values()

Bir sözlüğün değerlerini values() metodu verir:


```python
print(sozluk.values())
```

    dict_values([0, 1, 2, 3])


## items()

Bu metot, bir sözlüğün hem anahtarlarını hem de değerlerini aynı anda almamızı sağlar:


```python
sozluk.items()
```




    dict_items([('a', 0), ('b', 1), ('c', 2), ('d', 3)])



Bu metot sıklıkla for döngüleri ile birlikte kullanılarak bir sözlüğün anahtar ve değerlerinin manipüle edilebilmesini sağlar:


```python
for anahtar, deger in sozluk.items():
    print("{} = {}".format(anahtar, deger))
```

    a = 0
    b = 1
    c = 2
    d = 3


## get()

Sözlüklerin get() adlı metodu, parantez içinde iki adet argüman alır. Birinci argüman sorgulamak istediğimiz sözlük öğesidir. İkinci argüman ise bu öğenin sözlükte bulunmadığı durumda kullanıcıya hangi mesajın gösterileceğini belirtir. Buna göre, aşağıda yaptığımız şey, önce “sorgu” değişkenini sözlükte aramak, eğer bu öğe sözlükte bulunamıyorsa da kullanıcıya, “Bu kelime veritabanımızda yoktur!” cümlesini göstermekten ibarettir...


```python
ing_sozluk = {"dil": "language", "bilgisayar": "computer", "masa": "table"} 

sorgu = input("Lütfen anlamını öğrenmek istediğiniz kelimeyi yazınız:") 

print(ing_sozluk.get(sorgu, "Bu kelime veritabanımızda yoktur!"))
```

    Lütfen anlamını öğrenmek istediğiniz kelimeyi yazınız:araba
    Bu kelime veritabanımızda yoktur!


## clear()

Bu kelime İngilizce’de “temizlemek” anlamına gelir. Görevi sözlükteki öğeleri temizlemektir. Yani içi dolu bir sözlüğü bu metot yardımıyla tamamen boşaltabiliriz:


```python
lig = {"şampiyon": "Adana Demirspor", 
       "ikinci": "Mersin İdman Yurdu", 
       "üçüncü": "Adana Gençlerbirliği"}
```

İsterseniz sözlüğümüzü boşaltmadan önce bu sözlükle biraz çalışalım: Sözlüğümüzün öğelerine şöyle ulaşıyoruz:


```python
lig
```




    {'şampiyon': 'Adana Demirspor',
     'ikinci': 'Mersin İdman Yurdu',
     'üçüncü': 'Adana Gençlerbirliği'}



Şimdi geldi bu sözlüğün bütün öğelerini silmeye:


```python
lig.clear()
```

Şimdi sözlüğümüzün durumunu tekrar kontrol edelim:


```python
lig
```




    {}



Gördüğünüz gibi artık “lig” adlı sözlüğümüz bomboş. clear() metodunu kullanarak bu sözlüğün bütün öğelerini sildik. Ama tabii ki bu şekilde sözlüğü silmiş olmadık. Boş da olsa bellekte hâlâ “lig” adlı bir sözlük duruyor. Eğer siz “lig”i ortadan kaldırmak isterseniz “del” adlı bir parçacıktan yararlanmanız gerekir:


```python
del lig
```

Kontrol edelim:


```python
lig
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-14-f416219c5a5e> in <module>
    ----> 1 lig
    

    NameError: name 'lig' is not defined


Gördüğünüz gibi artık “lig” diye bir şey yok... Bu sözlüğü bellekten tamamen kaldırdık.

## copy()

Bu metot sözlüğü kopyalamaya yaramaktadır.


```python
hava_durumu = {"İstanbul": "yağmurlu", 
               "Ankara": "güneşli", 
               "Konya": "bulutlu"}
```

Şimdi bu sözlüğü yedekliyoruz. Yani kopyalıyoruz:


```python
yedek_hava_durumu = hava_durumu.copy()
```

yedek_hava_durumu adlı sözlüğe bakalım:


```python
yedek_hava_durumu
```




    {'İstanbul': 'yağmurlu', 'Ankara': 'güneşli', 'Konya': 'bulutlu'}



## fromkeys()

fromkeys() metodu öteki metotlardan biraz farklıdır. Bu metot mevcut sözlük üzerinde işlem yapmaz. fromkeys()‘in görevi yeni bir sözlük oluşturmaktır. Bu metot yeni bir sözlük oluştururken listeler veya demetlerden yararlanır. Şöyle ki:


```python
elemanlar = "Ahmet", "Mehmet", "Can"

adresler = dict.fromkeys(elemanlar, "Kadıköy")

adresler
```




    {'Ahmet': 'Kadıköy', 'Mehmet': 'Kadıköy', 'Can': 'Kadıköy'}



Gördüğünüz gibi öncelikle “elemanlar” adlı bir demet tanımladık. Daha sonra da “adresler” adlı bir sözlük tanımlayarak, fromkeys() metodu yardımıyla anahtar olarak “elemanlar” demetindeki öğelerden oluşan, değer olarak ise “Kadıköy”ü içeren bir sözlük meydana getirdik.


En başta tanımladığımız “elemanlar” demeti liste de olabilirdi. Hatta tek başına bir karakter dizisi dahi yazabilirdik oraya...

## pop()

Bu metodun sözlüklerdeki kullanımı, listelerdeki kullanımına az çok benzer. Ama burada farklı olarak, pop metodunu argümansız bir şekilde kullanamıyoruz. Yani pop metodunun parantezi içinde mutlaka bir sözlük öğesi belirtmeliyiz:


```python
sepet = {"meyveler": ("elma", "armut"), 
         "sebzeler": ("pırasa", "fasulye"), 
         "içecekler": ("su", "kola", "ayran")}

sepet.pop("meyveler")
```




    ('elma', 'armut')



Bu komut, sözlükteki “meyveler” anahtarını silecek ve sildiği bu öğenin değerini ekrana basacaktır. Eğer silmeye çalıştığımız anahtar sözlükte yoksa Python bize bir hata mesajı gösterecektir. Eğer get() fonksiyonunda olduğu gibi bir kullanım burada yapılırsa hatadan kurtulunmuş olunur. Örneğin:


```python
sepet.pop("tatlılar", "Silinecek öğe yok!")
```




    'Silinecek öğe yok!'



## popitem()

popitem() metodunun parantezi boş, yani parametresiz olarak kullanılır. Bu metot bir sözlükten rastgele öğeler silmek için kullanılır. Daha önce de pek çok kez söylediğimiz gibi, sözlükler sırasız veri tipleridir. Dolayısıyla popitem() metodunun öğeleri silerken kullanabileceği bir sıra kavramı yoktur. Bu yüzden bu metot öğeleri rastgele silmeyi tercih eder...


```python
sepet = {"meyveler": ("elma", "armut"), 
         "sebzeler": ("pırasa", "fasulye")}

sepet.popitem()
```




    ('sebzeler', ('pırasa', 'fasulye'))



## setdefault()

Bu metot epey enteresan, ama bir o kadar da yararlı bir araçtır... Bu metodun ne işe yaradığını doğrudan bir örnek üzerinde görelim:


```python
sepet = {"meyveler": ("elma", "armut"), 
         "sebzeler": ("pırasa", "fasulye")}

sepet.setdefault("içecekler", ("su", "kola"))
```




    ('su', 'kola')



Bu komut yardımıyla sözlüğümüz içinde “içecekler” adlı bir anahtar oluşturduk. Bu anahtarın değeri ise (“su”, “kola”) oldu... Bir de şuna bakalım:


```python
sepet.setdefault("meyveler", ("erik", "çilek"))
```




    ('elma', 'armut')



Gördüğünüz gibi, sözlükte zaten “meyveler” adlı bir anahtar bulunduğu için, Python aynı adı taşıyan ama değerleri farklı olan yeni bir “meyveler” anahtarı oluşturmadı. Demek ki bu metot yardımıyla bir sözlük içinde arama yapabiliyor, eğer aradığımız anahtar sözlükte yoksa, setdefault() metodu içinde belirttiğimiz özellikleri taşıyan yeni bir anahtar-değer çifti oluşturabiliyoruz.

## update()

Bu metot yardımıyla oluşturduğumuz sözlükleri yeni verilerle güncelleyeceğiz. Diyelim ki elimizde şöyle bir sözlük var:


```python
stok = {"elma": 5, "armut": 10, "peynir": 6, "sosis": 15}
```

Stoğumuzda 5 adet elma, 10 adet armut, 6 kutu peynir, 15 adet de sosis var. Diyelim ki daha sonraki zamanlarda bu stoğa mal giriş-çıkışı oldu ve stoğun son hali şöyle:


```python
yeni_stok = {"elma": 3, "armut": 20, "peynir": 8, "sosis": 4, "sucuk": 6}
```

Yapmamız gereken şey, stoğumuzu yeni bilgilere göre güncellemek olacaktır. İşte bu işlemi update() metodu ile yapabiliriz:


```python
stok.update(yeni_stok)
```


```python
print(stok)
```

    {'elma': 3, 'armut': 20, 'peynir': 8, 'sosis': 4, 'sucuk': 6}


> Son Güncelleme: 24 Aralık 2019 - Salı
