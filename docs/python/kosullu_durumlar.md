# Koşullu Durumlar

Koşullu Duumlar, geliştirdiğimiz yazılımda bazı filtrelemeler yapmamızı veya belirli bir koşul belirleyip ona göre davranmasını sağlayabiliriz. Bunun için python'da bulunan koşulları inceleyelim.

## Koşul Deyimleri

### İf

Python programlama dilinde koşullu durumları belirtmek için üç adet deyimden faydalanırız:

- if
- elif
- else

if deyimi ile başlayalım.


```python
a = 10
if a > 5:
    print("Sayı 10'dan büyüktür.")
```

    Sayı 10'dan büyüktür.


if deyimi >(büyüktür) işaretinin haricinde farklı işaretlerde almaktadır.

| İşleç |     Anlamı    |
|:-----:|:-------------:|
|   >   |    büyüktür   |
|   <   |    küçüktür   |
|   >=  | büyük eşittir |
|   <=  | küçük eşittir |
|   ==  |    eşittir    |
|   !=  | eşit değildir |

Kullanıcıdan bilgi alarak if deyimini kullanalım.


```python
sayi = int(input("Bir sayı giriniz: "))
if sayi < 5:
    print("sayı 5'ten küçüktür.")
if sayi > 5:
    print("sayı 5'ten büyüktür.")
if sayi == 5:
    print("sayı 5'e eşittir.")
```

    Bir sayı giriniz: 5
    sayı 5'e eşittir.


### elif

elif, bir başka koşul deyimidir. Nasıl çalıştığını aşağıda bulunan örneği incleyerek anlayalım.


```python
sayi = int(input("Bir sayı giriniz: "))

if sayi == 5:
    print("sayı 5'e eşittir.")
elif sayi < 5:
    print("sayı 5'ten küçüktür.")
elif sayi < 10:
    print("sayı 10'dan küçüktür.")
elif sayi > 5:
    print("sayı 5'ten büyüktür.")
```

    Bir sayı giriniz: 1
    sayı 5'ten küçüktür.


Yukarıda yazdığımız örneği hepsi if olacak şekilde yazalım ve iki sonucuda karşılaştıralım.


```python
sayi = int(input("Bir sayı giriniz: "))

if sayi == 5:
    print("sayı 5'e eşittir.")
if sayi < 5:
    print("sayı 5'ten küçüktür.")
if sayi < 10:
    print("sayı 10'dan küçüktür.")
if sayi > 5:
    print("sayı 5'ten büyüktür.")
```

    Bir sayı giriniz: 1
    sayı 5'ten küçüktür.
    sayı 10'dan küçüktür.


Gördüğünüz gibi elif koşulunu kullanarak yazdığımız zaman girmiş olduğumuz değer hem 5 hem de 10 değerinden küçük olduğu halde sadece 5'ten küçüktür dedi. Yani elif değeri kendisinden sonraki başka koşul çalışacak dahi olsa o koşula hiç uğramıyor.

Aynı programı if değerini kullandığımız zaman hem 5'ten küçüktür hem de 10'dan küçüktür yazdı. Bu da bizlere if ve elif koşullarının nasıl çalıştığı hakkında bilgi veriyor.

### else

else koşullu deyimi yukarıda bahsettiğimiz koşullu deyimlerden biraz farklı çalışmaktadır. Nasıl çalıştığını bir örnek üzerinde inceleyelim.


```python
sayi = int(input("Bir sayı giriniz: "))

if sayi == 1:
    print("Bildiniz.")
else: 
    print("Tekrar deneyiniz.")
```

    Bir sayı giriniz: 0
    Tekrar deneyiniz.


Görmüş olduğunuz gibi eğer yazmış olduğumuz koşul sağlanmadığı zaman else durumu çalışmaktadır.

> Son Güncelleme: 16 Aralık 2019 - Pazartesi
