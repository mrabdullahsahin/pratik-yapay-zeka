# Karakter Dizilerinin Metotları

## replace()

Bu metot karakter dizisi içerisinde değişiklikler yapabilmemizi sağlar.

Kullanım şekli: karakter_dizisi.replace(eski_karakter_dizisi, yeni_karakter_dizisi). Örneğin:


```python
kelime = "elma"
kelime
```




    'elma'




```python
kelime.replace("e","E")
```




    'Elma'



Bu fonksiyon ile karakter dizileri üzerinde birçok değişiklik yapabilirsiniz.

## split()

Bu metot karakter dizisi içerisinde parçalama yapabilmemizi sağlar.


```python
meyveler = "Elma, Armut, Karpuz, Kiraz"
```


```python
meyveler.split()
```




    ['Elma,', 'Armut,', 'Karpuz,', 'Kiraz']



meyveler değişkeninde bulunan içeriği boşluğa parçaladı fakat verdiği çıktı biraz problemli. Yani her içerik virgül ile beraber gelmiş. Split fonksiyonuna neye göre parçalamasını söylersek onu baz alarak parçalama işlemini yapar.


```python
meyveler.split(",")
```




    ['Elma', ' Armut', ' Karpuz', ' Kiraz']



veya bir harfe göre parçalatabiliriz.


```python
meyveler.split("a")
```




    ['Elm', ', Armut, K', 'rpuz, Kir', 'z']



split fonksiyonu aynı zamanda kaç kere bölmesi gerektiğinide almaktadır. Örneğin:


```python
meyveler.split(",",2)
```




    ['Elma', ' Armut', ' Karpuz, Kiraz']



## rsplit()

rsplit() metodunun split() metodundan farkı sağdan sola doğru okumasıdır. Örneğin:


```python
meyveler.rsplit(",",2)
```




    ['Elma, Armut', ' Karpuz', ' Kiraz']



rsplit() metodu karakter dizisini bölmeye sağdan başladı ve sola doğru gitti, split() metodundan farkı bu.

## splitlines()

Bu metot veriyi satır satır böle bilmemizi sağlamaktadır. Örneğin:


```python
lorem = """Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec magna nulla. 
Sed interdum diam at sem ultrices, nec suscipit massa lobortis. 
Fusce in leo finibus risus lacinia viverra. 
Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. 
Nam eget lorem ornare libero consequat tempus. 
Pellentesque sed odio at magna fringilla euismod a at enim. Fusce aliquet malesuada neque sit amet hendrerit."""
```


```python
print(lorem.splitlines())
```

    ['Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec magna nulla. ', 'Sed interdum diam at sem ultrices, nec suscipit massa lobortis. ', 'Fusce in leo finibus risus lacinia viverra. ', 'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. ', 'Nam eget lorem ornare libero consequat tempus. ', 'Pellentesque sed odio at magna fringilla euismod a at enim. Fusce aliquet malesuada neque sit amet hendrerit.']


Örnekte olduğu gibi splitlines() metodu değerleri satır satır parçaladı.

## lower()

Bu metot değişkenin tuttuğu değerlerin tamamının küçük harfe dönüştürülmesini sağlıyor.


```python
degisken = input("Bir kelime yazınız: ")

print(degisken.lower())
```

    Bir kelime yazınız: MERHABA
    merhaba


Bu fonksiyonun küçük bir problemi var. Türkçe karakter duyarlılığı yoktur. Bu durumu bilmekte fayda var.


```python
iller = "ISPARTA, ADIYAMAN, DİYARBAKIR, AYDIN, BALIKESİR, AĞRI"

iller = iller.replace("I", "ı").replace("İ", "i").lower()

print(iller)
```

    ısparta, adıyaman, diyarbakır, aydın, balıkesir, ağrı


## upper()

Bu metot değişkenin tuttuğu değerlerin tamamının büyük harfe dönüştürülmesini sağlıyor.


```python
degisken = "oku"

print(degisken.upper())
```

    OKU


Bu metodunda aynı şekilde Türkçe karakter duyarlılığı yoktur. Bu durumu bilmekte fayda var.


```python
iller = "istanbul, izmir, siirt, mersin"

iller = iller.replace("i", "İ").upper() 

print(iller)
```

    İSTANBUL, İZMİR, SİİRT, MERSİN


## islower()

Bu metot bir değişkenin tuttuğu değerin küçük olup olmadığını kontrol ediyor.


```python
deger = "Deger"

deger.islower()
```




    False




```python
deger = "deger"

deger.islower()
```




    True



## isupper()

Bu metot bir değişkenin tuttuğu değerin büyük olup olmadığını kontrol ediyor.


```python
deger = "Deger"

deger.isupper()
```




    False




```python
deger = "DEGER"

deger.isupper()
```




    True



## endswith()

Bu metot yardımıyla bir karakter dizisinin hangi karakter dizisi ile bittiğini sorgulayabiliyoruz. Örneğin:


