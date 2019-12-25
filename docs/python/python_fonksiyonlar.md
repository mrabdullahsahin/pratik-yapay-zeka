# Fonksiyonlar

## Fonksiyon Nedir ve Ne İşe Yarar?

Fonksiyonların genel görünüşü ve yapısı:

1. Her fonksiyonun bir adı bulunur ve fonksiyonlar sahip oldukları bu adlarla anılır. (print fonksiyonu, open fonksiyonu, type fonksiyonu, input fonksiyonu, len fonksiyonu vb.)

2. Şekil olarak, her fonksiyonun isminin yanında birer parantez işareti bulunur. (open(), print(), input(), len() vb.)

3. Bu parantez işaretlerinin içine, fonksiyonlara işlevsellik kazandıran bazı parametreler yazılır. (open(dosya_adı), print("Merhaba Zalim Dünya!"), len("kahramanmaraş") vb.)

4. Fonksiyonlar farklı sayıda parametre alabilir. Örneğin print() fonksiyonu toplam 256 adet parametre alabilirken, input() fonksiyonu yalnızca tek bir parametre alır.

5. Fonksiyonların isimli ve isimsiz parametreleri vardır. print() fonksiyonundaki sep, end ve file parametreleri isimli parametrelere örnekken, mesela print("Merhaba Dünya!") kodunda Merhaba Dünya! parametresi isimsiz bir parametredir. Aynı şekilde input("Adınız: ") gibi bir kodda Adınız: parametresi isimsiz bir parametredir.

6. Fonksiyonların, isimli ve isimsiz parametreleri dışında, bir de varsayılan değerli parametreleri vardır. Örneğin print() fonksiyonunun sep, end ve file parametreleri varsayılan değerli parametrelere birer örnektir. Eğer bir parametrenin varsayılan bir değeri varsa, o parametreye herhangi bir değer vermeden de fonksiyonu kullanabiliriz. Python bu parametrelere, belirli değerleri öntanımlı olarak kendisi atayacaktır. Tabii eğer istersek, varsayılan değerli parametrelere kendimiz de başka birtakım değerler verebiliriz.

Fonksiyonların görevi, karmaşık işlemleri bir araya toplayarak, bu işlemleri tek adımda yapmamızı sağlamaktır. Fonksiyonlar çoğu zaman, yapmak istediğimiz işlemler için bir şablon vazifesi görür. Fonksiyonları kullanarak, bir veya birkaç adımdan oluşan işlemleri tek bir isim altında toplayabiliriz. Python’daki ‘fonksiyon’ kavramı başka programlama dillerinde ‘rutin’ veya ‘prosedür’ olarak adlandırılır. Gerçekten de fonksiyonlar rutin olarak tekrar edilen görevleri veya prosedürleri tek bir ad/çatı altında toplayan araçlardır.

Fonksiyonları daha iyi kavramak için print() fonksiyonunu ele alalım:

1. Kendisine verilen “Python” ve "2000" gibi değerleri ekrana basıyor,

2. sep=” “ parametresinin etkisiyle, bu parametreler arasına birer boşluk ekliyor,

3. end=”\n” parametresinin etkisiyle, sonuncu parametreyi de ekrana bastıktan sonra bir alt satıra geçiyor,

4. file=sys.stdout parametresinin etkisiyle, çıktı konumu olarak komut ekranını kullanıyor. Yani çıktıları ekrana veriyor.

5. flush=False parametresinin etkisiyle, çıktılar ekrana gönderilmeden önce tamponda bekletiliyor.

## Fonksiyon Tanımlamak ve Çağırmak

Fonksiyon tanımalama ve çağırma işlemini bir örnek üzerinden anlamaya çalışalım. Elimizde bulunan kayıt oluştur isimli fonksiyon ile ekrana şu şekilde bir çıktı verelim:

'-------------------------'

isim : Mehmet 

soyisim : Öztaban 

işletim sistemi: Debian

şehir : Ankara

'-------------------------'

