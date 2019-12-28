## NumPy

**NumPy**, bilimsel hesaplama için temel bir pakettir. Aşağıdakileri içeren bir **Python** dil uygulamasıdır:

* Güçlü N boyutlu dizi yapısı
* Gelişmiş fonksiyonlar
* C/C++ ve Fortran koduna entegre edilebilen araçlar
* Lineer cebir, Fourier dönüşümü ve rastgele sayı özellikleri

Bilimsel hesaplama için kullanılmaya ek olarak, NumPy'da genel veriler için verimli çok boyutlu bir araç olarak kullanılabilir. Her tür veriyle çalışabileceği için, NumPy sorunsuz ve verimli bir şekilde birden fazla veri tabanı türüne entegre edilebilir.

## Kütüphaneyi Tanımlama


```python
import numpy as np # lineer cebir
import pandas as pd # veri işleme
```

## Temel Özellikler ve Dizi Oluşturma

Burada 1 boyutlu bir dizi ve uzunluğu ise 3 olan bir dizi mevcuttur.


```python
[1,2,3]
```




    [1, 2, 3]



Aşağıda ise 2 boyutlu bir dizi ve uzunluğu ise 3 olan bir dizi mevcuttur.


```python
[[ 1, 2, 3],[ 4, 5, 6]]
```




    [[1, 2, 3], [4, 5, 6]]



NumPy dizi fonksiyonu ile iki adet farklı boyutlarda diziler oluşturalım.


```python
a = np.array([1, 2, 3])
b = np.array([(1,2,3), (4,5,6)])

print("a: ",a)
print("b: ",b)
```

    a:  [1 2 3]
    b:  [[1 2 3]
     [4 5 6]]


Köşeli parantezlerin burada gerekli olduğunu unutmayın. Ve aşağıdaki yazı biçimi yanlıştır:


```python
# a = np.array(1,2,3,4) # YANLIŞ!!!
```

NumPy'nin dizi sınıfının takma adı **numpy.array** olan **ndarray**, Python standart kitaplığındaki **array.array** öğesinden farklıdır. **ndarray** 'ın özellikleri aşağıdaki gibidir:

* **ndarray.ndim:** dizinin kaç boyutlu olduğunu gösterir.
* **ndarray.shape:** Uzunluğu, dizinin （ndim） boyutuna göre belirlenen bir sayı dizisidir. Örneğin, uzunluğu n olan tek boyutlu bir dizinin şekli n'dir ve n satırlı ve m sütunlu bir dizinin şekli n, m'dir.
* **ndarray.size:** dizideki tüm öğelerin sayısı.
* **ndarray.dtype:** dizideki elemanın veri tipi, örneğin numpy.int32, numpy.int16 veya numpy.float64.
* **ndarray.itemsize:** dizideki her öğenin bayt cinsinden boyutu.

Aşağıda bulunan kod örneğiniz inceleyelim.


```python
a = np.array([1, 2, 3])
b = np.array([(1,2,3), (4,5,6)])

print('a=')
print(a)
print("a's ndim {}".format(a.ndim))
print("a's shape {}".format(a.shape))
print("a's size {}".format(a.size))
print("a's dtype {}".format(a.dtype))
print("a's itemsize {}".format(a.itemsize))

print('')

print('b=')
print(b)
print("b's ndim {}".format(b.ndim))
print("b's shape {}".format(b.shape))
print("b's size {}".format(b.size))
print("b's dtype {}".format(b.dtype))
print("b's itemsize {}".format(b.itemsize))
```

    a=
    [1 2 3]
    a's ndim 1
    a's shape (3,)
    a's size 3
    a's dtype int64
    a's itemsize 8
    
    b=
    [[1 2 3]
     [4 5 6]]
    b's ndim 2
    b's shape (2, 3)
    b's size 6
    b's dtype int64
    b's itemsize 8


Diziyi oluştururken elemanın veri tipini de belirtebiliriz, örneğin:


```python
c = np.array( [ [1,2], [3,4] ], dtype=complex )
c
```




    array([[1.+0.j, 2.+0.j],
           [3.+0.j, 4.+0.j]])



## Belirli Bir Dizi Oluşturma

Mühendislikte, genellikle belirli veri türlerine ihtiyaç duyarız ve NumPy bize bunları sağlar:

* **zeros:** elemanları 0 olan bir dizi oluşturmak için kullanılır
* **ones:** elemanları 1 olan bir dizi oluşturmak için kullanılır
* **empty:** boş bir dizi oluşturmak için kullanılır.
* **arange:** kapsam ve rakam aralığı belirleyerek bir dizi oluşturmak için kullanılır.
* **linespace:** aralığı ve öğe sayısını belirterek bir dizi oluşturmak için kullanılır.
* **random:** rastgele sayılar üretmek için kullanılır


```python
a = np.zeros((2,3))
print('np.zeros((2,3)= \n{}\n'.format(a))

b = np.ones((2,3))
print('np.ones((2,3))= \n{}\n'.format(b))

c = np.empty((2,3))
print('np.empty((2,3))= \n{}\n'.format(c))

d = np.arange(1, 2, 0.3)
print('np.arange(1, 2, 0.3)= \n{}\n'.format(d))

e = np.linspace(1, 2, 7)
print('np.linspace(1, 2, 7)= \n{}\n'.format(e))

f = np.random.random((2,3))
print('np.random.random((2,3))= \n{}\n'.format(f))
```

    np.zeros((2,3)= 
    [[0. 0. 0.]
     [0. 0. 0.]]
    
    np.ones((2,3))= 
    [[1. 1. 1.]
     [1. 1. 1.]]
    
    np.empty((2,3))= 
    [[1. 1. 1.]
     [1. 1. 1.]]
    
    np.arange(1, 2, 0.3)= 
    [1.  1.3 1.6 1.9]
    
    np.linspace(1, 2, 7)= 
    [1.         1.16666667 1.33333333 1.5        1.66666667 1.83333333
     2.        ]
    
    np.random.random((2,3))= 
    [[0.13767128 0.90433798 0.39300773]
     [0.89677942 0.56711353 0.52187677]]
    


## Boyut ve Fonksiyonlar

Bir dizi oluşturmaya ek olarak, bazı verileri tuttuktan sonra, mevcut diziyi temel alan bazı yeni veri yapıları oluşturmamız gerekebilir. Bu durumda, aşağıdaki işlevleri kullanabiliriz:

* **reshape:** varolan diziye ve belirtilen şekle dayalı yeni bir dizi oluşturmak için kullanılır.
* **vstack:** birden çok diziyi dikey yönde konumlandırmak için kullanılır (dizinin boyutları aynı olmalıdır).
* **hstack:** Birden çok diziyi yatay yönde konumlandırmak için kullanılır (dizinin boyutları aynı olmalıdır).
* **hsplit:** diziyi yatay olarak bölmek için kullanılır.
* **vsplit:** diziyi dikey olarak bölmek için kullanılır.

We'll use some examples to illustrate.

Test amaçlı birkaç veri oluşturalım.

* **zero_line:** üç tane sıfır içeren ve bir satırı bulunan bir dizi
* **one_column:** üç tane bir içeren ve bir sütunu bulunan bir dizi
* **a:** iki satır ve üç sütun içeren bir matris.
* **b:** [11,20] aralığında bir tamsayı dizisi.


```python
zero_line = np.zeros((1,3))
one_column = np.ones((3,1))
print("zero_line = \n{}\n".format(zero_line))
print("one_column = \n{}\n".format(one_column))

a = np.array([(1,2,3), (4,5,6)])
b = np.arange(11, 20)
print("a = \n{}\n".format(a))
print("b = \n{}\n".format(b))
```

    zero_line = 
    [[0. 0. 0.]]
    
    one_column = 
    [[1.]
     [1.]
     [1.]]
    
    a = 
    [[1 2 3]
     [4 5 6]]
    
    b = 
    [11 12 13 14 15 16 17 18 19]
    


B dizisi başlangıçta tek boyutlu bir dizidir ve yeniden şekillendirme yöntemiyle 3 satırlık ve 3 sütunluk bir matris haline dönüştürdük.


```python
b = b.reshape(3, -1)
print("b.reshape(3, -1) = \n{}\n".format(b))
```

    b.reshape(3, -1) = 
    [[11 12 13]
     [14 15 16]
     [17 18 19]]
    


Buradaki ikinci parametre -1 olarak ayarlanır, bu da gerçek koşullara göre otomatik olarak belirleneceği anlamına gelir. Dizi aslen 9 element içerdiğinden, yeniden boyutlandırıldıktan sonraki matris 3X3'tür. Kod çıkışı aşağıdaki gibidir:


```python
b.reshape(3, -1)
```




    array([[11, 12, 13],
           [14, 15, 16],
           [17, 18, 19]])



Ardından, üç diziyi vstack işlevi aracılığıyla dikey olarak tutacağız:


```python
c = np.vstack((a, b, zero_line))
print("c = np.vstack((a,b, zero_line)) = \n{}\n".format(c))
```

    c = np.vstack((a,b, zero_line)) = 
    [[ 1.  2.  3.]
     [ 4.  5.  6.]
     [11. 12. 13.]
     [14. 15. 16.]
     [17. 18. 19.]
     [ 0.  0.  0.]]
    


Benzer şekilde, hstack'ı yatay işlemi için de kullanabiliriz. Bu sefer ilk önce dizinin yapısını ayarlamamız gerekiyor:


```python
a = a.reshape(3, 2)
print("a.reshape(3, 2) = \n{}\n".format(a))

d = np.hstack((a, b, one_column))
print("d = np.hstack((a,b, one_column)) = \n{}\n".format(d))
```

    a.reshape(3, 2) = 
    [[1 2]
     [3 4]
     [5 6]]
    
    d = np.hstack((a,b, one_column)) = 
    [[ 1.  2. 11. 12. 13.  1.]
     [ 3.  4. 14. 15. 16.  1.]
     [ 5.  6. 17. 18. 19.  1.]]
    


Sonra, ayırma işlemine bir göz atalım. İlk önce d dizisini yatay yönde üç diziye böldük.


```python
e = np.hsplit(d, 3)
print("e = np.hsplit(d, 3) = \n{}\n".format(e))
print("e[1] = \n{}\n".format(e[1]))
```

    e = np.hsplit(d, 3) = 
    [array([[1., 2.],
           [3., 4.],
           [5., 6.]]), array([[11., 12.],
           [14., 15.],
           [17., 18.]]), array([[13.,  1.],
           [16.,  1.],
           [19.,  1.]])]
    
    e[1] = 
    [[11. 12.]
     [14. 15.]
     [17. 18.]]
    


Diziyi eşit olarak bölmek için sayı belirlemeye ek olarak, bölünecek sütun sayısını da belirtebiliriz. Aşağıdaki, d dizisini ilk sütundan ve üçüncü sütundan bölme işlemini gerçekleştiriyoruz.


```python
f = np.hsplit(d, (1, 3))
print("f = np.hsplit(d, (1, 3)) = \n{}\n".format(f))
```

    f = np.hsplit(d, (1, 3)) = 
    [array([[1.],
           [3.],
           [5.]]), array([[ 2., 11.],
           [ 4., 14.],
           [ 6., 17.]]), array([[12., 13.,  1.],
           [15., 16.,  1.],
           [18., 19.,  1.]])]
    


Son olarak, d dizisini dikey yönde böldük. Benzer şekilde, belirtilen sayı dizisinin eşit şekilde bölünmesini sağlayamayız çünkü boyutları eşit değil.


```python
g = np.vsplit(d, 3)
print("np.hsplit(d, 2) = \n{}\n".format(g))

# np.vsplit(d, 2) # ValueError: array split does not result in an equal division
```

    np.hsplit(d, 2) = 
    [array([[ 1.,  2., 11., 12., 13.,  1.]]), array([[ 3.,  4., 14., 15., 16.,  1.]]), array([[ 5.,  6., 17., 18., 19.,  1.]])]
    


## İndeks

NumPy dizisindeki verilere nasıl erişildiğine bakalım.

Yine, test için bir boyutlu bir dizi oluşturalım. İçeriği [100,200) aralığında bir tamsayıdır.

Basit bir şekilde verilere erişebilmemiz için array_adi[indis numarası] yapısını kullanacağız.


```python
base_data = np.arange(100, 200)
print("base_data\n={}\n".format(base_data))

print("base_data[10] = {}\n".format(base_data[10]))
```

    base_data
    =[100 101 102 103 104 105 106 107 108 109 110 111 112 113 114 115 116 117
     118 119 120 121 122 123 124 125 126 127 128 129 130 131 132 133 134 135
     136 137 138 139 140 141 142 143 144 145 146 147 148 149 150 151 152 153
     154 155 156 157 158 159 160 161 162 163 164 165 166 167 168 169 170 171
     172 173 174 175 176 177 178 179 180 181 182 183 184 185 186 187 188 189
     190 191 192 193 194 195 196 197 198 199]
    
    base_data[10] = 110
    


NumPy'da daha önceden oluşturduğumuz bir dizi için filtreleme işlemini gerçekleştirebiliriz. Burada beş ve beşin katı olan sayılar getirildi.


```python
every_five = np.arange(0, 100, 5)
print("base_data[every_five] = \n{}\n".format(
    base_data[every_five]))
```

    base_data[every_five] = 
    [100 105 110 115 120 125 130 135 140 145 150 155 160 165 170 175 180 185
     190 195]
    



```python
a = np.array([(1,2), (10,20)])
print("a = \n{}\n".format(a))
print("base_data[a] = \n{}\n".format(base_data[a]))
```

    a = 
    [[ 1  2]
     [10 20]]
    
    base_data[a] = 
    [[101 102]
     [110 120]]
    


Yukarıda 2X2 boyutunda olan çıktıyı 10X10 boyutunda aşağıdaki gibi elde ediyoruz.


```python
base_data2 = base_data.reshape(10, -1)
print("base_data2 = np.reshape(base_data, (10, -1)) = \n{}\n".format(base_data2))
```

    base_data2 = np.reshape(base_data, (10, -1)) = 
    [[100 101 102 103 104 105 106 107 108 109]
     [110 111 112 113 114 115 116 117 118 119]
     [120 121 122 123 124 125 126 127 128 129]
     [130 131 132 133 134 135 136 137 138 139]
     [140 141 142 143 144 145 146 147 148 149]
     [150 151 152 153 154 155 156 157 158 159]
     [160 161 162 163 164 165 166 167 168 169]
     [170 171 172 173 174 175 176 177 178 179]
     [180 181 182 183 184 185 186 187 188 189]
     [190 191 192 193 194 195 196 197 198 199]]
    


İki boyutlu bir dizi için,

* Eğer sadece satır belirtirsek sadece o satırda bulunan elemanlar gelir.
* Eğer hem satır hem de sütun belirtirsek sadece belirtilen eleman gelir.
* Son öğeye "-1" ile erişebiliriz.


```python
print("base_data2[2] = \n{}\n".format(base_data2[2]))
print("base_data2[2, 3] = \n{}\n".format(base_data2[2, 3]))
print("base_data2[-1, -1] = \n{}\n".format(base_data2[-1, -1]))
```

    base_data2[2] = 
    [120 121 122 123 124 125 126 127 128 129]
    
    base_data2[2, 3] = 
    123
    
    base_data2[-1, -1] = 
    199
    


Ek olarak, kapsamı ":" ile belirtebiliriz, örneğin: 2:5. Yalnızca ":" yazmak tam kapsamı belirtir.

Lütfen aşağıdaki kodu inceleyin:

* ikinci satırın tüm elemanlarını getir.
* üçüncü sütunun bütün elemanlarını getir.
* satır numarası iki olan ve sütun numarası beş olan ve aynı zamanda satır numarası iki olan ve sütun numarası beş olan elemanları getir.


```python
print("base_data2[2, :]] = \n{}\n".format(base_data2[2, :]))
print("base_data2[:, 3]] = \n{}\n".format(base_data2[:, 3]))
print("base_data2[2:5, 2:4]] = \n{}\n".format(base_data2[2:5, 2:4]))
```

    base_data2[2, :]] = 
    [120 121 122 123 124 125 126 127 128 129]
    
    base_data2[:, 3]] = 
    [103 113 123 133 143 153 163 173 183 193]
    
    base_data2[2:5, 2:4]] = 
    [[122 123]
     [132 133]
     [142 143]]
    


