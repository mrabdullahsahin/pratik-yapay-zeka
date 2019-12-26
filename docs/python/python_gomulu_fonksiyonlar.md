## Gömülü Fonksiyonlar

### abs()

abs() fonksiyonunu bir sayının mutlak değerini elde etmek için kullanıyoruz. Örneğin:


```python
abs(-20)
```




    20



bir başka örnek:


```python
abs(20)
```




    20



bir diğer örnek:


```python
abs(20.0)
```




    20.0



Mutlak değer kavramı yalnızca tamsayılar ve kayan noktalı sayılar için değil, aynı zamanda karmaşık sayılar için de geçerlidir. Dolayısıyla abs() fonksiyonunu kullanarak karmaşık sayıların da mutlak değerini hesaplayabiliriz:


```python
abs(20+3j)
```




    20.223748416156685



### round()

round() fonksiyonu bir sayıyı belli ölçütlere göre yukarı veya aşağı doğru yuvarlamamızı sağlar. Basit birkaç örnek verelim:


```python
round(12.4)
```




    12



burada dikkat etmemiz gereken bir nokta var.

Şu örnekleri bir inceleyelim:


```python
round(1.5)
```




    2




```python
round(12.5)
```




    12



Gördüğünüz gibi, fonksiyonumuz 1.5 sayısını yukarı doğru, 12.5 sayısını ise aşağı doğru yuvarladı. Bunun sebebi, kayan noktalı bir sayının üst ve alt tam sayılara olan uzaklığının birbirine eşit olduğu durumlarda Python’ın çift sayıya doğru yuvarlama yapmayı tercih etmesidir. Mesela yukarıdaki örneklerde 1.5 sayısı hem 1 sayısına, hem de 2 sayısına eşit uzaklıkta bulunuyor. İşte Python bu durumda, bir çift sayı olan 2 sayısına doğru yuvarlamayı tercih edecektir.

round() fonksiyonu toplam iki parametre alır. İlk parametre, yuvarlanacak sayının kendisidir. Yuvarlama hassasiyetini belirlemek için ise ikinci bir parametreden yararlanabiliriz.

Örneğin 22 sayısını 7 ‘ye böldüğümüzde normalde şöyle bir çıktı elde ederiz:


```python
22/7
```




    3.142857142857143



round() fonksiyonunu tek parametre ile kullandığımızda bu fonksiyon yukarıdaki sayıyı şu şekilde yuvarlayacaktır:


```python
round(22/7)
```




    3



İşte biz round() fonksiyonuna ikinci bir parametre daha vererek, yuvarlama hassasiyetini kontrol edebiliriz.

Aşağıdaki örnekleri dikkatlice inceleyin:


```python
print("round(22/7): ",round(22/7))

print("round(22/7, 0): ",round(22/7, 0))

print("round(22/7, 1): ",round(22/7, 1))

print("round(22/7, 2): ",round(22/7, 2))

print("round(22/7, 3): ",round(22/7, 3))

print("round(22/7, 4): ",round(22/7, 4))
```

    round(22/7):  3
    round(22/7, 0):  3.0
    round(22/7, 1):  3.1
    round(22/7, 2):  3.14
    round(22/7, 3):  3.143
    round(22/7, 4):  3.1429


Gördüğünüz gibi, round() fonksiyonuna verdiğimiz ikinci parametre, yuvarlama işleminin ne kadar hassas olacağını belirliyor.

### all()

all() fonksiyonunun görevi, bir dizi içinde bulunan bütün değerler True ise True değeri, eğer bu değerlerden herhangi biri False ise de False değeri döndürmektir.

Örneğin elimizde şöyle bir liste olduğunu varsayalım:


```python
liste = [1, 2, 3, 4]

all(liste)
```




    True



Bildiğiniz gibi, 0 hariç bütün sayıların bool değeri True‘dur. Yukarıdaki listede False değeri verebilecek herhangi bir değer bulunmadığından, all() fonksiyonu bu liste için True değerini veriyor. Bir de şuna bakalım:


```python
liste = [0, 1, 2, 3, 4]

all(liste)
```




    False



Son bir örnek daha verelim:


```python
liste = ['ahmet', 'mehmet', '']

all(liste)
```




    False



Listede False değerine sahip bir boş karakter dizisi bulunduğu için all() fonksiyonu False çıktısı veriyor.

### any()

any() fonksiyonunun görevi de, bir dizi içindeki bütün değerlerden en az biri True ise True çıktısı vermektir.


```python
liste = ['ahmet', 'mehmet', '']

any(liste)
```




    True



any() fonksiyonunun True çıktısı verebilmesi için listede yalnızca bir adet True değerli öğe olması yeterlidir. Bu fonksiyonun False çıktısı verebilmesi için dizi içindeki bütün öğelerin bool değerinin False olması gerekir:


```python
l = ['', 0, [], (), set(), dict()]

any(l)
```




    False



### ascii()

Bu fonksiyon, bir nesnenin ekrana basılabilir halini verir bize.


```python
a = 'python'

print(ascii(a))
```

    'python'


Bu fonksiyonun, print() fonksiyonundan farklı olarak, çıktıya tırnak işaretlerini de eklediğine dikkat edin.

ascii() fonksiyonunun tam olarak ne yaptığını daha iyi anlamak için herhalde şu örnek daha faydalı olacaktır.

Dikkatlice bakın:


```python
print('\n')
```

    
    


Bu komutu verdiğimizde, n kaçış dizisinin etkisiyle yeni satıra geçileceğini biliyorsunuz.

Bir de şuna bakın:


```python
print(ascii('\n!'))
```

    '\n!'


Gördüğünüz gibi, ascii() fonksiyonu, satır başı kaçış dizisinin görevini yapmasını sağlamak yerine bu kaçış dizisinin ekrana basılabilir halini veriyor bize.

Ayrıca bu fonksiyon, karakter dizileri içindeki Türkçe karakterlerin de UNICODE temsillerini döndürür. Örneğin:


```python
a = 'ışık'

print(ascii(a))
```

    '\u0131\u015f\u0131k'


### repr()

repr() fonksiyonunun yaptığı iş, biraz önce gördüğümüz ascii() fonksiyonunun yaptığı işe çok benzer. Bu iki fonksiyon, ASCII olmayan karakterlere muameleleri açısından birbirinden ayrılır.

Hatırlarsanız ascii() fonksiyonu ASCII olmayan karakterlerle karşılaştığında bunların UNICODE (veya onaltılık) temsillerini gösteriyordu:


```python
ascii('şeker')
```




    "'\\u015feker'"



repr() fonksiyonu ise ASCII olmayan karakterlerle karşılaşsa bile, bize çıktı olarak bunların da karakter karşılıklarını gösterir:


```python
repr('şeker')
```




    "'şeker'"



### bool()

Bu fonksiyon bir nesnenin bool değerini verir:


```python
print("bool(0): ",bool(0))

print("bool(1): ",bool(1))

print("bool([]): ",bool([]))
```

    bool(0):  False
    bool(1):  True
    bool([]):  False


### bin()