```python
deger = "deger"

deger.endswith("r")
```




    True



## startswith()

Bu metot yardımıyla bir karakter dizisinin hangi karakter dizisi ile başladığını sorgulayabiliyoruz. Örneğin:


```python
deger = "Deger"

deger.startswith("D")
```




    True



## capitalize()

Bu metot yardımıyla bir karakter dizisinin sadece ilk harfini büyütebiliriz.


```python
deger = "deger"

deger.capitalize()
```




    'Deger'



## title()

Bu metot yardımıyla bir karakter dizisinin ilk harflerini büyütmektedir.


```python
deger = "python programlama dili"

deger.title()
```




    'Python Programlama Dili'



## swapcase()

Bu metot bir karakter dizisi içindeki büyük harfleri küçük harfe; küçük harfleri de büyük harfe dönüştürür. Örneğin:


```python
deger = "PythoN"

deger.swapcase()
```




    'pYTHOn'



## casefold()

Bu metot lower() metoduna benzerdir.


```python
deger = "DeGer"

deger.casefold()
```




    'deger'



## strip()

Bu metot karakter dizilerinde bulunan boşlukları silmektedir. Aynı zamanda boşluğun haricinde bizim belirttiğimiz değere göre silme işlemini yapmaktadır.


```python
deger = "deger   "

deger.strip()
```




    'deger'



strip() metodunun ön tanımlı olarak kırptığı karakterler: 

- ‘‘ boşluk karakteri
- \t sekme (TAB) oluşturan kaçış dizisi
- \n satır başına geçiren kaçış dizisi
- \r imleci aynı satırın başına döndüren kaçış dizisi \v düşey sekme oluşturan kaçış dizisi
- \f yeni bir sayfaya geçiren kaçış dizisi

Eğer istersek bizim verdiğimi değere görede kırpma işlemini gerçekleştirebilir. Örneğin:


```python
deger = "Python"

deger.strip("P")
```




    'ython'



## lstrip()

Bu metot strip() metodu ile aynı işlemi yapmaktadır. Fakat farklı olarak sol tarafta bulunan gereksiz karakterleri siler.


```python
deger = "   Python  "

deger.lstrip()
```




    'Python  '



Bir başka örnek:


```python
deger = "Python P"

deger.lstrip("P")
```




    'ython P'



## rstrip()

Bu metot strip() metodu ile aynı işlemi yapmaktadır. Fakat farklı olarak sağ tarafta bulunan gereksiz karakterleri siler.


```python
deger = " Python  "

deger.rstrip()
```




    ' Python'



Bir başka örnek:


```python
deger = "Python P"

deger.rstrip("P")
```




    'Python '



## join()

Bu metot karakter dizilerini birleştirmemize yarar.


```python
karakter = "Python Programlama Dili"
bolunmus = karakter.split()
print(bolunmus)
```

    ['Python', 'Programlama', 'Dili']


Şimdi tekrar birleştirelim.


```python
" ".join(bolunmus)
```




    'Python Programlama Dili'



Burada boşluk karakterini kullandık. Eğer isterseniz daha farklı karakterler kullanabilirsiniz.

## count()

Bu metodun görevi bir karakter dizisi içinde belli bir karakterin kaç kez geçtiğini sorgulamaktır


```python
deger = "Fatih Sultan Mehmet 1453 yılında İstanbul'u fethetti."
```


```python
deger.count("a")
```




    4



Bu metot bir parametre daha almaktadır. Bu parametrede kaçıncı sıradan başlayacağını gösteriyor.


```python
deger.count("a", 5)
```




    3



## index()

Bu metot karakter dizisinde bulunan bir değerin kaçıncı indekste olduğunu öğrenebilmemize yarar.


```python
deger = "Fatih"
```


```python
deger.index("F")
```




    0



index metodu ikinci bir parametre almaktadır. Bu parametre kaçıncı sıradan aramaya başlayacağını göstermektedir.


```python
deger.index("i",1)
```




    3



Bu metot üçüncü bir parametre daha almaktadır. Bu parametrede bir önceki parametre ile dilimleme yapıp, dilimlemenin yapıldığı aralıkta aramasını belirttiğimiz değeri aramaktadır.


```python
deger.index("i",1,4)
```




    3



## rindex()

Bu metot karakter dizisini sağdan sola doğru okur.


```python
deger.rindex("h")
```




    4



## find()

Bu metot index() metodu ile aynı işi yapmaktadır.


```python
deger.find("i")
```




    3



## rfind()

Bu metot rindex() metodu ile aynı işi yapmaktadır.


```python
deger.rfind("h")
```




    4



## center()

Bu metot karakter dizisini merkezde tutmamıza yarar.


```python
deger = "python"
```


```python
deger.center(10)
```




    '  python  '



Bu metot ikinci bir parametre almaktadır. Bu parametrede boşluğun haricinde farklı karakterlerde kullanabilmemizi sağlamaktadır.


