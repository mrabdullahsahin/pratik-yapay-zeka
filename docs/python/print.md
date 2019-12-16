# print Fonksiyonu

Print fonksiyonu ekrana çıktı vermemizi sağlar.


```python
print("Python")
```

    Python


Print fonksiyonunu üç farklı tırnak ile birlikte kullanabilirsiniz.

1. Tek tırnak (‘ ‘)
2. Çift tırnak (” ”)
3. Üç tırnak (“”” “””)


```python
print('1) Python programlama dili')
print("2) Python programlama dili")
print("""3) Python programlama dili""")
```

    1) Python programlama dili
    2) Python programlama dili
    3) Python programlama dili


Print fonksiyonun içerisinde tırnakları beraber kullanmak istedğiniz zaman ise şu şekilde bir yol izleyebilirsiniz.


```python
print('Python programlama dilinin adı "piton" yılanından gelmez')
print("İstanbul'un 5 günlük hava durumu tahmini")
print("""Python programlama dilinin adı "piton" yılanından gelmez""")
print("""İstanbul'un 5 günlük hava durumu tahmini""")
```

    Python programlama dilinin adı "piton" yılanından gelmez
    İstanbul'un 5 günlük hava durumu tahmini
    Python programlama dilinin adı "piton" yılanından gelmez
    İstanbul'un 5 günlük hava durumu tahmini


Print içerisinde üç tırnak kullanarak çok farklı çıktılar verebilirsiniz.


```python
print("""
 [H]=========ŞAHİ========[-][o][x]
 |                                 |
 |     Programa Hoşgeldiniz!       |
 |           Sürüm 0.8             |
 |    Devam etmek için herhangi    |
 |       bir düğmeye basın.        |
 |                                 |
 |=================================|
 """)
```

    
     [H]=========ŞAHİ========[-][o][x]
     |                                 |
     |     Programa Hoşgeldiniz!       |
     |           Sürüm 0.8             |
     |    Devam etmek için herhangi    |
     |       bir düğmeye basın.        |
     |                                 |
     |=================================|
     


Print fonksiyonunda rakam ile harfleri beraber yazdırabilirsiniz.


```python
print("Python", "Versiyon",3.7)
```

    Python Versiyon 3.7


## print() Fonksiyonunun Parametreleri

### sep

sep parametresi, ekrana basılacak öğeler arasına hangi karakterin yerleştirileceğini gösterir.


```python
print("http://", "www.", "istihza.", "com", sep="")
```

    http://www.istihza.com



```python
print("İstanbul", "Konya", sep="-")
```

    İstanbul-Konya


### end

end parametresi ise bu parametrelerin sonuna neyin geleceğini belirler.


```python
print("Bugün günlerden Cuma", end=".")
```

    Bugün günlerden Cuma.

### file

file verilen karakter dizisi ve/veya sayıların, yani parametrelerin nereye yazılacağını belirtmektir. Aşağıda bulunan komutlarıo çalıştırdığımız taktirde python dosyasının bulunduğu konuma deneme.txt isminde bir dosya oluşturup belirtmiş olduğumuz cümleyi yazacaktır.


```python
dosya = open("deneme.txt", "w")
print("Ben Python, Monty Python!", file=dosya)
dosya.close()
```

### yıldız(*)

Bu parametre veriler arasında işlem yapmamızı sağlar.


```python
print(*"Python")
```

    P y t h o n