Bu fonksiyon, bir sayının ikili düzendeki karşılığını verir:


```python
bin(12)
```




    '0b1100'



Bu fonksiyonun verdiği çıktının bir sayı değil, karakter dizisi olduğuna dikkat etmelisiniz.

### bytes()

Bu fonksiyon bytes türünde nesneler oluşturmak için kullanılır.

Bu fonksiyon, kendisine verilen parametrelerin türüne bağlı olarak birbirinden farklı sonuçlar ortaya çıkarır. Örneğin eğer bu fonksiyona parametre olarak bir tam sayı verecek olursanız, bu fonksiyon size o tam sayı miktarınca bir bayt nesnesi verecektir. Gelin isterseniz bu durumu örnekler üzerinde göstermeye çalışalım:


```python
bytes(10)
```




    b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'



Yukarıdaki komut bize, her bir öğesinin değeri 0 olan 10 baytlık bir veri döndürdü:


```python
a = bytes(10)

a
```




    b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'




```python
print(a[0])
print(a[1])
print(a[2])
```

    0
    0
    0


Gördüğünüz gibi, bytes(10) komutuyla oluşturduğumuz a değişkeni içinde toplam 10 adet bayt var ve bu baytların her birinin değeri 0.

Yukarıda, bytes() fonksiyonuna bir tam sayı değerli parametre verdiğimizde nasıl bir sonuç alacağımızı öğrendik. Peki biz bu fonksiyona parametre olarak bir karakter dizisi verirsek ne olur?

Hemen görelim:


```python
bytes("python")
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-29-0f3b72b3b524> in <module>
    ----> 1 bytes("python")
    

    TypeError: string argument without an encoding


Bu fonksiyona karakter dizilerini doğrudan parametre olarak veremeyiz.

bayta dönüştürme işlemi her kod çözücü tarafından farklı biçimde yapılır. Örneğin:


```python
'ışık'.encode('utf-8')
```




    b'\xc4\xb1\xc5\x9f\xc4\xb1k'




```python
'ışık'.encode('cp857')
```




    b'\x8d\x9f\x8dk'




```python
'ışık'.encode('cp1254')
```




    b'\xfd\xfe\xfdk'



Dolayısıyla, bytes() fonksiyonunun bir karakter dizisini bayta çevirirken nasıl davranması gerektiğini anlayabilmesi için, bayta dönüştürme işlemini hangi kod çözücü ile yapmak istediğimizi açıkça belirtmemiz gerekir:


```python
bytes('ışık', 'utf-8')
```




    b'\xc4\xb1\xc5\x9f\xc4\xb1k'




```python
bytes('ışık', 'cp1254')
```




    b'\xfd\xfe\xfdk'



Bu arada, çıktıda görünen ‘b’ harflerinin, elimizdeki verinin bir bayt olduğunu gösteren bir işaret olduğunu biliyorsunuz.

Ayrıca, bytes() fonksiyonuna verdiğimiz ikinci parametrenin isminin encoding olduğunu ve bu parametreyi isimli bir parametre olarak da kullanabileceğimizi belirtelim:


```python
bytes('python', encoding='ascii')
```




    b'python'




```python
bytes('şeker', 'ascii')
```


    ---------------------------------------------------------------------------

    UnicodeEncodeError                        Traceback (most recent call last)

    <ipython-input-37-71877b66453f> in <module>
    ----> 1 bytes('şeker', 'ascii')
    

    UnicodeEncodeError: 'ascii' codec can't encode character '\u015f' in position 0: ordinal not in range(128)


‘ş’ harfi ‘ASCII’ karakter kümesinde; ‘€’ işareti ise ‘CP857’ adlı karakter kümesinde tanımlanmamış birer karakter olduğu için, ilgili kod çözücüler bu karakterleri çözüp bayta dönüştüremiyor. Yazdığımız kodların bu tür durumlarda tamamen çökmesini engellemek için, önceki derslerimizde de çeşitli vesilelerle öğrenmiş olduğumuz errors adlı bir parametreden yararlanabiliriz:


```python
bytes('şeker', encoding='ascii', errors='replace')
```




    b'?eker'



Son olarak, bytes() fonksiyonuna parametre olarak 0-256 arası sayılardan oluşan diziler de verebiliriz:


```python
bytes([65, 10, 12, 11, 15, 66])
```




    b'A\n\x0c\x0b\x0fB'



### bytearray()

bytearray() ve bytes() fonksiyonları birbirlerine çok benzer. Bu ikisi arasındaki tek fark, bytearray() ile oluşturulan veri tipinin, bytes() ile oluşturulan veri tipinin aksine, değiştirilebilir nitelikte olmasıdır:


```python
a = bytearray('konya', 'ascii')

a
```




    bytearray(b'konya')




```python
bytearray(b'konya')
```




    bytearray(b'konya')




```python
a[0] = 65

a
```




    bytearray(b'Aonya')



### chr()

Bu fonksiyon, kendisine parametre olarak verilen bir tam sayının karakter karşılığını döndürür. Örneğin:


```python
chr(10)
```




    '\n'



Bildiğiniz gibi 10 sayısının karakter karşılığı satır başı karakteridir. Bir de şuna bakalım:


```python
chr(65)
```




    'A'



65 sayısının karakter karşılığı ise ‘A’ harfidir.

Bu fonksiyon sayıları karakterlere dönüştürürken ASCII sistemini değil, UNICODE sistemini temel alır. Dolayısıyla bu fonksiyon ile 128 (veya 255) üstü sayıları da dönüştürebiliriz. Örneğin:


```python
chr(305)
```




    'ı'



### list()

Bu fonksiyon iki farklı amaç için kullanılabilir:

1. Liste tipinde bir veri oluşturmak
2. Farklı veri tiplerini liste adlı veri tipine dönüştürmek

Birinci amaç için bu fonksiyonu şu şekilde kullanıyoruz:


```python
l = list()
```

ikinc amaç için bu fonksiyonu şu şekilde kullanıyoruz:


```python
liste = list('python')

liste
```




    ['p', 'y', 't', 'h', 'o', 'n']



Elbette bu fonksiyonu kullanarak başka veri tiplerini de listeye dönüştürebiliriz. Örneğin bir
sözlüğü, bu fonksiyon yardımıyla kolayca listeye dönüştürebiliriz:


```python
s = {'elma': 44, 'armut': 10, 'erik': 100}

list(s)
```




    ['elma', 'armut', 'erik']



Bir sözlük listeye dönüştürülürken, elbette sözlüğün anahtarları dikkate alınacaktır. Eğer siz sözlüğün anahtarlarından değil de değerlerinde bir liste oluşturmak isterseniz şöyle bir kod yazabilirsiniz:


```python
list(s.values())
```




    [44, 10, 100]



### set()

set() fonksiyonu list() fonksiyonuna çok benzer. Bu fonksiyon da tıpkı list() fonksiyonu gibi, veri tipleri arasında dönüştürme işlemleri gerçekleştirmek için kullanılabilir. set() fonksiyonunun görevi farklı veri tiplerini kümeye dönüştürmektir:


```python
k = set()
```

Burada boş bir küme oluşturduk. Şimdi de mesela bir karakter dizisini kümeye dönüştürelim:


```python
i = 'python'