İlk olarak kayıt_olustur() adlı fonksiyonu kullanabilmek için bu ada sahip fonksiyonu aşağıdaki şekilde tanımlamalıyız:


```python
def kayıt_olustur(isim, soyisim, isletim, sehir): 
    print("-"*30)
    
    print("isim           : ", isim)
    print("soyisim        : ", soyisim)
    print("işletim sistemi: ", isletim)
    print("şehir          : ", sehir)
    
    print("-"*30)
```

Fonksiyonumuzu test edelim:


```python
kayıt_olustur("Abdullah","Şahin","Windows","Konya")
```

    ------------------------------
    isim           :  Abdullah
    soyisim        :  Şahin
    işletim sistemi:  Windows
    şehir          :  Konya
    ------------------------------


Görmüş olduğunuz gibi yazmış olduğumuz fonksiyon çalıştı. Şimdi yazığımız yapıyı irdeleyelim:

1. Kodlar def adlı bir ifade ile başlamış. Bu ifadenin ingilizce olarak açılımı definition.
2. Bunun ardından ‘kayıt_olustur’ ifadesini görüyoruz.
3. Bu ifadeyi, içinde birtakım kelimeler barındıran bir parantez çifti izliyor. 
4. Parantezin içinde, isim, soyisim, isletim ve sehir adlı değerler var.
5. def ile başlayan bu satır iki nokta üst üste işareti ile son buluyor.
6. İlk satırın ardından gelen kısım ilk satıra göre girintili bir şekilde yazılmış.
7. kayıt_olustur("Abdullah","Şahin","Windows","Konya") satırı önceki satırlara göre girintisiz yazılmış.

Eğer bu kodlara dikkatlice bakacak olursanız, aslında bu kodların topu topu iki parçadan oluştuğunu göreceksiniz. İsterseniz yukarıdaki yapıyı biraz sadeleştirelim:

```python
def kayıt_olustur(parametre1, parametre2, parametre3, parametre4): 

    (...)
    
    
kayıt_olustur(parametre1, parametre2, parametre3, parametre4)
```

Bu yapının ilk parçası şudur:

 ```python
 def kayıt_olustur(parametre1, parametre2, parametre3, parametre4): 
 
     (...)
 ```

İkinci parçası ise şu:

```python
kayıt_olustur(parametre1, parametre2, parametre3, parametre4)
```

Teknik olarak söylemek gerekirse, ilk parçaya ‘fonksiyon tanımı’ (function definition), ikinci parçaya ise ‘fonksiyon çağrısı’ (function call ) adı verilir. Dolayısıyla bir fonksiyonun yaşam döngüsü iki aşamadan oluşur. Buna göre bir fonksiyon önce tanımlanır;

```python
def kayıt_oluştur(parametre1, parametre2, parametre3, parametre4): 
    (...)
```

...sonra da çağrılır. Bir fonksiyon çağrılmadan **asla** çalışmaz.

```python
kayıt_olustur(parametre1, parametre2, parametre3, parametre4)
```

## Fonksiyonların Yapısı

Bir fonksiyonun ilk parçasına ‘fonksiyon tanımı’ (function definition) adı verilir. Bir fonksiyonu tanımlamak için def adlı bir parçacıktan yararlanıyoruz. Örneğin:

```python
def bir_fonksiyon(): 
    (...)
```

Burada def parçacığı, tanımladığımız şeyin bir fonksiyon olduğunu gösteriyor. bir_fonksiyon ifadesi ise tanımladığımız bu fonksiyonun adıdır. Fonksiyonu tanımladıktan sonra, çağırırken bu adı kullanacağız.

def bir_fonksiyon(): ifadesinin sonundaki iki nokta işaretinden de tahmin edebileceğiniz gibi, sonraki satıra yazacağımız kodlar girintili olacak. Fonksiyon gövdesine, def ifadesinden itibaren 4 (dört) boşlukluk bir girinti veriyoruz. def ifadesinden itibaren girintili olarak yazdığımız kısmın tamamı o fonksiyonun gövdesini oluşturur ve bütünüyle o fonksiyona aittir.

Örneğin:

