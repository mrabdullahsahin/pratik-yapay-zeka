# Değişkenler

Değişkenler bütün programlama dillerinde olmazsa olmazdır. Değişken tanımlarken bazı kurallar mevcuttur.

- Değişken adları bir sayı ile başlayamaz. Yani şu kullanım yanlıştır:


```python
3_kilo = "5 TL"
```


      File "<ipython-input-1-bc29f79e52e9>", line 1
        3_kilo = "5 TL"
         ^
    SyntaxError: invalid token



- Değişken adları aritmetik işleçlerle başlayamaz. Yani şu kullanım yanlıştır:


```python
+değer = 4568
```


      File "<ipython-input-2-53e025623b01>", line 1
        +değer = 4568
                     ^
    SyntaxError: can't assign to operator



- Değişken adları ya bir alfabe harfiyle ya da _ işaretiyle başlamalıdır:


```python
_deger = 4568
deger = 4568
```

- Değişken adları içinde Türkçe karakterler kullanabilirsiniz. Ancak ileride beklenmedik uyum sorunları çıkması ihtimaline karşı değişken adlarında Türkçe karakter kullanmaktan kaçınmak isteyebilirsiniz.


- Python için anahtar veya özel olan kelimeleri değişken adı olarak kullanamazsınız. Bu adlar aşağıda listelenmiştir.


```python
import keyword
keyword.kwlist
```




    ['False',
     'None',
     'True',
     'and',
     'as',
     'assert',
     'async',
     'await',
     'break',
     'class',
     'continue',
     'def',
     'del',
     'elif',
     'else',
     'except',
     'finally',
     'for',
     'from',
     'global',
     'if',
     'import',
     'in',
     'is',
     'lambda',
     'nonlocal',
     'not',
     'or',
     'pass',
     'raise',
     'return',
     'try',
     'while',
     'with',
     'yield']



## type Fonksiyonu

Bu fonksiyonu herhangi bir nesnenin hangi veri tipinde olduğunu öğrenebilmemizi sağlar.


```python
print(type("Abdullah"))
print(type(1))
print(type(5.0))
print(type(True))
```

    <class 'str'>
    <class 'int'>
    <class 'float'>
    <class 'bool'>


## len Fonksiyonu

len fonksiyonu ile bir verinin uzunluğunu hızlıca öğrenebilirsiniz.


```python
len("Abdullah")
```




    8




```python
isim = "Abdullah"
len(isim)
```




    8



> Son Güncelleme: 14 Aralık 2019 - Cumartesi