set(i)
```




    {'h', 'n', 'o', 'p', 't', 'y'}



### tuple()

tuple() fonksiyonu da, tıpkı list(), set() ve benzerleri gibi bir dönüştürücü fonksiyondur. Bu fonksiyon farklı veri tiplerini demete dönüştürür:


```python
tuple('a')
```




    ('a',)



### frozenset()

Bu fonksiyonu kullanarak farklı veri tiplerini dondurulmuş kümeye dönüştürebilirsiniz:


```python
s = set('istihza')

df = frozenset(s)

df
```




    frozenset({'a', 'h', 'i', 's', 't', 'z'})



### complex()

Karmaşık sayılar Python’da ‘complex’ ifadesiyle gösteriliyor. Mesela şu bir karmaşık sayıdır:


```python
12+0j
```




    (12+0j)



İşte eğer herhangi bir sayıyı karmaşık sayıya dönüştürmeniz gerekirse complex() adlı bir fonksiyondan yararlanabilirsiniz. Örneğin:


```python
complex(15)
```




    (15+0j)



Böyle bir kod yazdığımızda, verdiğimiz parametre karmaşık sayının gerçek kısmını oluşturacak, sanal kısım ise 0 olarak kabul edilecektir. Elbette isterseniz sanal kısmı kendiniz de belirleyebilirsiniz:


```python
complex(15, 2)
```




    (15+2j)



### float()

Bu fonksiyonu, sayıları veya karakter dizilerini kayan noktalı sayıya dönüştürmek için kullanıyoruz:


```python
float('134')
```




    134.0



### int()

Bu fonksiyon birkaç farklı amaç için kullanılabilir. int() fonksiyonunun en temel görevi, bir karakter dizisi veya kayan noktalı sayıyı (eğer mümkünse) tam sayıya dönüştürmektir:


```python
int('10')
```




    10




```python
int(12.4)
```




    12



Bunun dışında bu fonksiyonu, herhangi bir sayma sisteminde temsil edilen bir sayıyı onlu sayma sistemine dönüştürmek için de kullanabiliriz. Örneğin:


```python
int('12', 8)
```




    10



Burada, sekizli sayma sistemine ait sayı değerli bir karakter dizisi olan ‘12’‘yi onlu sayma sistemine dönüştürdük ve böylece ‘10 sayısını elde ettik.

int() fonksiyonunu sayma sistemleri arasında dönüştürme işlemlerinde kullanabilmek için ilk parametrenin bir karakter dizisi olması gerektiğine dikkat ediyoruz.

Bu arada, int(’12’, 8) komutununun 12 sayısını sekizli sayma sistemine dönüştürmediğine dikkat edin. Bu komutun yaptığı iş sekizli sayma sistemindeki 12 sayısını onlu sayma sistemine dönüştürmektir.

int() fonksiyonunun bu kullanımıyla ilgili bir örnek daha verelim:


```python
int('4cf', 16)
```




    1231



Burada da, onaltılı sayma sistemine ait bir sayı olan 4cf‘yi onlu sayma sistemine çevirdik ve 1231 sayısını elde ettik. 4cf sayısını int() fonksiyonuna parametre olarak verirken bunu karakter dizisi şeklinde yazmayı unutmuyoruz. Aksi halde Python bize bir hata mesajı gösterecektir.

### str()

Bu fonksiyonun, farklı veri tiplerini karakter dizisine dönüştürmek için kullanıldığını biliyorsunuz. Örneğin:


```python
str(12)
```




    '12'



Burada 12 sayısını bir karakter dizisine dönüştürdük. Şimdi de bir baytı karakter dizisine dönüştürelim:


```python
bayt = b'python'
```

Bayt nesnemizi tanımladık. Şimdi bunu bir karakter dizisine dönüştürelim:


```python
kardiz = str(bayt, encoding='utf-8')

print(kardiz)
```

    python


### dict()

Bu fonksiyon, farklı veri tiplerinden sözlükler üretmemizi sağlar. Örneğin bu fonksiyonu kullanarak boş bir sözlük oluşturabiliriz:


```python
s = dict()
```

Bu fonksiyon, değişkenlerden sözlükler oluşturmamızı da sağlar:


```python
s = dict(a=1, b=2, c=3)

s
```




    {'a': 1, 'b': 2, 'c': 3}



dict() fonksiyonuna parametre olarak iç içe geçmiş listeler veya demetler vererek de sözlük üretebiliriz:


```python
ogeler = (['a', 1], ['b', 2], ['c', 3])

dict(ogeler)
```




    {'a': 1, 'b': 2, 'c': 3}



### callable()

Bu fonksiyon, bir nesnenin ‘çağrılabilir’ olup olmadığını denetler. Peki hangi nesneler çağrılabilir özelliktedir. Mesela fonksiyonlar çağrılabilir nesnelerdir. Değişkenler ise çağrılabilir nesneler değildir.

Birkaç örnek verelim bununla ilgili:


```python
callable(open)
```




    True



Python’ın open() adlı bir fonksiyonu olduğu için, doğal olarak callable() fonksiyonu True çıktısı veriyor.

Bir de şuna bakalım:


```python
import sys

callable(sys.version)
```




    False



Burada da sys modülü içindeki version adlı nesnenin çağrılabilir özellikte olup olmadığını sorguladık. Daha önceki derslerimizde de gördüğünüz gibi, sys modülü içindeki version adlı araç bir fonksiyon değil, değişkendir. Dolayısıyla bu değişken callable(sys.version) sorgusuna False yanıtı verir.

### ord()

u fonksiyon, bir karakterin karşılık geldiği ondalık sayıyı verir. Örneğin:


```python
ord('a')
```




    97




```python
ord('ı')
```




    305



### oct()

Bu fonksiyon, bir sayıyı sekizli düzendeki karşılığına çevirmemizi sağlar:


```python
oct(10)
```




    '0o12'



### hex()

Bu fonksiyon, bir sayıyı onaltılı düzendeki karşılığına çevirmemizi sağlar:


```python
hex(305)
```




    '0x131'



Yalnız hem oct() hem de hex() fonksiyonlarında dikkat etmemiz gereken şey, bu fonksiyonların parametre olarak bir sayı alıp, çıktı olarak bir karakter dizisi veriyor olmasıdır.

### eval(), exec(), globals(), locals(), compile()

Bu bölümde beş farklı fonksiyonu bir arada inceleyeceğiz. Bu fonksiyonları birlikte ele almamızın nedeni bunların birbiriyle yakından bağlantılı olması.
Burada işleyeceğimiz bu beş fonksiyon şunlardan oluşuyor: 

1. eval()
2. exec()
3. globals() 
4. locals() 
5. compile()

Ancak bu fonksiyonlardan söz etmeye başlamadan önce Python’daki iki önemli kavramı açıklığa kavuşturmamız gerekiyor: Bu kavramlar şunlar:

1. ifade
2. deyim

Öncelikle ‘ifade’ kavramından başlayalım.

İngilizcede expression denen ‘ifadeler’, bir değer üretmek için kullanılan kod parçalarıdır. Karakter dizileri, sayılar, işleçler, öteki veri tipleri, liste üreteçleri, sözlük üreteçleri, küme üreteçleri, fonksiyonlar hep birer ifadedir.

Örneğin:


```python
5
```




    5




```python
23 + 4
```




    27




```python
len([1, 2, 3])
```




    3



İngilizcede statement olarak adlandırılan ‘deyimler’ ise ifadeleri de kapsayan daha geniş bir kavramdır. Buna göre bütün ifadeler aynı zamanda birer deyimdir. Daha doğrusu, ifadelerin bir araya gelmesi ile deyimler oluşturulabilir.

Deyimlere birkaç örnek verelim:


```python
a = 5
```


```python
if a:
    print(a)