```python
def selamla():
    print("Merhaba Dünya!")
```

Fonksiyonlarla ilgili söylediklerimizi toparlayacak olursak şöyle bir bilgi listesi ortaya çıkarabiliriz:

1. Python’da kabaca iki tip fonksiyon bulunur. Bunlardan biri gömülü fonksiyonlar (builtin functions ), öteki ise özel fonksiyonlardır (custom functions ). Burada ‘özel’ ifadesi, ‘kullanıcının ihtiyaçlarına göre kullanıcı tarafından özel olarak üretilmiş’ anlamına gelir.

2. Gömülü fonksiyonlar; Python geliştiricileri tarafından tanımlanıp dilin içine gömülmüş olan print(), open(), type(), str(), int() vb. fonksiyonlardır. Bu fonksiyonlar halihazırda tanımlanıp hizmetimize sunulduğu için bunları biz herhangi bir tanımlama işlemi yapmadan doğrudan kullanabiliriz.

3. Özel fonksiyonlar ise, gömülü fonksiyonların aksine, Python geliştiricileri tarafından değil, bizim tarafımızdan tanımlanmıştır. Bu fonksiyonlar dilin bir parçası olmadığından, bu fonksiyonları kullanabilmek için bunları öncelikle tanımlamamız gerekir.

4. Python’da bir fonksiyonun yaşam döngüsü iki aşamadan oluşur: Tanımlanma ve çağrılma.

5. Bir fonksiyonun çağrılabilmesi (yani kullanılabilmesi) için mutlaka birisi tarafından tanımlanmış olması gerekir.

6. Fonksiyonu tanımlayan kişi Python geliştiricileri olabileceği gibi, siz de olabilirsiniz. Ama neticede ortada bir fonksiyon varsa, bir yerlerde o fonksiyonun tanımı da vardır.

7. Fonksiyon tanımlamak için def adlı bir ifadeden yararlanıyoruz. Bu ifadeden sonra, tanımlayacağımız fonksiyonun adını belirleyip iki nokta üst üste işareti koyuyoruz. İki nokta üst üste işaretinden sonra gelen satırlar girintili olarak yazılıyor. Daha önce öğrendiğimiz bütün girintileme kuralları burada da geçerlidir.

8. Fonksiyonun adını belirleyip iki nokta üst üste koyduktan sonra, alt satırda girintili olarak yazdığımız bütün kodlar fonksiyonun gövdesini oluşturur. Doğal olarak, bir fonksiyonun gövdesindeki bütün kodlar o fonksiyona aittir. Girintinin dışına çıkıldığı anda fonksiyon tanımı da sona erer.

## Fonksiyonlar Ne İşe Yarar?

Fonksiyonlar bir program içerisinde sürekli olarak yapmamız gereken işlemleri tekrar etmemizi engelleyen yapılardır.

Örnek vermek gerekirse, siz programınızda kare alma işlemini yapacaksınız ve bunu birçok kez kullanmanız gerekecekse bunu fonksiyon haline getirmek işlemlerinizi biraz daha kolaylaştıracaktır. Örneğimizi inceleyelim:


```python
sayı = 12
çıktı = "{} sayısının karesi {} sayısıdır" 
print(çıktı.format(sayı, sayı**2))
```

    12 sayısının karesi 144 sayısıdır


Bu kodu birçok yerde tekrar ettiğinizi varsayarsak, şu şekilde bir görüntü oluşacak:


```python
sayı = 12
çıktı = "{} sayısının karesi {} sayısıdır" 
print(çıktı.format(sayı, sayı**2))

####programla ilgili başka kodlar###

sayı = 14
print(çıktı.format(sayı, sayı**2))

###programla ilgili başka kodlar###

sayı = 53
print(çıktı.format(sayı, sayı**2))
```

    12 sayısının karesi 144 sayısıdır
    14 sayısının karesi 196 sayısıdır
    53 sayısının karesi 2809 sayısıdır


Görmüş olduğunuz gibi fazladan zaman harcadık ve gereksiz bir kod kalabalığı oluştu. Bu işlemi bir fonksiyon ile yapalım:


```python
def kare_bul(sayi): 
    sonuc = "{} sayısının karesi {} sayısıdır" 
    print(sonuc.format(sayi, sayi**2))
```

Şimdide tanımladığımız bu fonksiyonu çağıralım.


```python
kare_bul(12)
```

    12 sayısının karesi 144 sayısıdır


kare_bul fonksiyonu ile işlerimiz hem kolaylaştı hem de kod tekrarından kaçınmış olduk.

## Parametreler ve Argümanlar

Parametreler fonksiyon tanımlarken parantez içinde belirttiğimiz, fonksiyon gövdesinde yapılan işin değişken öğelerini gösteren parçalardır. Bir fonksiyonu tanımlarken belirlediğimiz adlara **parametre**, aynı fonksiyonu çağırırken belirlediğimiz adlara ise **argüman** deniyor.

Örneğin:

```python
def kopyala(kaynak_dosya, hedef_dizin): #bu kısımda bulunan değerler parametredir.
    cikti = "{} adlı dosya {} adlı dizin içine kopyalandı!" 
    print(cikti.format(kaynak_dosya, hedef_dizin))
    
kopyala("deneme.txt", "/home/abdullah/Desktop") #bu kısımda tırnak içinde tanımladıklarımız ise argümandır.
```

Burada **kopyala()** adlı bir fonksiyon tanımladık. Bu fonksiyon toplam iki adet parametre alıyor: **kaynak_dosya** ve **hedef_dizin**. Gördüğünüz gibi, bu iki parametre gerçekten de fonksiyon gövdesinde yapılan işin değişken öğelerini gösteriyor. Bu fonksiyonun üreteceği çıktı, fonksiyonu çağıran kişinin bu iki parametreye vereceği değerlere bağlı olarak şekillenecek.

### Sıralı (veya İsimsiz) Parametreler

Python’da şöyle bir fonksiyon tanımlayabileceğimizi biliyoruz:

```python
def kayit_olustur(isim, soyisim, isletim, sehir): 
    print("-"*30)
    
    print("isim           : ", isim)
    print("soyisim        : ", soyisim)
    print("işletim sistemi: ", isletim)
    print("şehir          : ", sehir)
    
    print("-"*30)

```

Yukarıda tanımladığımız bu fonksiyonu şu şekilde çağırabiliriz:

```python
kayit_olustur("Ahmet", "Öz", "Debian", "Ankara")
```

Bu fonksiyonda, yazdığımız parametrelerin sırası büyük önem taşır. Mesela yukarıdaki
fonksiyonu şöyle çağırdığımızı düşünün:

```python
kayit_olustur("Debian", "Ankara", "Öz", "Ahmet")
```

Eğer fonksiyon parametrelerini bu sırayla kullanırsak aldığımız çıktı hatalı olacaktır:

'------------------------------'

isim : Debian 
    
soyisim : Ankara 
    
işletim sistemi: Öz
    
şehir : Ahmet 

'------------------------------'

Gördüğünüz gibi, isim, soyisim ve öteki bilgiler birbirine karışmış. İşte Python’da, veriliş sırası önem taşıyan bu tür parametrelere ‘sıralı parametreler’ (veya isimsiz parametreler) adı verilir.

### İsimli Parametreler

Bir önceki bölümde verdiğimiz şu örneği yeniden ele alalım:

```python
def kayıt_oluştur(isim, soyisim, isletim, sehir): 
    print("-"*30)
    print("isim           : ", isim)
    print("soyisim        : ", soyisim)
    print("işletim sistemi: ", isletim)
    print("şehir          : ", sehir)
    print("-"*30)
```

Bu fonksiyonu çağırırken parametrelerin sırasını doğru vermenin, alacağımız çıktının düzgün olması bakımından büyük önem taşıdığını biliyoruz. Ancak özellikle parametre sayısının çok olduğu fonksiyonlarda parametre sırasını akılda tutmak zor olabilir. Böyle durumlarda parametreleri isimleri ile birlikte kullanmayı tercih edebiliriz:

```python
kayit_olustur(soyisim="Öz", isim="Ahmet", isletim="Debian", sehir= "Ankara")
```

Böylece fonksiyon parametrelerini istediğimiz sıra ile kullanabiliriz. Ancak burada dikkat etmemiz gereken bazı noktalar var. Python’da isimli bir parametrenin ardından sıralı bir parametre gelemez. Yani şu kullanım yanlıştır:

```python
kayit_olustur(soyisim="Öz", isim="Ahmet", "Debian", "Ankara")
```

Bu kodlar bize şu hatayı verir:

```python
   File "<stdin>", line 1
SyntaxError: non-keyword arg after keyword arg
```

Bu yüzden, eğer isimli parametreler kullanacaksak, isimli parametrelerden sonra sıralı parametre kullanmamaya dikkat ediyoruz.

### Varsayılan Değerli Parametreler

Bu durumu print fonksiyonu üzerinden açıklamaya çalışalım:

```python
print("Fırat", "Özgül", sep=" ", end="\n", file=sys.stdout, flush=False)
```

Yani biz görmesek de aslında her print() çağrısı sep, end, file ve flush parametrelerini de içeriyor. Biz bu özel parametreleri kullanmasak da, yazdığımız kod düzgün bir şekilde çalışır. Bunun nedeni, sep, end, file ve flush parametrelerinin öntanımlı olarak birtakım değerlere sahip olmasıdır. Yani biz bu parametrelere kendimiz bir değer atamazsak Python bu parametrelere kendi belirlediği bazı öntanımlı değerleri atayacaktır. Dolayısıyla, eğer biz başka bir değer yazmazsak, sep parametresi ” “ değerine, end parametresi “n” değerine, file parametresi sys.stdout değerine, flush parametresi ise False değerine sahip olacaktır. İşte bu tür parametrelere Python’da ‘varsayılan değerli parametreler’ adı verilir. Peki biz kendimiz varsayılan değerli parametreler içeren fonksiyonları nasıl tanımlayabiliriz?

Şu örneğe dikkatlice bakın:

```python
def kur(kurulum_dizini="/usr/bin/"):
    print("Program {} dizinine kuruldu!".format(kurulum_dizini))
```

Burada kur() adlı bir fonksiyon tanımladık. Bu fonksiyonun görevi, yazdığımız bir programı, kullanıcının bilgisayarındaki bir dizine kurmak ve programın hangi dizine kurulduğu konusunda kullanıcıyı bilgilendirmek. Bu fonksiyonu şu şekilde çağırabiliriz:

```python
kur()
```

Eğer kur() fonksiyonunu böyle çağırırsak bize şu çıktıyı verecektir:

```python
Program /usr/bin/ dizinine kuruldu!
```

Gördüğünüz gibi, kur() fonksiyonunun kurulum_dizini adlı bir parametresi var. Biz fonksiyonu tanımlarken, bu parametreye bir varsayılan değer atadık (/usr/bin/). Böylece kur() fonksiyonu parametresiz olarak çağrıldığında bu varsayılan değer devreye girdi.

### Rastgele Sayıda İsimsiz Parametre Belirleme

Bir örnek üzerinden fonksiyonların rastgele sayıda isimsiz parametre alma durumuna bakalım.

```python
def fonksiyon(*parametreler):
    print(parametreler)
fonksiyon(1, 2, 3, 4, 5)
```

Bu kodları çalıştırdığımızda şu çıktıyı alacağız:

```python
(1, 2, 3, 4, 5)
```

Gördüğünüz gibi, fonksiyon tanımı içinde kullandığımız * işareti sayesinde fonksiyonumuzun pratik olarak sınırsız sayıda parametre kabul etmesini sağlayabiliyoruz. Bu arada, bu tür fonksiyonların alabileceği parametre sayısı, dediğimiz gibi, pratikte sınırsızdır, ama teknik olarak bu sayı 256 adedi geçemez.

Peki böyle bir fonksiyon tanımlamak ne işimize yarar?

