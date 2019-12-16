# Kaçış Dizileri

## Ters Taksim (/)

Bu işaret karakter dizilerini tanımlarken oluşabilecek hatalardan kaçmamızı sağlar.


```python
print('İstanbul\'un 5 günlük hava durumu tahmini')
```

    İstanbul'un 5 günlük hava durumu tahmini


## Satır Başı (/n)


```python
print("birinci satır\nikinci satır\nüçüncü satır")
```

    birinci satır
    ikinci satır
    üçüncü satır


## Sekme (/t)

/t kaçış dizisi sanki Tab (sekme) tuşuna basılmış gibi bir etki oluşturur.


```python
print("abc\tdef")
```

    abc	def



```python
print("bir", "iki", "üç", sep="\t")
```

    bir	iki	üç



```python
print(*"123456789", sep="\t")
```

    1	2	3	4	5	6	7	8	9


## Zil Sesi (/a)

\ işareti ‘a’ harfiyle birleşerek !bip! benzeri bir zil sesi üretilmesini sağlar.


```python
print("\a")
```

    


## Aynı Satır Başı (/r)

Bu kaçış dizisi, bir karakter dizisinde aynı satırın en başına dönülmesini sağlar.


```python
print("Merhaba\rDünya")
```

    Dünya


Burada, “Merhaba” karakter dizisi ekrana yazdırıldıktan sonra \r kaçış dizisinin etkisiyle satır başına dönülüyor ve bu kaçış dizisinden sonra gelen “Dünya” karakter dizisi “Merhaba” karakter dizisinin üzerine yazıyor. Tabii “Dünya” karakter dizisi içinde 5 karakter, “Merhaba” karakter dizisi içinde ise 7 karakter olduğu için, “Merhaba” karakter dizisinin son iki karakteri (“ba”) dışarda kalıyor. Böylece ortaya “Dünyaba” gibi bir şey çıkıyor.

## İmleç Kaydırma (/b)

\b kaçış dizisinin görevi, imleci o anki konumundan sola kaydırmaktır. 


```python
print("yahoo.com\b.uk")
```

    yahoo.com.uk


## Küçük Unicode (/u)

Bu kaçış dizisi UNICODE sistemindeki her bir kodun konumunu gösterir.


```python
'\u0130'
```




    'İ'



## Büyük Unicode (/U)

UNICODE kod konumlarını gösterebilmemizi sağlar.


```python
'\U00000131'
```




    'ı'



## Uzun Ad (/N)

Karakterleri UNICODE adlarına göre kullanabilmemizi sağlar.


```python
print("\N{LATIN SMALL LETTER A}")
```

    a


## Onaltılı Karakter (\x)

Onaltılı sistemdeki bir sayının karakter karşılığını gösterebilmemizi sağlar.


```python
"\x41"
```




    'A'



## Etkisizleştirme (r)

Karakter dizisi içinde kaçış dizilerini kullanabilmemizi sağlar.


```python
print(r"Kurulum dizini: C:\aylar\nisan\toplam masraf")
```

    Kurulum dizini: C:\aylar\nisan\toplam masraf