```

    5


Python programlama dilinde deyimlerle ifadeleri ayırt etmenin kolay bir yolu da eval() fonksiyonundan yararlanmaktır. Eğer deyim mi yoksa ifade mi olduğundan emin olamadığınız bir şeyi eval() fonksiyonuna parametre olarak verdiğinizde hata almıyorsanız o parametre bir ifadedir. Eğer hata alıyorsanız o parametre bir deyimdir. Çünkü eval() fonksiyonuna parametre olarak yalnızca ifadeler verilebilir.

Birkaç örnek verelim:


```python
eval('a = 5')
```


    Traceback (most recent call last):


      File "/opt/anaconda3/lib/python3.7/site-packages/IPython/core/interactiveshell.py", line 3326, in run_code
        exec(code_obj, self.user_global_ns, self.user_ns)


      File "<ipython-input-85-2f07a5f3d91b>", line 1, in <module>
        eval('a = 5')


      File "<string>", line 1
        a = 5
          ^
    SyntaxError: invalid syntax



Gördüğünüz gibi, eval() fonksiyonu bize bir hata mesajı verdi. Çünkü a = 5 kodu bir deyimdir. Unutmayın, Python’da bütün değer atama işlemleri birer deyimdir. Dolayısıyla eval() fonksiyonu bu deyimi parametre olarak alamaz.

Bir de şuna bakalım:


```python
eval('5 + 25')
```




    30



Bu defa hata almadık. Çünkü eval() fonksiyonuna, olması gerektiği gibi, parametre olarak bir ifade verdik. Bildiğiniz gibi, 5 + 25 kodu bir ifadedir.

Dediğimiz gibi, eval() fonksiyonu deyimleri parametre olarak alamaz. Ama exec() fonksiyonu alabilir:


```python
exec('a = 5')
```

Bu şekilde, değeri 5 olan a adlı bir değişken oluşturmuş olduk. İsterseniz kontrol edelim:


```python
print(a)
```

    5


Gördüğünüz gibi, exec() fonksiyonu, mevcut isim alanı içinde a adlı bir değişken oluşturdu. Yalnız elbette mevcut isim alanı içinde yeni değişkenler ve yeni değerler oluştururken dikkatli olmamız gerektiğini biliyorsunuz. Zira mesela yukarıdaki komutu vermeden önce mevcut isim alanında zaten a adlı bir değişken varsa, o değişkenin değeri değişecektir:


```python
a = 20
```

Elimizde, değeri 20 olan a adlı bir değişken var. Şimdi exec() fonksiyonu yardımıyla a değişkeninin de içinde yer aldığı mevcut isim alanına müdahale ediyoruz:


```python
exec('a = 10')
```

Böylece a değişkeninin eski değerini silmiş olduk. Kontrol edelim:


```python
print(a)
```

    10


Bu tür durumlarda, exec() ile oluşturduğunuz değişkenleri global isim alanına değil de, farklı bir isim alanına göndermeyi tercih edebilirsiniz. Peki ama bunu nasıl yapacağız?

Python programlama dilinde isim alanları sözlük tipinde bir veridir. Örneğin global isim alanı basit bir sözlükten ibarettir.

Global isim alanını gösteren sözlükte hangi anahtar ve değerlerin olduğunu görmek için globals() adlı bir fonksiyonu kullanabilirsiniz:


```python
# globals() #uzun çıktılar verdiği için çalıştırılmamıştır, sizler test etmek için çalıştırabilirsiniz.
```

```python
 {'__doc__': None, '__loader__': <class '_frozen_importlib.BuiltinImporter'>, '__name__': '__main__', '__package__': None, '__builtins__': <module 'builtins'>}
```

Gördüğünüz gibi, elimizdeki şey gerçekten de bir sözlük. Dolayısıyla bir sözlük ile ne yapabilirsek bu sözlükle de aynı şeyi yapabiliriz...

‘globals’ adlı bu sözlüğün içeriği, o anda global isim alanında bulunan nesnelere göre farklılık gösterecektir. Örneğin:


```python
x = 10
```

şeklinde 10 değerine sahip bir x nesnesi tanımladıktan sonra globals() fonksiyonunu tekrar
çalıştırırsanız global isim alanına bu nesnenin de eklenmiş olduğunu görürsünüz.

Dediğimiz gibi, globals() fonksiyonundan dönen nesne bir sözlüktür. Bu sözlüğe, herhangi bir sözlüğe veri ekler gibi değer de ekleyebilirsiniz:


```python
globals()['z'] = 23
```

Bu şekilde global isim alanına z adlı bir değişken eklemiş oldunuz:

Yalnız, Python programlama dili bize bu şekilde global isim alanına nesne ekleme imkanı verse de, biz mecbur değilsek bu yöntemi kullanmaktan kaçınmalıyız. Çünkü bu şekilde sıradışı bir yöntemle değişken tanımladığımız için aslında global isim alanını, nerden geldiğini kestirmenin güç olduğu değerlerle ‘kirletmiş’ oluyoruz.

Bildiğiniz gibi, Python’da global isim alanı dışında bir de lokal isim alanı bulunur. Lokal isim alanlarının, fonksiyonlara (ve ileride göreceğimiz gibi sınıflara) ait bir isim alanı olduğunu biliyorsunuz. İşte bu isim alanlarına ulaşmak için de locals() adlı bir fonksiyondan yararlanacağız:


```python
def fonksiyon(param1, param2): 
    x = 10
    print(locals())