Mesela bu yapıyı kullanarak şöyle bir fonksiyon yazabilirsiniz:

```python

def carp(*sayilar): 
    sonuc = 1
    for i in sayilar: 
        sonuc *= i
    print(sonuc)
    
```

Bu fonksiyon kendisine verilen bütün parametreleri birbiriyle çarpar. Örneğin:

```python
carp(1, 2, 3, 4)
```

Bu kodun çıktısı 24 olacaktır. Gördüğünüz gibi, fonksiyonumuza istediğimiz sayıda parametre
vererek bu sayıların birbiriyle çarpılmasını sağlayabiliyoruz.

Elbette * işaretiyle birlikte kullanacağınız parametrenin adı olarak, Python’ın değişken adlandırma kurallarına uygun bütün kelimeleri belirleyebilirsiniz. Mesela biz yukarıda **parametreler** adını tercih ettik. Ama Python dünyasında * işaretiyle birlikte kullanılacak parametrenin adı geleneksel olarak, **argümanlar** anlamında **args**'tır. 

Yani Python programcıları genellikle yukarıdaki gibi bir fonksiyonu şöyle tanımlar:

```python
 def fonksiyon(*args): 
        ...
```

***** işareti ile birlikte kullanılacak parametrenin adını **args** yapmak bir zorunluluk olmamakla birlikte, başka Python programcılarının kodlarınızı daha kolay anlayabilmesi açısından bu geleneği devam ettirmenizi tavsiye ederim. Yazdığımız kodlarda Python programlama dilinin geleneklerine bağlı kalmak çoğunlukla iyi bir alışkanlıktır.

### Rastgele Sayıda İsimli Parametre Belirleme

Bir önceki bölümde oluduğu gibi, rastgele sayıda **isimli** parametre belirlemek de mümkündür.

Örneğin:

```python
def fonksiyon(**parametreler):
    print(parametreler)
    
fonksiyon(isim="Ahmet", soyisim="Öz", meslek="Mühendis", sehir="Ankara")
```

Bu kodları çalıştırdığımızda şöyle bir çıktı alıyoruz:

```python
{'sehir': 'Ankara', 'isim': 'Ahmet', 'soyisim': 'Öz', 'meslek': 'Mühendis'}
```

Gördüğünüz gibi, fonksiyonu tanımlarken parametremizin sol tarafına yerleştirdiğimiz ** işareti, bu fonksiyonu çağırırken yazdığımız isimli parametrelerin bize bir sözlük olarak verilmesini sağlıyor. Bu yapının bize bir sözlük verdiğini bildikten sonra, bunu sözlük veri tipinin kuralları çerçevesinde istediğimiz şekilde kullanabiliriz.

Tıpkı ***** işaretlerinin betimlediği parametrenin geleneksel olarak **args** şeklinde adlandırılması gibi, ** işaretlerinin betimlediği parametre de geleneksel olarak **kwargs** şeklinde adlandırılır. Dolayısıyla yukarıdaki gibi bir fonksiyonu Python programcıları şöyle tanımlar:

```python
def kayıt_olustur(**kwargs):
    ...
```

** işaretli parametreler pek çok farklı durumda işinize yarayabilir veya işinizi kolaylaştırabilir. Mesela * ve ** işaretlerini kullanarak şöyle bir program yazabilirsiniz:

```python
def karşılık_bul(*args, **kwargs): 
    for sözcük in args:
        if sözcük in kwargs:
            print("{} = {}".format(sözcük, kwargs[sözcük]))
        else:
            print("{} kelimesi sözlükte yok!".format(sözcük))

            
sözlük = {"kitap" : "book", 
          "bilgisayar" : "computer",
          "programlama": "programming"}

karşılık_bul("kitap", "bilgisayar", "programlama", "fonksiyon", **sözlük)
```

Burada tanımladığımız karşılık_bul() adlı fonksiyon, kendisine verilen parametreleri (*args), bir sözlük içinde arayarak (***sözlük) karşılıklarını bize çıktı olarak veriyor. Eğer verilen parametre sözlükte yoksa, ilgili kelimenin sözlükte bulunmadığı konusunda da bizi bilgilendiriyor.