```python
deger.center(20,"-")
```




    '-------python-------'



## rjust()

Bu metot bir karakter dizisini sağa yaslar.


```python
deger = "python"
```


```python
deger.rjust(10,"-")
```




    '----python'



## ljust()

Bu metot bir dizisini sola yaslar.


```python
deger = "python"
```


```python
deger.ljust(10,"-")
```




    'python----'



## zfill()

Bu metot yardımıyla karakter dizisinin sol tarafına istediğimiz sayıda sıfır ekleyebiliriz.


```python
deger = "python"
```


```python
deger.zfill(10)
```




    '0000python'



## partition()

Bu metot yardımıyla karakter dizisini belli bir ölçüte göre üçe ayırıyoruz.


```python
deger = "istanbul"
```


```python
deger.partition("an")
```




    ('ist', 'an', 'bul')



## rpartition()

Bu metot yardımıyla karakter dizisini sağdan sola doğru belli bir ölçüte göre üçe ayırıyoruz.


```python
deger = "adana"
```


```python
deger.rpartition("a")
```




    ('adan', 'a', '')



## encode()

Bu metot yardımıyla karakter dizilerimizi istediğimiz kodlama sistemine göre kodlayabiliriz.


```python
"fatih".encode("cp1254")
```




    b'fatih'



## expandtabs()

Bu metot yardımıyla karakter dizisi içindeki sekme boşluklarını genişletebiliyoruz.


```python
deger = "elma\tbir\tmeyvedir"
```


```python
deger.expandtabs(10)
```




    'elma      bir       meyvedir'



## str.maketrans(), translate()

Bu metotlar genelde beraber kullanıldığı için buradada beraber kullanacağız. Şu şekilde bir durum olduğunu düşünelim, internette bazen Türkçe karakter kullanmamamızı gerektiren durumlar oluyor. Böyle bir durumu bu metodlar ile çözeceğiz ve yazdığımız Türkçe karakter barındıran bir cümleyi Türkçe karakter barındırmayan bir hale getirecek.


```python
kaynak = "şçöğüıŞÇÖĞÜİ" 
hedef = "scoguiSCOGUI"

çeviri_tablosu = str.maketrans(kaynak, hedef)

metin = "Bildiğiniz gibi, internet üzerinde bazen Türkçe karakterleri kullanamıyoruz." 

print(metin.translate(çeviri_tablosu))
```

    Bildiginiz gibi, internet uzerinde bazen Turkce karakterleri kullanamiyoruz.


## isalpha()

Bu metot yardımı ile bir karakter dizisinin alfabetik olup olmadığını denetleyebiliriz.


```python
deger = "ağaç"
```


```python
deger.isalpha()
```




    True



Bir başka örneğe bakalım:


```python
deger = "Ağaç1"
```


```python
deger.isalpha()
```




    False



## isdigit()

Bu metot yardımı ile bir karakter dizisinin nümerik olup olmadığını denetleyebiliriz.


```python
deger = "12345"
```


```python
deger.isdigit()
```




    True



Bir başka örneğe bakalım:


```python
deger = "A1"
```


```python
deger.isdigit()
```




    False



## isalnum()

Bu metot yardımı ile bir karakter dizisinin alfanümerik olup olmadığını denetleyebiliriz.


```python
deger = "a1"
```


```python
deger.isalnum()
```




    True



Bir başka örneğe bakalım:


```python
deger = "a1>"
```


```python
deger.isalnum()
```




    False



## isdecimal()

Bu metot yardımı ile bir karakter dizisinin ondalık sayı cinsinden olup olmadığını denetleyebiliriz.


```python
deger = "123"
```


```python
deger.isdecimal()
```




    True



Bir başka örneğe bakalım:


```python
"123.4".isdecimal()
```




    False



## isidentifier()

Bu metot ile neyin tanımlayıcı olup neyin tanımlayıcı olamayacağını denetleyebiliriz.


```python
"1a".isidentifier()
```




    False



Python'da değişkenler rakam ile başlayamaz bu yüzden bu metod bizlere False değerini verdi.

## isnumeric()

Bu metot ile bir karakter dizisinin nümerik olup olmadığını denetleyebiliriz.


```python
"12".isnumeric()
```




    True



Bir başka örneğe bakalım:


```python
"ad".isnumeric()
```




    False



## isspace()

Bu metot ile bir karakter dizisinin tamamen boşluklardan oluşup olmadığını denetleyebiliriz.


```python
"Bu bir boşluk değil.".isspace()
```




    False



Bir başka örneğe bakalım:


```python
"       ".isspace()
```




    True



## isprintable()

Bu metot ile bir karakterin basılabilen bir karakter mi yoksa basılmayan bir karakter mi olduğunu denetleyebiliriz.


```python
"ahmet".isprintable()
```




    True



Bir başka örneğe bakalım:


```python
"\n".isprintable()
```




    False



> Son Güncelleme: 18 Aralık 2019 - Çarşamba