fonksiyon(10, 20)
```

    {'param1': 10, 'param2': 20, 'x': 10}


Bu fonksiyonu çalıştırdığınızda şu çıktıyı alacaksınız:

Gördüğünüz gibi, locals() fonksiyonu gerçekten de bize fonksiyon() adlı fonksiyon içindeki
lokal değerleri veriyor.

globals() ve locals() fonksiyonlarının ne işe yaradığını incelediğimize göre exec() fonksiyonunu anlatırken kaldığımız yere dönebiliriz.

Ne diyorduk?

Elimizde, değeri 20 olan a adlı bir değişken vardı:


```python
a = 20
```

exec() fonksiyonu yardımıyla a değişkeninin de içinde yer aldığı mevcut isim alanına müdahale edelim:


```python
exec('a = 3')
```

Bu şekilde a değişkeninin varolan değerini silmiş olduk:


```python
print(a)
```

    3


Dediğimiz gibi, bu tür durumlarda, exec() ile oluşturduğunuz değişkenleri global isim alanı yerine farklı bir isim alanına göndermeyi tercih etmemiz daha uygun olacaktır. Python’da isim alanlarının basit bir sözlük olduğunu öğrendiğimize göre, exec() ile oluşturduğumuz değişkenleri global isim alanı yerine nasıl farklı bir isim alanına göndereceğimizi görebiliriz.

Önce yeni bir isim alanı oluşturalım:


```python
ia = {}
```

Şimdi exec() ile oluşturacağımız değerleri bu isim alanına gönderebiliriz:


```python
exec('a = 3', ia)
```

Böylece global isim alanındaki a değişkeninin değerine dokunmamış olduk:


```python
a
```




    3



Yeni oluşturduğumuz değer ise ia adlı yeni isim alanına gitti:


```python
ia['a']
```




    3



### copyright()

Bu fonksiyon yardımıyla Python’ın telif haklarına ilişkin bilgilere erişebilirsiniz:


```python
copyright()
```

    Copyright (c) 2001-2019 Python Software Foundation.
    All Rights Reserved.
    
    Copyright (c) 2000 BeOpen.com.
    All Rights Reserved.
    
    Copyright (c) 1995-2001 Corporation for National Research Initiatives.
    All Rights Reserved.
    
    Copyright (c) 1991-1995 Stichting Mathematisch Centrum, Amsterdam.
    All Rights Reserved.


### credits()

Bu fonksiyon, Python programlama diline katkıda bulunanlara teşekkür içeren küçük bir metni ekrana çıktı olarak verir:


```python
credits()
```

        Thanks to CWI, CNRI, BeOpen.com, Zope Corporation and a cast of thousands
        for supporting Python development.  See www.python.org for more information.


### license()

Bu fonksiyon yardımıyla Python’ın lisansına ilişkin epey ayrıntılı metinlere ulaşabilirsiniz.


```python
license()
```

    A. HISTORY OF THE SOFTWARE
    ==========================
    
    Python was created in the early 1990s by Guido van Rossum at Stichting
    Mathematisch Centrum (CWI, see http://www.cwi.nl) in the Netherlands
    as a successor of a language called ABC.  Guido remains Python's
    principal author, although it includes many contributions from others.
    
    In 1995, Guido continued his work on Python at the Corporation for
    National Research Initiatives (CNRI, see http://www.cnri.reston.va.us)
    in Reston, Virginia where he released several versions of the
    software.
    
    In May 2000, Guido and the Python core development team moved to
    BeOpen.com to form the BeOpen PythonLabs team.  In October of the same
    year, the PythonLabs team moved to Digital Creations, which became
    Zope Corporation.  In 2001, the Python Software Foundation (PSF, see
    https://www.python.org/psf/) was formed, a non-profit organization
    created specifically to own Python-related Intellectual Property.
    Zope Corporation was a sponsoring member of the PSF.
    
    All Python releases are Open Source (see http://www.opensource.org for
    the Open Source Definition).  Historically, most, but not all, Python
    Hit Return for more, or q (and Return) to quit: q


### dir()

Eğer dir() fonksiyonunu parametresiz olarak kullanırsak, mevcut isim alanındaki öğeleri bir liste halinde elde ederiz:


```python
# dir() #uzun çıktılar verdiği için çalıştırılmamıştır, sizler test etmek için çalıştırabilirsiniz.
```

Bu bakımdan dir() fonksiyonu globals() ve locals() fonksiyonlarına benzer. Ancak onlardan farkı, dir() fonksiyonunun çıktı olarak bir liste, globals() ve locals() fonksiyonlarının ise birer sözlük vermesidir.

Ayrıca dir() fonksiyonunu kullanarak nesnelerin metot ve niteliklerini içeren bir listeye ulaşabileceğimizi de biliyorsunuz. Örneğin bu fonksiyonu kullanarak farklı veri tiplerinin metot ve niteliklerini listeleyebiliriz:


```python
# dir('')  #uzun çıktılar verdiği için çalıştırılmamıştır, sizler test etmek için çalıştırabilirsiniz.
# dir([])  #uzun çıktılar verdiği için çalıştırılmamıştır, sizler test etmek için çalıştırabilirsiniz.
# dir({})  #uzun çıktılar verdiği için çalıştırılmamıştır, sizler test etmek için çalıştırabilirsiniz.
```

### divmod()

Bu fonksiyonun işlevini bir örnek üzerinden göstermeye çalışalım:


```python
divmod(10, 2)
```




    (5, 0)



Gördüğünüz gibi divmod(10, 2) komutu bize iki öğeli bir demet veriyor. Bu demetin ilk öğesi, divmod() fonksiyonuna verilen ilk parametrenin ikinci parametreye bölünmesi işleminin sonucudur. Demetimizin ikinci öğesi ise, ilk parametrenin ikinci parametreye bölünmesi işleminden kalan sayıdır. Yani demetin ilk parametresi bölme işleminin ‘bölüm’ kısmını, ikinci öğesi ise ‘kalan’ kısmını verir.

Bu fonksiyonun bölme işlemininin sonucunu tamsayı cinsinden verdiğine dikkat ediyoruz:


```python
divmod(10, 3)
```




    (3, 1)



10 sayısı 3 sayısına bölündüğünde tamsayı cinsinden sonuç 3 ‘tür. Bu bölme işleminin kalanı ise 1 ‘dir.

### enumerate()

İngilizcede enumerate kelimesi ‘numaralandırmak’ anlamına gelir. enumerate() fonksiyonunun görevi de kelimenin bu anlamıyla aynıdır. Yani bu fonksiyonu kullanarak nesneleri numaralandırabiliriz.

Bu fonksiyon bize bir ‘enumerate’ nesnesi verir:


```python
enumerate('python')
```




    <enumerate at 0x10e47baa0>



Bu nesnenin içeriğine nasıl erişebileceğimizi biliyorsunuz: 

Nesneyi bir listeye çevirebiliriz:


```python
list(enumerate('python'))
```




    [(0, 'p'), (1, 'y'), (2, 't'), (3, 'h'), (4, 'o'), (5, 'n')]



veya:


```python
[i for i in enumerate('python')]
```




    [(0, 'p'), (1, 'y'), (2, 't'), (3, 'h'), (4, 'o'), (5, 'n')]



print() fonksiyonuna yıldızlı parametre olarak verebiliriz:


```python
print(*enumerate('python'))
```

    (0, 'p') (1, 'y') (2, 't') (3, 'h') (4, 'o') (5, 'n')


veya nesne üzerinde bir döngü kurabiliriz:


```python
for i in enumerate('python'):
    print(i)