karşılık_bul() adlı fonksiyonu nasıl tanımladığımıza çok dikkat edin. Parametre listesi içinde belirttiğimiz *args ifadesi sayesinde, fonksiyonu kullanacak kişiye, istediği sayıda isimsiz parametre girme imkanı tanıyoruz. ***kwargs parametresi ise kullanıcıya istediği sayıda isimli parametre girme olanağı veriyor.

### return Deyimi

Bu bölümde return adlı bir deyimden söz edeceğiz. Öncelikle basit bir örnek verelim:

```python
def ismin_ne():
    isim = input("ismin ne? ") 
    print(isim)
```

ismin_ne() adlı fonksiyonun tek görevi kullanıcıdan aldığı isim bilgisini ekrana basmaktır. Peki bu fonksiyonu bir de şöyle tanımlayalım:

```python
def ismin_ne():
    isim = input("ismin ne? ")
    return isim
```

Şimdi de bu fonksiyonu çağıralım:

```python
ismin_ne()
```

Gördüğünüz gibi, fonksiyonu çağırdığımızda yalnızca fonksiyon gövdesindeki input() fonksiyonu çalıştı, ama bu fonksiyondan gelen veri ekrana çıktı olarak verilmedi. Çünkü biz burada herhangi bir ekrana basma (‘print’) işlemi yapmadık. Yaptığımız tek şey isim adlı değişkeni ‘döndürmek’.

Peki bu ne anlama geliyor?

return kelimesi İngilizcede ‘iade etmek, geri vermek, döndürmek’ gibi anlamlar taşır. İşte yukarıdaki örnekte de return deyiminin yaptığı iş budur. Yani bu deyim bize fonksiyondan bir değer ‘döndürür’.

Eğer tanımladığımız bir fonksiyonda return deyimini kullanarak herhangi bir değer döndürmezsek, Python fonksiyondan hususi bir değerin döndürülmediğini göstermek için ‘None’ adlı bir değer döndürür... İşte yukarıda tanımladığımız ilk ismin_ne() fonksiyonunu print(ismin_ne()) şeklinde çağırdığımızda ekranda None değerinin görünmesinin nedeni budur.

Peki bir fonksiyon içinde herhangi bir veriyi ekrana basmayıp return deyimi yardımıyla döndürmemizin bize ne faydası var?

Aslında bunun cevabı çok açık. Bir fonksiyon içinde bir değeri döndürmek yerine ekrana bastığınızda o fonksiyonun işlevini alabildiğine kısıtlamış oluyorsunuz. Fonksiyonunuzun tek işlevi bir değeri ekrana basmak oluyor.

Yukarıda tanımladığımız ismin_ne() fonksiyonu şu şekilde çağıralım:

```python
print("Merhaba {}. Nasılsın?".format(ismin_ne()))
```

Çıktımız şu şekilde olacaktır:

```
ismin ne? Fırat
Merhaba Fırat. Nasılsın?
```

Geriye değer döndüren fonksiyonlarda, fonksiyonun geriye döndürmüş olduğu değeri istediğimiz şekilde kullanabiliriz.

return deyimiyle ilgili son bir şey daha söyleyelim...

Bu deyim, içinde bulunduğu fonksiyonun çalışma sürecini kesintiye uğratır. Yani return deyimini kullandığınız satırdan sonra gelen hiçbir kod çalışmaz. Basit bir örnek verelim:

```python
def fonk():
    print(3)
    return
    print(5)
    
fonk()
```

Bu kodları çalıştırdığınızda yalnızca print(3) satırının çalıştığını, print(5) satırına ise hiç ulaşılmadığını göreceksiniz. İşte bu durumun sebebi, Python’ın kodları return satırından itibaren okumayı bırakmasıdır.

## Fonksiyonların Kapsamı ve global Deyimi

Elimizde şöyle bir kod olduğunu düşünelim:

```python
x = 0

def fonk(): 
    x = 1
    return x
```