## Matematiksel İşlevler

NumPy'de ayrıca birçok matematiksel işlev mevcuttur. İşte bazı örnekler;


```python
base_data = (np.random.random((5, 5)) - 0.5) * 100
print("base_data = \n{}\n".format(base_data))

print("np.amin(base_data) = {}".format(np.amin(base_data)))
print("np.amax(base_data) = {}".format(np.amax(base_data)))
print("np.average(base_data) = {}".format(np.average(base_data)))
print("np.sum(base_data) = {}".format(np.sum(base_data)))
print("np.sin(base_data) = \n{}".format(np.sin(base_data)))
```

    base_data = 
    [[-24.02118448  38.70903889 -34.35956793  31.15984863 -16.3851276 ]
     [ 18.00896965  40.12647579 -18.77313246 -19.6817189   49.0027422 ]
     [ 36.18306188 -44.80584945 -37.19340083 -34.07989665  -4.8155779 ]
     [  8.98118218   0.67046207  -2.53116377 -29.06968423   7.50321075]
     [ -9.03445665 -19.03624479 -48.60902452 -14.77772175  -7.25167879]]
    
    np.amin(base_data) = -48.60902452032344
    np.amax(base_data) = 49.00274219960913
    np.average(base_data) = -5.363217545890414
    np.sum(base_data) = -134.08043864726037
    np.sin(base_data) = 
    [[ 0.89638983  0.84679304 -0.19666101 -0.25328831  0.62658556]
     [-0.7450343   0.65503482  0.07634909 -0.73938939 -0.95292478]
     [-0.99850179 -0.73356466  0.48442958 -0.45966907  0.99468075]
     [ 0.42918999  0.6213481  -0.57321894  0.71410891  0.9391081 ]
     [-0.38048558 -0.18560632  0.99633329 -0.80176431 -0.82403314]]