```

    (0, 'p')
    (1, 'y')
    (2, 't')
    (3, 'h')
    (4, 'o')
    (5, 'n')


### exit()

Bu fonksiyon, o anda çalışan programdan çıkmanızı sağlar. Eğer bu komutu etkileşimli kabukta verirseniz o anda açık olan oturum kapanacaktır.

### help()

help() fonksiyonu gömülü fonksiyonlar içinde en faydalı fonksiyonların başında gelir. Bu fonksiyonu kullanarak Python programlama diline ait öğelere ilişkin yardım belgelerine ulaşabiliriz. Örneğin:


```python
help(dir)
```

    Help on built-in function dir in module builtins:
    
    dir(...)
        dir([object]) -> list of strings
        
        If called without an argument, return the names in the current scope.
        Else, return an alphabetized list of names comprising (some of) the attributes
        of the given object, and of attributes reachable from it.
        If the object supplies a method named __dir__, it will be used; otherwise
        the default dir() logic is used and returns:
          for a module object: the module's attributes.
          for a class object:  its attributes, and recursively the attributes
            of its bases.
          for any other object: its attributes, its class's attributes, and
            recursively the attributes of its class's base classes.
    


Bu komutu verdiğimizde dir() fonksiyonunun ne işe yaradığını gösteren İngilizce bir belgeye ulaşırız. Gördüğünüz gibi, hakkında bilgi edinmek istediğimiz öğeyi help() fonksiyonuna parametre olarak vererek ilgili yardım dosyasına erişebiliyoruz.

Eğer bu fonksiyonu parametresiz olarak kullanırsak ‘etkileşimli yardım’ denen ekrana ulaşırız:


```python
help()
```

    
    Welcome to Python 3.7's help utility!
    
    If this is your first time using Python, you should definitely check out
    the tutorial on the Internet at https://docs.python.org/3.7/tutorial/.
    
    Enter the name of any module, keyword, or topic to get help on writing
    Python programs and using Python modules.  To quit this help utility and
    return to the interpreter, just type "quit".
    
    To get a list of available modules, keywords, symbols, or topics, type
    "modules", "keywords", "symbols", or "topics".  Each module also comes
    with a one-line summary of what it does; to list the modules whose name
    or summary contain a given string such as "spam", type "modules spam".
    
    help> dir
    Help on built-in function dir in module builtins:
    
    dir(...)
        dir([object]) -> list of strings
        
        If called without an argument, return the names in the current scope.
        Else, return an alphabetized list of names comprising (some of) the attributes
        of the given object, and of attributes reachable from it.
        If the object supplies a method named __dir__, it will be used; otherwise
        the default dir() logic is used and returns:
          for a module object: the module's attributes.
          for a class object:  its attributes, and recursively the attributes
            of its bases.
          for any other object: its attributes, its class's attributes, and
            recursively the attributes of its class's base classes.
    
    help> q
    
    You are now leaving help and returning to the Python interpreter.
    If you want to ask for help on a particular object directly from the
    interpreter, you can type "help(object)".  Executing "help('string')"
    has the same effect as typing a particular string at the help> prompt.


Bu ekranda, hakkında bilgi edinmek istediğiniz öğeyi help> ibaresinden hemen sonra, boşluk bırakmadan yazarak öğeye ilişkin bilgilere ulaşabilirsiniz:

Etkileşimli yardım ekranından çıkmak için ‘q’ harfine basabilirsiniz.

### id()

Python’da her nesnenin bir kimliğinin olduğunu biliyorsunuz. Python’daki her nesnenin kimliği eşşiz, tek ve benzersizdir.


```python
a = 50

id(a)
```




    4491754160




```python
kardiz = "Merhaba Dünya"

id(kardiz)
```




    4534630896



### input()

Bu fonksiyonun ne işe yaradığını gayet iyi biliyorsunuz. input() adlı bu gömülü fonksiyonu kullanarak kullanıcı ile veri alışverişinde bulunabiliyoruz.

### format()

Bu gömülü fonksiyonun görevi, daha önce karakter dizilerini işlerken, karakter dizilerinin bir metodu olarak öğrendiğimiz format() metodununa benzer bir şekilde, karakter dizilerini biçimlendirmektir. Ancak format() fonksiyonu, daha önce öğrendiğimiz format() metoduna göre daha dar kapsamlıdır. format() metodunu kullanarak oldukça karmaşık karakter dizisi biçimlendirme işlemlerini gerçekleştirebiliriz, ama birazdan inceleyeceğimiz format() gömülü fonksiyonu yalnızca tek bir değeri biçimlendirmek için kullanılır.

Basit bir örnek verelim:


```python
format(12, '.2f')
```




    '12.00'



Yukarıdaki ifadeyi daha önce gördüğümüz format() metodu ile şu şekilde yazabiliriz:


```python
'{:.2f}'.format(12)
```




    '12.00'



### filter()

Bu gömülü fonksiyon yardımıyla dizi niteliği taşıyan nesneler içindeki öğeler üzerinde belirli bir ölçüte göre bir süzme işlemi uygulayabiliriz.

filter() fonksiyonu toplam iki parametre alır. Bu parametrelerden ilki ölçütü belirleyen fonksiyon, ikincisi ise bu ölçütün uygulanacağı öğedir. Yukarıdaki örneğe baktığımızda, tek() adlı fonksiyonun, l adlı öğe üzerine uygulandığını görüyoruz.

Yukarıdaki örnekte ilk olarak tek() adlı bir fonksiyon tanımladık:


```python
def tek(sayı):
        return sayı % 2 == 1