Bu kodlarda, fonksiyonun dışında x adlı bir değişken var. Fonksiyonun içinde de yine x adını taşıyan başka bir değişken var. Fonksiyonumuzun görevi bu x değişkenini döndürmek.

Bu noktada size şöyle bir soru sormama izin verin: Acaba fonksiyon içinde tanımladığımız x değişkeni, fonksiyon dışındaki x değişkeninin değerini değiştiriyor mu? Bu sorunun cevabını şu kodlarla verelim:

```python

x = 0

def fonk(): 
    x=1
    return x

print('fonksiyon içindeki x: ', fonk())
print('fonksiyon dışındaki x: ', x)

```

Bu kodları çalıştırdığımızda şu çıktıyı alacağız:

```
fonksiyon içindeki x:  1
fonksiyon dışındaki x:  0
```

Gördüğünüz gibi fonksiyon içindeki ve fonksiyon dışındaki aynı adlı değişkenler birbirine karışmıyor. Bunun sebebi, Python’daki ‘isim alanı’ (namespace ) adlı bir kavramdır.

Peki isim alanı ne demek?

Python’da değişkenlerin, fonksiyonların ve daha sonra göreceğiniz gibi sınıfların bir kapsamı vardır. Bu kapsama Python’da ‘isim alanı’ adı verilir. Dolayısıyla Python’da her nesnenin, geçerli ve etkin olduğu bir isim alanı bulunur. Örneğin yukarıdaki kodlarda fonksiyon dışındaki x değişkeni ana isim alanında yer alan ‘global’ bir değişkendir. Fonksiyon içindeki x değişkeni ise fonk() değişkeninin isim alanı içinde yer alan ‘lokal’ bir değişkendir. Bu iki değişken, adları aynı da olsa, birbirlerinden farklı iki nesnedir.

Bir de şu örneğe bakalım:

```python
x = []
print('x\'in ilk hali:', x)

def değiştir():
    print('x\'i değiştiriyoruz...') x.append(1)
    return x

değiştir()
print('x\'in son hali: ', x)
```

Burada ise daha farklı bir durum söz konusu. Fonksiyon içinde append() metodunu kullanarak yaptığımız ekleme işlemi fonksiyon dışındaki listeyi de etkiledi. Peki ama bu nasıl oluyor?

Python herhangi bir nesneye göndermede bulunduğumuzda, yani o nesnenin değerini talep ettiğimizde aradığımız nesneyi ilk önce mevcut isim alanı içinde arar. Eğer aranan nesneyi mevcut isim alanı içinde bulamazsa yukarıya doğru bütün isim alanlarını tek tek kontrol eder.

İşte Python programlama dili çözüm olacak bir araç sunar bize. Bu aracın adı **global.**

Gelin isterseniz bu **global** adlı deyimin nasıl kullanılacağına bakalım önce... 

Şu kodların hata vereceğini biliyorsunuz:

```python
isim = 'Fırat'

def fonk():
    isim += ' Özgül'
    return isim

print(fonk())
```

Ama bu kodlara şöyle bir ekleme yaparsanız işler değişir:

```python
isim = 'Fırat'

def fonk():
    global isim
    isim += ' Özgül'
    return isim

print(fonk())
```

Burada fonk() adlı fonksiyonun ilk satırında şöyle bir kod görüyoruz:

```python
global isim
```

İşte bu satır, isim adlı değişkenin global alana taşınmasını sağlıyor. Böylece global alanda
bulunan isim adlı değişkeni değişikliğe uğratabiliyoruz.

global deyimi her ne kadar ilk bakışta çok faydalı bir araçmış gibi görünse de aslında programlarımızda genellikle bu deyimi kullanmaktan kaçınmamız iyi bir fikir olacaktır. Çünkü bu deyim aslında global alanı kirletmemize neden oluyor. Global değişkenlerin lokal isim alanlarında değişikliğe uğratılması, eğer dikkatsiz davranırsanız programlarınızın hatalı çalışmasına yol açabilir

> Son Güncelleme: 25 Aralık 2019 - Çarşamba