```python
arr = np.arange(1,20)
arr = arr * arr              #Her eleman kendisi ile çarpılacak
print("Multpiles: ",arr)
arr = arr - arr              #Her eleman kendisinden çıkarılacak
print("Substracts: ",arr)
arr = np.arange(1,20)
arr = arr + arr              #Her eleman kendisi ile toplanacak
print("Add: ",arr)
arr = arr / arr              #Her eleman kendisine bölünecek
print("Divide: ",arr)
arr = np.arange(1,20)
arr = arr + 50
print("Add +50: ",arr)
```

    Multpiles:  [  1   4   9  16  25  36  49  64  81 100 121 144 169 196 225 256 289 324
     361]
    Substracts:  [0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0]
    Add:  [ 2  4  6  8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38]
    Divide:  [1. 1. 1. 1. 1. 1. 1. 1. 1. 1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
    Add +50:  [51 52 53 54 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69]



```python
print("Sqrt: ",np.sqrt(arr))   #Her elemanın karekökü alınacak
print("Exp: ",np.exp(arr))     #Her elemanın üsteli alınacak
print("Sin: ",np.sin(arr))     #Her elemanın sin değeri alınacak
print("Cos: ",np.cos(arr))     #Her elemanın kosinüs değeri alınacak
print("Log: ",np.log(arr))     #Her elemanın logaritması alınacak
print("Sum: ",np.sum(arr))     #Dizideki bütün elemanların toplamı
print("Std: ",np.std(arr))     #Dizinin standart sapma değeri
```

    Sqrt:  [7.14142843 7.21110255 7.28010989 7.34846923 7.41619849 7.48331477
     7.54983444 7.61577311 7.68114575 7.74596669 7.81024968 7.87400787
     7.93725393 8.         8.06225775 8.1240384  8.18535277 8.24621125
     8.30662386]
    Exp:  [1.40934908e+22 3.83100800e+22 1.04137594e+23 2.83075330e+23
     7.69478527e+23 2.09165950e+24 5.68572000e+24 1.54553894e+25
     4.20121040e+25 1.14200739e+26 3.10429794e+26 8.43835667e+26
     2.29378316e+27 6.23514908e+27 1.69488924e+28 4.60718663e+28
     1.25236317e+29 3.40427605e+29 9.25378173e+29]
    Sin:  [ 0.67022918  0.98662759  0.39592515 -0.55878905 -0.99975517 -0.521551
      0.43616476  0.99287265  0.63673801 -0.30481062 -0.96611777 -0.7391807
      0.1673557   0.92002604  0.82682868 -0.02655115 -0.85551998 -0.89792768
     -0.11478481]
    Cos:  [ 0.7421542  -0.16299078 -0.91828279 -0.82930983  0.02212676  0.85322011
      0.89986683  0.11918014 -0.77108022 -0.95241298 -0.25810164  0.67350716
      0.98589658  0.39185723 -0.56245385 -0.99964746 -0.5177698   0.44014302
      0.99339038]
    Log:  [3.93182563 3.95124372 3.97029191 3.98898405 4.00733319 4.02535169
     4.04305127 4.06044301 4.07753744 4.09434456 4.11087386 4.12713439
     4.14313473 4.15888308 4.17438727 4.18965474 4.20469262 4.21950771
     4.2341065 ]
    Sum:  1140
    Std:  5.477225575051661


## Matris

Şimdi, NumPy'nin matris şeklinde nasıl kullanılacağına bakalım.

İlk önce 5X5 boyutunda rastgele bir tamsayı matrisi oluşturalım. Bir matrisin transpoze elde edilmesinin iki yolu vardır: **.T** veya **transpose** fonksiyonu. Ek olarak, matris **nokta** işlevi ile çarpılabilir. Örnek kod aşağıdaki gibidir:


```python
base_data = np.floor((np.random.random((5, 5)) - 0.5) * 100)
print("base_data = \n{}\n".format(base_data))

print("base_data.T = \n{}\n".format(base_data.T))
print("base_data.transpose() = \n{}\n".format(base_data.transpose()))

matrix_one = np.ones((5, 5))
print("matrix_one = \n{}\n".format(matrix_one))

minus_one = np.dot(matrix_one, -1)
print("minus_one = \n{}\n".format(minus_one))

print("np.dot(base_data, minus_one) = \n{}\n".format(
    np.dot(base_data, minus_one)))
```

    base_data = 
    [[ -6.  33. -15.  22.  36.]
     [-35. -22. -45.  -5. -48.]
     [-35.   9.  42.  43. -26.]
     [ 46.  30.  41. -22. -18.]
     [ 20.  17. -15.  18. -34.]]
    
    base_data.T = 
    [[ -6. -35. -35.  46.  20.]
     [ 33. -22.   9.  30.  17.]
     [-15. -45.  42.  41. -15.]
     [ 22.  -5.  43. -22.  18.]
     [ 36. -48. -26. -18. -34.]]
    
    base_data.transpose() = 
    [[ -6. -35. -35.  46.  20.]
     [ 33. -22.   9.  30.  17.]
     [-15. -45.  42.  41. -15.]
     [ 22.  -5.  43. -22.  18.]
     [ 36. -48. -26. -18. -34.]]
    
    matrix_one = 
    [[1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]]
    
    minus_one = 
    [[-1. -1. -1. -1. -1.]
     [-1. -1. -1. -1. -1.]
     [-1. -1. -1. -1. -1.]
     [-1. -1. -1. -1. -1.]
     [-1. -1. -1. -1. -1.]]
    
    np.dot(base_data, minus_one) = 
    [[-70. -70. -70. -70. -70.]
     [155. 155. 155. 155. 155.]
     [-33. -33. -33. -33. -33.]
     [-77. -77. -77. -77. -77.]
     [ -6.  -6.  -6.  -6.  -6.]]
    


## Rastgele Sayı Üretmek

Numpy.random paketi rastgele sayılar için bir takım algoritmalar içerir. Burada en yaygın dört kullanım listelenmiştir:

Bu dört kullanım şu şekildedir;

* Her biri **[0.0, 1.0)** arasında olan 20 rasgele sayı üretmek için.
* Belirtilen **şekle** bağlı olarak rasgele bir sayı oluşturmak için.
* Belirtilen aralıktaki belirli bir sayıyı adedi kadar sayı üretebilmek için.
* Var olan verilerin sırasını bozmak için.


```python
print("random: {}\n".format(np.random.random(20)));

print("rand: {}\n".format(np.random.rand(3, 4)));

print("randint: {}\n".format(np.random.randint(0, 100, 20)));

print("permutation: {}\n".format(np.random.permutation(np.arange(20))));
```

    random: [0.97591459 0.70963244 0.71274272 0.9052036  0.8276741  0.90969397
     0.81121699 0.41986093 0.94351019 0.98516341 0.50522794 0.30265514
     0.87921027 0.41402905 0.27851685 0.07824987 0.20212265 0.71857348
     0.85119351 0.51447833]
    
    rand: [[0.56123578 0.45788863 0.51853179 0.91962668]
     [0.60568674 0.8469316  0.94220325 0.80376898]
     [0.80604184 0.40306272 0.72154831 0.53511804]]
    
    randint: [39 68 74 55 48  9 46 71 48 56  7  6 78 63 41 15 67 85 16 51]
    
    permutation: [ 8  0  3 14 15 17  1  9 12 13 11 16 10  7 19  2  4 18  6  5]
    


> Son Güncelleme: 28 Aralık 2019 - Cumartesi