```

Bu fonksiyonun görevi, kendisine parametre olarak verilen bir sayının tek sayı olup olmadığını sorgulamak. Eğer verilen parametre bir tek sayı ise fonksiyonumuz True değerini, tek sayı değilse False değerini döndürecektir. İsterseniz fonksiyonumuzu test edelim:


```python
print(tek(12))
```

    False


12 sayısı bir tek sayı olmadığı için fonksiyonumuz bize False çıktısı verir. 

Bir de şuna bakalım:


```python
print(tek(117))
```

    True


117 sayısı ise bir tek sayıdır. Bu nedenle fonksiyonumuz bize True değerini verecektir. 

İşte biz bu fonksiyonu, filter() fonksiyonu yardımıyla şu liste üzerine uygulayacağız:


```python
l = [400, 176, 64, 175, 355, 13, 207, 298, 397, 386, 31, 120, 120, 236, 241, 123, 249, 364, 292, 153]
```

Dediğimiz gibi, filter() fonksiyonu, dizi özelliği taşıyan nesneler üzerinde belli bir ölçüte göre filtreleme işlemi yapmamızı sağlar. Biz de biraz önce tanımladığımız tek() adlı fonksiyonu l adlı bu listeye uygulayarak liste içindeki tek sayıları filtreleyeceğiz.

filter() fonksiyonunu çalıştıralım:


```python
filter(tek, l)
```




    <filter at 0x10e48d6d0>



Burada filter() fonksiyonuna ilk parametre olarak tek() fonksiyonunu verdik. İkinci parametremiz ise bu fonksiyonu uygulayacağımız l adlı liste. Amacımız, l adlı liste üzerine tek() fonksiyonunu uygulayarak, bu liste içindeki öğelerden True çıktısı verenleri (yani tek sayıları) ayıklamak.

Gördüğünüz gibi, bu fonksiyonu bu şekilde kullandığımızda elde ettiğimiz şey bir ‘filtre nesnesi’. Bu nesne içindeki öğeleri görebilmek için ne yapabileceğimizi biliyorsunuz:


```python
list(filter(tek, l))
```




    [175, 355, 13, 207, 397, 31, 241, 123, 249, 153]



veya:


```python
print(*filter(tek, l))
```

    175 355 13 207 397 31 241 123 249 153


ya da:


```python
[i for i in filter(tek, l)]
```




    [175, 355, 13, 207, 397, 31, 241, 123, 249, 153]



Gördüğünüz gibi, gerçekten de l adlı liste içindeki bütün tek sayılar süzüldü.

### hash()

Bu fonksiyon, belirli türdeki nesnelere bir karma değeri vermemizi sağlar. Örneğin:


```python
hash('python')
```




    -2102507435354808480



Ancak bu fonksiyonun ürettiği çıktı aynı nesne için bütün sistemlerde aynı olmayabilir. Yani örneğin yukarıdaki hash(’istihza’) komutu 32 bitlik ve 64 bitlik işletim sistemlerinde birbirinden farklı sonuçlar verebilir. Ayrıca bu fonksiyonun ürettiği karma değerlerinin birbiriyle çakışma ihtimali de yüksektir. Dolayısıyla bu fonksiyonu kullanarak, mesela parola girişleri için karma değeri üretmek doğru olmaz.

### isinstance()

Bu fonksiyonu şöyle kullanıyoruz:


```python
isinstance('python', str)
```




    True



Gördüğünüz gibi ’python’ gerçekten bir karakter dizisi (str) olduğu için komutumuz True çıktısı veriyor.

Bir de şuna bakalım:


```python
isinstance('python', list)
```




    False



’python’ bir liste (list) olmadığı için komutumuz bu kez False çıktısı verdi.

### len()

Bu fonksiyon yardımıyla nesnelerin uzunluklarını hesaplayabileceğimizi biliyorsunuz


```python
len('python')
```




    6




```python
len([1, 4, 5, 3, 2, 9, 10])
```




    7



### map()

Diyelim ki elimizde şöyle bir liste var:


```python
l = [1, 4, 5, 4, 2, 9, 10]
```

Amacımız bu liste içindeki her öğenin karesini hesaplamak.


```python
def karesi(n):
    return n ** 2
```

Burada bir n sayısının karesini hesaplayan bir fonksiyon tanımladık. Şimdi bu fonksiyonu l listesinin bütün öğeleri üzerine uygulayacağız:


```python
list(map(karesi, l))
```




    [1, 16, 25, 16, 4, 81, 100]



### max()

max() gömülü fonksiyonunun görevi, bir dizi içindeki en büyük öğeyi vermektir. Bu fonksiyon birkaç farklı parametre alır ve verdiği çıktı, aldığı parametrelerin türüne ve sayısına bağlı olarak değişiklik gösterebilir.

Bu fonksiyonu en basit şu şekilde kullanabilirsiniz:


```python
max(1, 2, 3)
```




    3



max() fonksiyonu yukarıda gösterildiği gibi birtakım isimsiz parametrelerle birlikte key adlı isimli bir parametre de alır. Bu parametre yardımıyla max() fonksiyonunun ‘en büyük’ kavramını hangi ölçüte göre seçeceğini belirleyebiliriz. Örneğin:


```python
isimler = ['ahmet', 'can', 'mehmet', 'selin', 'abdullah', 'kezban']

max(isimler, key=len)
```




    'abdullah'



max() fonksiyonu öntanımlı olarak, ‘en büyük’ kavramını sayısal büyüklük üzerinden değerlendirir. Yani herhangi bir key parametresi kullanılmadığında, bu fonksiyon otomatik olarak bir dizi içindeki en büyük sayıyı bulur. Ancak eğer biz istersek, yukarıdaki örnekte olduğu gibi, ‘en büyük’ kavramının uzunluk cinsinden değerlendirilmesini de sağlayabiliriz.

### min()

min() fonksiyonu max() fonksiyonunun tam tersini yapar. Bildiğiniz gibi max() fonksiyonu bir dizi içindeki en büyük öğeyi buluyordu. İşte min() fonksiyonu da bir dizi içindeki en küçük öğeyi bulur. Bu fonksiyonun kullanımı max() ile aynıdır.


```python
min(-5,1,2,3,4,10)
```




    -5



### open()

Bu fonksiyon herhangi bir dosyayı açmak veya oluşturmak için kullanılır. Eğer dosyanın açılması veya oluşturulması esnasında bir hata ortaya çıkarsa IOError türünde bir hata mesajı verilir.

### pow()

Bu fonksiyon İngilizcedeki power (kuvvet) kelimesinin kısaltmasından oluşur. Adının anlamına uygun olarak, bu fonksiyonu bir sayının kuvvetlerini hesaplamak için kullanıyoruz.

Bu fonksiyon en temel şekilde şöyle kullanılır:


```python
pow(2, 3)
```




    8



Bu komutla 2 sayısının 3. kuvvetini hesaplamış oluyoruz.

pow() fonksiyonu toplamda üç farklı parametre alır. İlk iki parametrenin ne olduğunu yukarıda örnekledik. Üçüncü parametre ise kuvvet hesaplaması sonucu elde edilen sayının modülüsünü hesaplayabilmemizi sağlar. Yani:


```python
pow(2, 3, 2)
```




    0



Burada yaptığımız şey şu: Öncelikle 2 sayısının 3. kuvvetini hesapladık. Elde ettiğimiz sayı 8. Ardından da bu sayının 2 ‘ye bölünmesi işleminden kalan sayıyı elde ettik. Yani 0.

### print()

Bu fonksiyonu, bildiğiniz gibi, kullanıcılarımıza birtakım mesajlar göstermek için kullanıyoruz.

Kullanımını daha önce ayrıntılı bir şekilde anlatmış olduğumuz bu fonksiyonu şu şekilde formüle edebiliriz:

```python
print(deg1, deg2, deg3, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
```

Burada;

**degx** Çıktı verilecek değerlerin ne olduğunu belirtir. Buraya 256 adete kadar değer yazabilirsiniz.
sep Çıktı verilirken değerlerin arasına hangi karakterin yerleştirileceğini belirtir. Bu değer öntanımlı olarak boşluk karakteridir.

**end** Çıktı verilecek son değerin ardından hangi karakterin iliştirileceğini belirtir. Bu değer öntanımlı olarak satır başı (\n ) karakteridir.

**file** Çıktıların hangi dosyaya yazılacağını belirtir. Öntanımlı olarak bu parametrenin değeri sys.stdout‘tur. Yani print() fonksiyonu çıktılarını öntanımlı olarak standart çıktı konumuna gönderir.

**flush** Bildiğiniz gibi, herhangi bir dosyaya yazma işlemi sırasında dosyaya yazılacak değerler öncelikle tampona alınır. İşlem tamamlandıktan sonra tampondaki bu değerler topluca dosyaya aktarılır. İşte bu parametre, değerleri tampona almadan doğrudan dosyaya gönderebilmemizi sağlar. Bu parametrenin öntanımlı değeri False‘tur. Yani değerler dosyaya yazılmadan önce öntanımlı olarak öncelikle tampona gider. Ama eğer biz bu parametrenin değerini True olarak değiştirirsek, değerler doğrudan dosyaya yazılır.

### quit()

Bu fonksiyonu programdan çıkmak için kullanıyoruz. Eğer bu fonksiyonu etkileşimli kabukta verecek olursanız etkileşimli kabuk kapanacaktır.

### range()

Bu fonksiyonu belli bir aralıktaki sayıları listelemek için kullanıyoruz. Yani mesela 0 ile 10 arası sayıların listesini almak istersek şöyle bir komut yazabiliriz:


```python
l = range(0, 10)
```

Ancak burada dikkat etmemiz gereken bir özellik var: Bu fonksiyon aslında doğrudan herhangi bir sayı listesi oluşturmaz. Yukarıda l değişkenine atadığımız komutu ekrana yazdırırsak bunu daha net görebilirsiniz:


```python
print(l)
```

    range(0, 10)


Bir de bu verinin tipine bakalım:


```python
type(l)
```




    range



Gördüğünüz gibi, elimizdeki şey aslında bir sayı listesi değil, bir ‘range’ (aralık) nesnesidir. Biz bu nesneyi istersek başka veri tiplerine dönüştürebiliriz. Mesela bunu bir listeye dönüştürelim:


```python
list(l)
```




    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]



### reversed()

Bir listedeki isimleri ters çevirmek için kullanılır.


```python
isimler = ['ahmet', 'mehmet', 'veli', 'ayşe', 'çiğdem', 'ışık']
```


```python
reversed(isimler)
```




    <list_reverseiterator at 0x10e4819d0>



Gördüğünüz gibi, tıpkı range() fonksiyonunda olduğu gibi, reversed() fonksiyonu da bize ürettiği öğelerin kendisi yerine, bir ‘nesne’ veriyor. Ama tabii ki bu bizim için bir sorun değil. Biz bu nesnenin içeriğini nasıl elde edebileceğimizi gayet iyi biliyoruz:


```python
list(reversed(isimler))
```




    ['ışık', 'çiğdem', 'ayşe', 'veli', 'mehmet', 'ahmet']



### sorted()

Bu metot, daha önceki derslerimizden de bildiğiniz gibi, bir dizi içindeki öğeleri belirli bir ölçüte göre sıraya dizmemizi sağlıyor. Bununla ilgili çok basit bir örnek verelim:


```python
sorted('ahmet')
```




    ['a', 'e', 'h', 'm', 't']



Bu kodlar yardımıyla ahmet adlı karakter dizisi içindeki harfleri alfabe sırasına dizdik.

sorted() fonksiyonuna hangi türde bir veri tipi verirseniz verin, aldığınız çıktı her zaman bir liste olacaktır. Bunu unutmayın.

Bu fonksiyon, Türkçe karakter içeren öğeleri düzgün sıralayamaz.

### slice()

Bildiğiniz gibi, birtakım öğelerden oluşan bir nesnenin yalnızca belli kısımlarını ayırıp alma işlemine ‘dilimleme’ adı veriliyor. Bu fonksiyon dilimleme yapabilmemiz sağlar.


```python
l = ['ahmet', 'mehmet', 'ayşe', 'senem', 'salih']
```


```python
dl = slice(0, 3)
```


```python
l[dl]
```




    ['ahmet', 'mehmet', 'ayşe']



Gördüğünüz gibi, slice() fonksiyonunu yukarıda iki parametre ile kullandık. Tahmin edebileceğiniz gibi, bu fonksiyonunu formülü şu şekildedir:

```python
slice(başlangıç, bitiş, atlama)
```

### sum()

Bu fonksiyonun temel görevi, bir dizi içindeki değerlerin toplamını bulmaktır. Örneğin:


```python
l = [1, 2, 3]

sum(l)
```




    6



Bu fonksiyon genellikle yukarıdaki gibi tek parametreyle kullanılır. Ama aslında bu fonksiyon ikinci bir parametre daha alır. Dikkatlice bakın:


```python
l = [1, 2, 3]

sum(l, 10)
```




    16



Gördüğünüz gibi, Python sum() fonksiyonuna verilen ikinci parametreyi, birinci parametredeki toplam değerin üzerine ekliyor.

### type()

type() fonksiyonunun görevi bir nesnenin hangi veri tipine ait olduğunu söylemektir. Bu fonksiyonu artık yakından tanıyorsunuz:


```python
type('kiraz')
```




    str



### zip()

Gelin isterseniz bu fonksiyonu bir örnek üzerinden açıklamaya çalışalım. 

Diyelim ki elimizde şöyle iki farklı liste var:


```python
a1 = ['a', 'b', 'c']

a2 = ['d', 'e', 'f']
```

Eğer bu listelerin öğelerini birbirleriyle eşleştirmek istersek zip() fonksiyonundan yararlanabiliriz.

Dikkatlice bakın:


```python
zip(a1, a2)
```




    <zip at 0x10e492500>



Gördüğünüz gibi, yukarıdaki kod bize bir ‘zip’ nesnesi veriyor. Bu nesnenin öğelerine nasıl ulaşabileceğinizi biliyorsunuz:


```python
print(*zip(a1, a2))
```

    ('a', 'd') ('b', 'e') ('c', 'f')



```python
list(zip(a1, a2))
```




    [('a', 'd'), ('b', 'e'), ('c', 'f')]



Bu özellikten pek çok farklı şekilde yararlanabilirsiniz. Örneğin:


```python
isimler = ['ahmet', 'mehmet', 'zeynep', 'ilker']

yaslar = [25, 40, 35, 20]


for i, y in zip(isimler, yaslar):
    print('isim: {} / yaş: {}'.format(i, y))
```

    isim: ahmet / yaş: 25
    isim: mehmet / yaş: 40
    isim: zeynep / yaş: 35
    isim: ilker / yaş: 20


### vars()

Bu fonksiyon, mevcut isim alanı içindeki metot, fonksiyon ve nitelikleri listeler. Eğer bu fonksiyonu parametresiz olarak kullanırsak, daha önce gördüğümüz locals() fonksiyonuyla aynı çıktıyı elde ederiz:


```python
# vars() #uzun çıktılar verdiği için çalıştırılmamıştır, sizler test etmek için çalıştırabilirsiniz.
```

```python
{'__builtins__': <module 'builtins' (built-in)>, '__name__': '__main__', '__package__': None, '__loader__': <class '_frozen_importlib.BuiltinImporter'>, '__doc__': None}
```

Bu fonksiyonu, nesnelerin metotlarını ve niteliklerini öğrenmek için de kullanabilirsiniz:


```python
# vars(str)
```

Yukarıda sırasıyla karakter dizilerinin, listelerin ve sözlüklerin metotlarını listeledik. Bu yönüyle vars() fonksiyonu dir() fonksiyonuna benzer.

> Son Güncelleme: 26 Aralık 2019 - Perşembe
