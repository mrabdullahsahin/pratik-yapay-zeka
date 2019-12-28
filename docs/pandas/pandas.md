# **Pandas**

Pandas, Python programlama dili için yüksek performanslı, kullanımı kolay veri yapıları ve veri analizi araçları sağlayan açık kaynaklı, BSD lisanslı bir kütüphanedir.

Pandas, NumFOCUS tarafından destelenmektedir.

## **Kütüphaneyi Tanımlama**


```python
import numpy as np # lineer cebir
import pandas as pd # pandas kütüphanesi tanımlanıyor
```

## **Pandas Veri Türleri**

Pandas'ta iki tür veri yapısı vardır. Bunlar seri(series) ve veri çerçevesidir(dataframe).

### **Seriler(Series)** 

Seri, tek boyutlu etiketli bir dizidir. İçinde her türlü veriyi barındırabilir.


```python
mySeries = pd.Series([3,-5,7,4], index=['a','b','c','d'])
type(mySeries)
```




    pandas.core.series.Series



### **Veri Çerçevesi(DataFrame)**

Veri çerçevesi(dataframe) iki boyutlu bir veri yapısıdır. Sütunları içerir. Bu eserde veri çevçevesi olarak adlandırmak yerine dataframe olarak kullanacağız bilginiz olsun.


```python
data = {'Country' : ['Belgium', 'India', 'Brazil' ],
        'Capital': ['Brussels', 'New Delhi', 'Brassilia'],
        'Population': [1234,1234,1234]}
datas = pd.DataFrame(data, columns=['Country','Capital','Population'])
print(type(data))
print(type(datas))
```

    <class 'dict'>
    <class 'pandas.core.frame.DataFrame'>


## **Verileri İçeri Aktarma**

Pandas ile CSV, Excel ve SQL veritabanlarını açabiliriz.

### **CSV(Comma Separated Values / Virgülle Ayrılmış Değerler)**

CSV dosyalarını açıp okumak ve CSV dosyasının üzerine yazmak çok kolaydır.


```python
df = pd.read_csv('../datas/DJIA_table.csv')
type(df)
# Python dosyanız CSV dosyanızla aynı klasörde değilse, bunu aşağıdaki gibi yapmalısınız.
# df = pd.read_csv('/home/desktop/Iris.csv')
```




    pandas.core.frame.DataFrame



### **Excel**

Excel dosyalarıyla çalışmak istediğimizde, aşağıdaki kodu yazmamız gerekir.


```python
# pd.read_excel('dosyaadi')
# pd.to_excel('dir/dataFrame.xlsx', sheet_name='Sheet1')
```

### **Diğer dosya türleri (json, SQL, table, html)**


```python
# pd.read_sql(query,connection_object) -> Bir SQL tablosundan/veritabanından verileri okur.
# pd.read_table(filename) -> Sınırlandırılmış bir metin dosyasından (TSV gibi) okur.
# pd.read_json(json_string) -> Bir json formatlı dize, URL veya dosyadan okur.
# pd.read_html(url) -> Bir html URL'sini, dizgiyi veya dosyayı ayrıştırır ve tabloları dataframe listesine çıkarır.
# pd.read_clipboard() -> Panonuzun içeriğini alır ve onu read_table () öğesine iletir.
# pd.DataFrame(dict) -> Bir sözlükten, sütun adlarına ilişkin verileri, listeler halinde okur.
```

## **Veriyi Dışarı Aktarma** 


```python
# df.to_csv(filename) -> CSV dosyası halinde dışarı aktarır.
# df.to_excel(filename) -> Excel dosyası halinde dışarı aktarır.
# df.to_sql(table_name, connection_object) -> SQL tablosu halinde dışarı aktarır.
# df.to_json(filename) -> JSON halinde dışarı aktarır.
# df.to_html(filename) -> HTML tablosu halinde dışarı aktarır.
# df.to_clipboard() -> Clipboard halinde dışarı aktarır.
```

## **Test Verilerini Oluşturmak**


```python
pd.DataFrame(np.random.rand(20,5)) 
# 5 sütun ve 20 satırı bulunan rastgele kayan noktalı(float) sayılardan oluşan bir dataframe oluşturur.
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.881674</td>
      <td>0.656281</td>
      <td>0.530675</td>
      <td>0.701284</td>
      <td>0.745154</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.967789</td>
      <td>0.361502</td>
      <td>0.516868</td>
      <td>0.363684</td>
      <td>0.692905</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.020186</td>
      <td>0.246136</td>
      <td>0.276501</td>
      <td>0.156050</td>
      <td>0.610562</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.978084</td>
      <td>0.771438</td>
      <td>0.357285</td>
      <td>0.216900</td>
      <td>0.605728</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.470992</td>
      <td>0.136826</td>
      <td>0.025263</td>
      <td>0.513115</td>
      <td>0.355362</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0.037611</td>
      <td>0.968741</td>
      <td>0.148456</td>
      <td>0.219907</td>
      <td>0.811352</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0.405742</td>
      <td>0.105569</td>
      <td>0.316834</td>
      <td>0.546320</td>
      <td>0.783297</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0.388317</td>
      <td>0.875504</td>
      <td>0.483557</td>
      <td>0.115927</td>
      <td>0.220484</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0.181219</td>
      <td>0.213682</td>
      <td>0.188712</td>
      <td>0.017624</td>
      <td>0.993905</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0.454112</td>
      <td>0.676238</td>
      <td>0.465122</td>
      <td>0.823352</td>
      <td>0.728502</td>
    </tr>
    <tr>
      <th>10</th>
      <td>0.614288</td>
      <td>0.148511</td>
      <td>0.097686</td>
      <td>0.474665</td>
      <td>0.277006</td>
    </tr>
    <tr>
      <th>11</th>
      <td>0.603164</td>
      <td>0.677704</td>
      <td>0.480384</td>
      <td>0.990380</td>
      <td>0.094366</td>
    </tr>
    <tr>
      <th>12</th>
      <td>0.226657</td>
      <td>0.818445</td>
      <td>0.226504</td>
      <td>0.872379</td>
      <td>0.142988</td>
    </tr>
    <tr>
      <th>13</th>
      <td>0.200353</td>
      <td>0.040381</td>
      <td>0.791361</td>
      <td>0.142564</td>
      <td>0.729426</td>
    </tr>
    <tr>
      <th>14</th>
      <td>0.347076</td>
      <td>0.187979</td>
      <td>0.129819</td>
      <td>0.004997</td>
      <td>0.918674</td>
    </tr>
    <tr>
      <th>15</th>
      <td>0.905068</td>
      <td>0.607013</td>
      <td>0.319787</td>
      <td>0.798406</td>
      <td>0.493602</td>
    </tr>
    <tr>
      <th>16</th>
      <td>0.373228</td>
      <td>0.960043</td>
      <td>0.783589</td>
      <td>0.084993</td>
      <td>0.740864</td>
    </tr>
    <tr>
      <th>17</th>
      <td>0.407283</td>
      <td>0.617893</td>
      <td>0.734941</td>
      <td>0.895326</td>
      <td>0.096390</td>
    </tr>
    <tr>
      <th>18</th>
      <td>0.797779</td>
      <td>0.611200</td>
      <td>0.668267</td>
      <td>0.349107</td>
      <td>0.754915</td>
    </tr>
    <tr>
      <th>19</th>
      <td>0.029135</td>
      <td>0.871738</td>
      <td>0.030545</td>
      <td>0.048413</td>
      <td>0.582861</td>
    </tr>
  </tbody>
</table>
</div>



## **Veriyi Özetleme**

Pandas ile veriler hakkında bilgi almak kolaydır. Pandas içerisinde bulunan fonksiyonları tek tek inceleyelim.

### **df.info()** 

Bu Kod verilerimiz hakkında detaylı bilgi sunar.

* **RangeIndex:** Kaç tane veri olduğunu belirtir.
* **Data Columns:** Kaç tane sütun bulunduğunu belirtir.
* **Columns:** Sütunlar hakkında bilgi verir.
* **dtypes:** Ne tür verilerimizin olduğunu ve bu verilerden kaç tane bulunduğunu belirtir.
* **Memory Usage:** Hafıza kullanımının ne kadar olduğunu gösterir.


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1989 entries, 0 to 1988
    Data columns (total 7 columns):
    Date         1989 non-null object
    Open         1989 non-null float64
    High         1989 non-null float64
    Low          1989 non-null float64
    Close        1989 non-null float64
    Volume       1989 non-null int64
    Adj Close    1989 non-null float64
    dtypes: float64(5), int64(1), object(1)
    memory usage: 108.9+ KB


### **df.shape()**

Bu kod bize satır ve sütun sayısını gösterir.


```python
df.shape
```




    (1989, 7)



### **df.index** 

Bu kod bulunan toplam indeks sayısını gösterir.


```python
df.index
```




    RangeIndex(start=0, stop=1989, step=1)



### **df.columns** 

Bu kod, incelediğimiz verilerdeki tüm sütunları gösterir.


```python
df.columns
```




    Index(['Date', 'Open', 'High', 'Low', 'Close', 'Volume', 'Adj Close'], dtype='object')



### **df.count()**

Bu kod bize her sütunda kaç tane veri olduğunu gösterir.


```python
df.count()
```




    Date         1989
    Open         1989
    High         1989
    Low          1989
    Close        1989
    Volume       1989
    Adj Close    1989
    dtype: int64



### **df.sum()**

Bu kod bize her sütundaki verinin toplamını gösterir.


```python
df.sum()
```




    Date         2016-07-012016-06-302016-06-292016-06-282016-0...
    Open                                               2.67702e+07
    High                                               2.69337e+07
    Low                                                2.65988e+07
    Close                                               2.6778e+07
    Volume                                            323831020000
    Adj Close                                           2.6778e+07
    dtype: object



### **df.cumsum()**

Bu kod bize verilerin kümülatif toplamını verir.


```python
df.cumsum().head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.2</td>
      <td>18002.4</td>
      <td>17916.9</td>
      <td>17949.4</td>
      <td>82160000</td>
      <td>17949.4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-07-012016-06-30</td>
      <td>35637</td>
      <td>35933</td>
      <td>35628.7</td>
      <td>35879.4</td>
      <td>215190000</td>
      <td>35879.4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-07-012016-06-302016-06-29</td>
      <td>53093</td>
      <td>53637.5</td>
      <td>53084.7</td>
      <td>53574</td>
      <td>321570000</td>
      <td>53574</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-07-012016-06-302016-06-292016-06-28</td>
      <td>70283.5</td>
      <td>71047.2</td>
      <td>70275.2</td>
      <td>70983.8</td>
      <td>433760000</td>
      <td>70983.8</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-07-012016-06-302016-06-292016-06-282016-0...</td>
      <td>87638.7</td>
      <td>88402.4</td>
      <td>87338.3</td>
      <td>88124</td>
      <td>572500000</td>
      <td>88124</td>
    </tr>
  </tbody>
</table>
</div>



### **df.min()**

Bu kod verilerimiz içinde bulunan en küçüğünü değeri getirir.


```python
df.min()
```




    Date         2008-08-08
    Open            6547.01
    High            6709.61
    Low             6469.95
    Close           6547.05
    Volume          8410000
    Adj Close       6547.05
    dtype: object



### **df.max()**

Bu kod verilerimiz içinde bulunan en büyük değeri getirir.


```python
df.max()
```




    Date         2016-07-01
    Open            18315.1
    High            18351.4
    Low             18272.6
    Close           18312.4
    Volume        674920000
    Adj Close       18312.4
    dtype: object



### **idxmin()**

Bu kod verideki en küçük değeri getirir. Seri ve dataframe üzerindeki kullanım farklıdır.


```python
print("df: ",df['Open'].idxmin())
print("series", mySeries.idxmin())
```

    df:  1842
    series b


### **idxmax()**

Bu kod verilerdeki en büyük değeri döndürür.


```python
print("df: ",df['Open'].idxmax())
print("series: ",mySeries.idxmax())
```

    df:  282
    series:  c


### **df.describe()**

Bu kod verilerle ilgili temel istatistiksel bilgileri sağlar. Sayısal değerlere sahip sütunlar için geçerlidir.

* **count:** verilerin sayısını verir.
* **mean:** verilerin ortalamasını verir.
* **std:** verilerin standart sapmasını verir.
* **min:** en küçük veriyi verir.
* **25%:** birinci dörttebirlik
* **50%:** ortanca veya ikinci dörttebirlik
* **75%:** üçüncü dörttebirlik
* **max:** en büyük veriyi verir.


```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1989.000000</td>
      <td>1989.000000</td>
      <td>1989.000000</td>
      <td>1989.000000</td>
      <td>1.989000e+03</td>
      <td>1989.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>13459.116048</td>
      <td>13541.303173</td>
      <td>13372.931728</td>
      <td>13463.032255</td>
      <td>1.628110e+08</td>
      <td>13463.032255</td>
    </tr>
    <tr>
      <th>std</th>
      <td>3143.281634</td>
      <td>3136.271725</td>
      <td>3150.420934</td>
      <td>3144.006996</td>
      <td>9.392343e+07</td>
      <td>3144.006996</td>
    </tr>
    <tr>
      <th>min</th>
      <td>6547.009766</td>
      <td>6709.609863</td>
      <td>6469.950195</td>
      <td>6547.049805</td>
      <td>8.410000e+06</td>
      <td>6547.049805</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>10907.339844</td>
      <td>11000.980469</td>
      <td>10824.759766</td>
      <td>10913.379883</td>
      <td>1.000000e+08</td>
      <td>10913.379883</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>13022.049805</td>
      <td>13088.110352</td>
      <td>12953.129883</td>
      <td>13025.580078</td>
      <td>1.351700e+08</td>
      <td>13025.580078</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>16477.699219</td>
      <td>16550.070312</td>
      <td>16392.769531</td>
      <td>16478.410156</td>
      <td>1.926000e+08</td>
      <td>16478.410156</td>
    </tr>
    <tr>
      <th>max</th>
      <td>18315.060547</td>
      <td>18351.359375</td>
      <td>18272.560547</td>
      <td>18312.390625</td>
      <td>6.749200e+08</td>
      <td>18312.390625</td>
    </tr>
  </tbody>
</table>
</div>



### **df.mean()**

Bu kod, sayısal sütunlar için ortalama değerini gösterir.


```python
df.mean()
```




    Open         1.345912e+04
    High         1.354130e+04
    Low          1.337293e+04
    Close        1.346303e+04
    Volume       1.628110e+08
    Adj Close    1.346303e+04
    dtype: float64



### **df.median()**

Bu kod, sayısal değerlere sahip sütunlar için medyan değerini gösterir.


```python
df.median()
```




    Open         1.302205e+04
    High         1.308811e+04
    Low          1.295313e+04
    Close        1.302558e+04
    Volume       1.351700e+08
    Adj Close    1.302558e+04
    dtype: float64



### **df.quantile([0.25,0.75])**

Bu kod, her sütun için sütunların 0.25 ve 0.75 değerlerini hesaplar.


```python
df.quantile([0.25,0.75])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0.25</th>
      <td>10907.339844</td>
      <td>11000.980469</td>
      <td>10824.759766</td>
      <td>10913.379883</td>
      <td>100000000.0</td>
      <td>10913.379883</td>
    </tr>
    <tr>
      <th>0.75</th>
      <td>16477.699219</td>
      <td>16550.070312</td>
      <td>16392.769531</td>
      <td>16478.410156</td>
      <td>192600000.0</td>
      <td>16478.410156</td>
    </tr>
  </tbody>
</table>
</div>



### **df.var()**

Bu kod, her sütun için varyans değerini hesaplar.


```python
df.var()
```




    Open         9.880219e+06
    High         9.836200e+06
    Low          9.925152e+06
    Close        9.884780e+06
    Volume       8.821610e+15
    Adj Close    9.884780e+06
    dtype: float64



### **df.std()**

Bu kod, sayısal olan her sütun için standart sapma değerini hesaplar.


```python
df.std()
```




    Open         3.143282e+03
    High         3.136272e+03
    Low          3.150421e+03
    Close        3.144007e+03
    Volume       9.392343e+07
    Adj Close    3.144007e+03
    dtype: float64



### **df.cummax()**

Bu kod, veriler arasındaki toplam maksimum değeri hesaplar.


```python
df.cummax()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.2</td>
      <td>18002.4</td>
      <td>17916.9</td>
      <td>17949.4</td>
      <td>82160000</td>
      <td>17949.4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-07-01</td>
      <td>17924.2</td>
      <td>18002.4</td>
      <td>17916.9</td>
      <td>17949.4</td>
      <td>133030000</td>
      <td>17949.4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-07-01</td>
      <td>17924.2</td>
      <td>18002.4</td>
      <td>17916.9</td>
      <td>17949.4</td>
      <td>133030000</td>
      <td>17949.4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-07-01</td>
      <td>17924.2</td>
      <td>18002.4</td>
      <td>17916.9</td>
      <td>17949.4</td>
      <td>133030000</td>
      <td>17949.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-07-01</td>
      <td>17924.2</td>
      <td>18002.4</td>
      <td>17916.9</td>
      <td>17949.4</td>
      <td>138740000</td>
      <td>17949.4</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1984</th>
      <td>2016-07-01</td>
      <td>18315.1</td>
      <td>18351.4</td>
      <td>18272.6</td>
      <td>18312.4</td>
      <td>674920000</td>
      <td>18312.4</td>
    </tr>
    <tr>
      <th>1985</th>
      <td>2016-07-01</td>
      <td>18315.1</td>
      <td>18351.4</td>
      <td>18272.6</td>
      <td>18312.4</td>
      <td>674920000</td>
      <td>18312.4</td>
    </tr>
    <tr>
      <th>1986</th>
      <td>2016-07-01</td>
      <td>18315.1</td>
      <td>18351.4</td>
      <td>18272.6</td>
      <td>18312.4</td>
      <td>674920000</td>
      <td>18312.4</td>
    </tr>
    <tr>
      <th>1987</th>
      <td>2016-07-01</td>
      <td>18315.1</td>
      <td>18351.4</td>
      <td>18272.6</td>
      <td>18312.4</td>
      <td>674920000</td>
      <td>18312.4</td>
    </tr>
    <tr>
      <th>1988</th>
      <td>2016-07-01</td>
      <td>18315.1</td>
      <td>18351.4</td>
      <td>18272.6</td>
      <td>18312.4</td>
      <td>674920000</td>
      <td>18312.4</td>
    </tr>
  </tbody>
</table>
<p>1989 rows × 7 columns</p>
</div>



### **df.cummin()**

Bu kod verinin toplam minimum değerini verir.


```python
df.cummin()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.2</td>
      <td>18002.4</td>
      <td>17916.9</td>
      <td>17949.4</td>
      <td>82160000</td>
      <td>17949.4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.8</td>
      <td>17930.6</td>
      <td>17711.8</td>
      <td>17930</td>
      <td>82160000</td>
      <td>17930</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456</td>
      <td>17704.5</td>
      <td>17456</td>
      <td>17694.7</td>
      <td>82160000</td>
      <td>17694.7</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.5</td>
      <td>17409.7</td>
      <td>17190.5</td>
      <td>17409.7</td>
      <td>82160000</td>
      <td>17409.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>17190.5</td>
      <td>17355.2</td>
      <td>17063.1</td>
      <td>17140.2</td>
      <td>82160000</td>
      <td>17140.2</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1984</th>
      <td>2008-08-14</td>
      <td>6547.01</td>
      <td>6709.61</td>
      <td>6469.95</td>
      <td>6547.05</td>
      <td>8410000</td>
      <td>6547.05</td>
    </tr>
    <tr>
      <th>1985</th>
      <td>2008-08-13</td>
      <td>6547.01</td>
      <td>6709.61</td>
      <td>6469.95</td>
      <td>6547.05</td>
      <td>8410000</td>
      <td>6547.05</td>
    </tr>
    <tr>
      <th>1986</th>
      <td>2008-08-12</td>
      <td>6547.01</td>
      <td>6709.61</td>
      <td>6469.95</td>
      <td>6547.05</td>
      <td>8410000</td>
      <td>6547.05</td>
    </tr>
    <tr>
      <th>1987</th>
      <td>2008-08-11</td>
      <td>6547.01</td>
      <td>6709.61</td>
      <td>6469.95</td>
      <td>6547.05</td>
      <td>8410000</td>
      <td>6547.05</td>
    </tr>
    <tr>
      <th>1988</th>
      <td>2008-08-08</td>
      <td>6547.01</td>
      <td>6709.61</td>
      <td>6469.95</td>
      <td>6547.05</td>
      <td>8410000</td>
      <td>6547.05</td>
    </tr>
  </tbody>
</table>
<p>1989 rows × 7 columns</p>
</div>



### **df['columnName'].cumproad()**

Bu kod, verilerin toplu üretimini döndürür.


```python
df['Open'].cumprod().head()
```




    0    1.792424e+04
    1    3.174878e+08
    2    5.542073e+12
    3    9.527105e+16
    4    1.653449e+21
    Name: Open, dtype: float64



### **len(df)**

Bu kod toplam kaç adet veri olduğunu gösterir.


```python
len(df)
```




    1989



### **df.isnull()**

Boş değerleri denetler, boolean bir değer döndürür.


```python
df.isnull().head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
</div>



### **df.corr()**

Veriler arasındaki ilişki(korelasyon) hakkında bilgi verir.


```python
df.corr()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Open</th>
      <td>1.000000</td>
      <td>0.999592</td>
      <td>0.999436</td>
      <td>0.998991</td>
      <td>-0.691621</td>
      <td>0.998991</td>
    </tr>
    <tr>
      <th>High</th>
      <td>0.999592</td>
      <td>1.000000</td>
      <td>0.999373</td>
      <td>0.999546</td>
      <td>-0.686997</td>
      <td>0.999546</td>
    </tr>
    <tr>
      <th>Low</th>
      <td>0.999436</td>
      <td>0.999373</td>
      <td>1.000000</td>
      <td>0.999595</td>
      <td>-0.699572</td>
      <td>0.999595</td>
    </tr>
    <tr>
      <th>Close</th>
      <td>0.998991</td>
      <td>0.999546</td>
      <td>0.999595</td>
      <td>1.000000</td>
      <td>-0.694281</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>Volume</th>
      <td>-0.691621</td>
      <td>-0.686997</td>
      <td>-0.699572</td>
      <td>-0.694281</td>
      <td>1.000000</td>
      <td>-0.694281</td>
    </tr>
    <tr>
      <th>Adj Close</th>
      <td>0.998991</td>
      <td>0.999546</td>
      <td>0.999595</td>
      <td>1.000000</td>
      <td>-0.694281</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
</div>



## **Seçme & Filtreleme**
    
Pandas ile istediğimiz verileri nasıl seçebileceğimizi ve nasıl getirebileceğimizi öğreneceğiz.

### **mySeries['b']**

Bu kod seri içinde B değeri olan verileri döndürür.


```python
mySeries['b']
```




    -5



### **df[n:n]** 

Bu kod n'den ne'ye kadar olan verileri getir.


```python
df[1982:]
#Or
#df[5:7]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1982</th>
      <td>2008-08-18</td>
      <td>11659.650391</td>
      <td>11690.429688</td>
      <td>11434.120117</td>
      <td>11479.389648</td>
      <td>156290000</td>
      <td>11479.389648</td>
    </tr>
    <tr>
      <th>1983</th>
      <td>2008-08-15</td>
      <td>11611.209961</td>
      <td>11709.889648</td>
      <td>11599.730469</td>
      <td>11659.900391</td>
      <td>215040000</td>
      <td>11659.900391</td>
    </tr>
    <tr>
      <th>1984</th>
      <td>2008-08-14</td>
      <td>11532.070312</td>
      <td>11718.280273</td>
      <td>11450.889648</td>
      <td>11615.929688</td>
      <td>159790000</td>
      <td>11615.929688</td>
    </tr>
    <tr>
      <th>1985</th>
      <td>2008-08-13</td>
      <td>11632.809570</td>
      <td>11633.780273</td>
      <td>11453.339844</td>
      <td>11532.959961</td>
      <td>182550000</td>
      <td>11532.959961</td>
    </tr>
    <tr>
      <th>1986</th>
      <td>2008-08-12</td>
      <td>11781.700195</td>
      <td>11782.349609</td>
      <td>11601.519531</td>
      <td>11642.469727</td>
      <td>173590000</td>
      <td>11642.469727</td>
    </tr>
    <tr>
      <th>1987</th>
      <td>2008-08-11</td>
      <td>11729.669922</td>
      <td>11867.110352</td>
      <td>11675.530273</td>
      <td>11782.349609</td>
      <td>183190000</td>
      <td>11782.349609</td>
    </tr>
    <tr>
      <th>1988</th>
      <td>2008-08-08</td>
      <td>11432.089844</td>
      <td>11759.959961</td>
      <td>11388.040039</td>
      <td>11734.320312</td>
      <td>212830000</td>
      <td>11734.320312</td>
    </tr>
  </tbody>
</table>
</div>



### **df.iloc[[n],[n]]** 

Bu kod, n satırından ve n sütununa kadar olan verileri getirir.


```python
df.iloc[[0],[3]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Low</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>17916.910156</td>
    </tr>
  </tbody>
</table>
</div>



### **df.loc[n:n]**

Bu kod belirlediğimiz aralıktaki verileri getirir.


```python
#df.loc[n:]
# OR
df.loc[5:7]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>2016-06-24</td>
      <td>17946.630859</td>
      <td>17946.630859</td>
      <td>17356.339844</td>
      <td>17400.750000</td>
      <td>239000000</td>
      <td>17400.750000</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2016-06-23</td>
      <td>17844.109375</td>
      <td>18011.070312</td>
      <td>17844.109375</td>
      <td>18011.070312</td>
      <td>98070000</td>
      <td>18011.070312</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2016-06-22</td>
      <td>17832.669922</td>
      <td>17920.160156</td>
      <td>17770.359375</td>
      <td>17780.830078</td>
      <td>89440000</td>
      <td>17780.830078</td>
    </tr>
  </tbody>
</table>
</div>



### **df['columnName']** 

Bu kod ile belirttiğimiz sütunu seçip getirebiliriz.


```python
df['Open'].head()
# OR
# df.Open
```




    0    17924.240234
    1    17712.759766
    2    17456.019531
    3    17190.509766
    4    17355.210938
    Name: Open, dtype: float64



### **df['columnName'][n]**

Bu kodla istediğimiz sütunun herhangi bir değerini seçebiliriz.


```python
df['Open'][0]
# OR
# df.Open[0]
# df["Open"][1]
# df.loc[1,["Open"]]
```




    17924.240234



### **df['columnName'].nunique()**

Bu kod, seçilen sütunda bulunan verilerin kaç tanesinin tekrarlamadığını gösterir.


```python
df['Open'].nunique()
```




    1980



### **df['columnName'].unique()** 

Bu kod, seçilen sütundaki verilerden hangilerinin tekrar ettiğini gösterir.


```python
df['Open'].unique()
# We can write the above code as follows:: df.Open.unique()
```




    array([17924.240234, 17712.759766, 17456.019531, ..., 11781.700195,
           11729.669922, 11432.089844])



### **df.columnName**

Bu kod, istediğimiz sütunu seçmenin başka bir yoludur. Burada dikkat edilmesi gereken bazı husular mevcuttur. Bunlar;

- Eğer sütun adı "**sutun adi**" şeklinde ise, arada boşluk bulunduğu için bu yöntemde kullanamayız.
- Eğer sütun adında Türkçe karakter mevcut ise sorun çıkartabilir.


```python
df.Open.head()
```




    0    17924.240234
    1    17712.759766
    2    17456.019531
    3    17190.509766
    4    17355.210938
    Name: Open, dtype: float64



### **df['columnName'].value_counts(dropna =False)** 

Bu kod, belirlediğimiz sütundaki tüm verileri sayar, ancak null/none olan değerleri saymaz.


```python
print(df.Open.value_counts(dropna =True).head())
# OR
# print(df['Item'].value_counts(dropna =False))
```

    17374.779297    2
    18033.330078    2
    10309.389648    2
    17711.119141    2
    17812.250000    2
    Name: Open, dtype: int64


### **df.head(n)**

Bu kod isteğe bağlı olarak baştan sadece ilk 5 veriyi getirir. n yerine hangi rakamı yazarsak o kadar veri getirir.


```python
df.head()
# OR
# df.head(15)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.240234</td>
      <td>18002.380859</td>
      <td>17916.910156</td>
      <td>17949.369141</td>
      <td>82160000</td>
      <td>17949.369141</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.759766</td>
      <td>17930.609375</td>
      <td>17711.800781</td>
      <td>17929.990234</td>
      <td>133030000</td>
      <td>17929.990234</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456.019531</td>
      <td>17704.509766</td>
      <td>17456.019531</td>
      <td>17694.679688</td>
      <td>106380000</td>
      <td>17694.679688</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>112190000</td>
      <td>17409.720703</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>17355.210938</td>
      <td>17355.210938</td>
      <td>17063.080078</td>
      <td>17140.240234</td>
      <td>138740000</td>
      <td>17140.240234</td>
    </tr>
  </tbody>
</table>
</div>



### **df.tail(n)**

Bu kod isteğe bağlı olarak sondan sadece son 5 veriyi getirir. n yerine hangi rakamı yazarsak o kadar veri getirir.


```python
df.tail()
# OR
# df.tail(20)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1984</th>
      <td>2008-08-14</td>
      <td>11532.070312</td>
      <td>11718.280273</td>
      <td>11450.889648</td>
      <td>11615.929688</td>
      <td>159790000</td>
      <td>11615.929688</td>
    </tr>
    <tr>
      <th>1985</th>
      <td>2008-08-13</td>
      <td>11632.809570</td>
      <td>11633.780273</td>
      <td>11453.339844</td>
      <td>11532.959961</td>
      <td>182550000</td>
      <td>11532.959961</td>
    </tr>
    <tr>
      <th>1986</th>
      <td>2008-08-12</td>
      <td>11781.700195</td>
      <td>11782.349609</td>
      <td>11601.519531</td>
      <td>11642.469727</td>
      <td>173590000</td>
      <td>11642.469727</td>
    </tr>
    <tr>
      <th>1987</th>
      <td>2008-08-11</td>
      <td>11729.669922</td>
      <td>11867.110352</td>
      <td>11675.530273</td>
      <td>11782.349609</td>
      <td>183190000</td>
      <td>11782.349609</td>
    </tr>
    <tr>
      <th>1988</th>
      <td>2008-08-08</td>
      <td>11432.089844</td>
      <td>11759.959961</td>
      <td>11388.040039</td>
      <td>11734.320312</td>
      <td>212830000</td>
      <td>11734.320312</td>
    </tr>
  </tbody>
</table>
</div>



### **df.sample(n)**

Bu kod verimiz arasından rastgele n adet veri getir.


```python
df.sample(5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>515</th>
      <td>2014-06-17</td>
      <td>16779.210938</td>
      <td>16823.550781</td>
      <td>16732.910156</td>
      <td>16808.490234</td>
      <td>63530000</td>
      <td>16808.490234</td>
    </tr>
    <tr>
      <th>1425</th>
      <td>2010-11-02</td>
      <td>11125.219727</td>
      <td>11219.519531</td>
      <td>11125.219727</td>
      <td>11188.719727</td>
      <td>150390000</td>
      <td>11188.719727</td>
    </tr>
    <tr>
      <th>50</th>
      <td>2016-04-21</td>
      <td>18092.839844</td>
      <td>18107.289062</td>
      <td>17963.890625</td>
      <td>17982.519531</td>
      <td>102720000</td>
      <td>17982.519531</td>
    </tr>
    <tr>
      <th>759</th>
      <td>2013-06-27</td>
      <td>14921.280273</td>
      <td>15075.009766</td>
      <td>14921.280273</td>
      <td>15024.490234</td>
      <td>113650000</td>
      <td>15024.490234</td>
    </tr>
    <tr>
      <th>1322</th>
      <td>2011-03-31</td>
      <td>12350.759766</td>
      <td>12381.679688</td>
      <td>12319.009766</td>
      <td>12319.730469</td>
      <td>186140000</td>
      <td>12319.730469</td>
    </tr>
  </tbody>
</table>
</div>



### **df.sample(frac=0.5)**

Bu kod rastgele satırların kesirlerini seçer ve verileri bu dereceye kadar getirir.


```python
df.sample(frac=0.5).head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>151</th>
      <td>2015-11-24</td>
      <td>17770.900391</td>
      <td>17862.599609</td>
      <td>17683.509766</td>
      <td>17812.189453</td>
      <td>127170000</td>
      <td>17812.189453</td>
    </tr>
    <tr>
      <th>1421</th>
      <td>2010-11-08</td>
      <td>11439.540039</td>
      <td>11439.610352</td>
      <td>11362.530273</td>
      <td>11406.839844</td>
      <td>143990000</td>
      <td>11406.839844</td>
    </tr>
    <tr>
      <th>268</th>
      <td>2015-06-10</td>
      <td>17765.380859</td>
      <td>18045.140625</td>
      <td>17765.380859</td>
      <td>18000.400391</td>
      <td>96980000</td>
      <td>18000.400391</td>
    </tr>
    <tr>
      <th>477</th>
      <td>2014-08-11</td>
      <td>16557.269531</td>
      <td>16627.990234</td>
      <td>16557.269531</td>
      <td>16569.980469</td>
      <td>65560000</td>
      <td>16569.980469</td>
    </tr>
    <tr>
      <th>669</th>
      <td>2013-11-04</td>
      <td>15621.200195</td>
      <td>15658.900391</td>
      <td>15588.480469</td>
      <td>15639.120117</td>
      <td>71200000</td>
      <td>15639.120117</td>
    </tr>
  </tbody>
</table>
</div>



### **df.nlargest(n,'columnName')**

Bu kod, n adet en büyük değeri belirttiğimiz sütundan getirir.


```python
df.nlargest(5,'Open')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>282</th>
      <td>2015-05-20</td>
      <td>18315.060547</td>
      <td>18350.130859</td>
      <td>18272.560547</td>
      <td>18285.400391</td>
      <td>80190000</td>
      <td>18285.400391</td>
    </tr>
    <tr>
      <th>283</th>
      <td>2015-05-19</td>
      <td>18300.480469</td>
      <td>18351.359375</td>
      <td>18261.349609</td>
      <td>18312.390625</td>
      <td>87200000</td>
      <td>18312.390625</td>
    </tr>
    <tr>
      <th>280</th>
      <td>2015-05-22</td>
      <td>18286.869141</td>
      <td>18286.869141</td>
      <td>18217.140625</td>
      <td>18232.019531</td>
      <td>78890000</td>
      <td>18232.019531</td>
    </tr>
    <tr>
      <th>281</th>
      <td>2015-05-21</td>
      <td>18285.869141</td>
      <td>18314.890625</td>
      <td>18249.900391</td>
      <td>18285.740234</td>
      <td>84270000</td>
      <td>18285.740234</td>
    </tr>
    <tr>
      <th>337</th>
      <td>2015-03-03</td>
      <td>18281.949219</td>
      <td>18281.949219</td>
      <td>18136.880859</td>
      <td>18203.369141</td>
      <td>83830000</td>
      <td>18203.369141</td>
    </tr>
  </tbody>
</table>
</div>



### **df.nsmallest(n,'columnName')** 

Bu kod, n adet en küçük değeri belirttiğimiz sütundan getirir.


```python
df.nsmallest(3,'Open')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1842</th>
      <td>2009-03-10</td>
      <td>6547.009766</td>
      <td>6926.490234</td>
      <td>6546.609863</td>
      <td>6926.490234</td>
      <td>640020000</td>
      <td>6926.490234</td>
    </tr>
    <tr>
      <th>1844</th>
      <td>2009-03-06</td>
      <td>6595.160156</td>
      <td>6755.169922</td>
      <td>6469.950195</td>
      <td>6626.939941</td>
      <td>425170000</td>
      <td>6626.939941</td>
    </tr>
    <tr>
      <th>1843</th>
      <td>2009-03-09</td>
      <td>6625.740234</td>
      <td>6709.609863</td>
      <td>6516.859863</td>
      <td>6547.049805</td>
      <td>365990000</td>
      <td>6547.049805</td>
    </tr>
  </tbody>
</table>
</div>



### **df[df.columnName < 5]**

Bu kod, belirlediğimiz sütun ismindeki değerler içerisinde 5'ten küçük olanları getirir.


```python
df[df.Open > 18281.949219]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>280</th>
      <td>2015-05-22</td>
      <td>18286.869141</td>
      <td>18286.869141</td>
      <td>18217.140625</td>
      <td>18232.019531</td>
      <td>78890000</td>
      <td>18232.019531</td>
    </tr>
    <tr>
      <th>281</th>
      <td>2015-05-21</td>
      <td>18285.869141</td>
      <td>18314.890625</td>
      <td>18249.900391</td>
      <td>18285.740234</td>
      <td>84270000</td>
      <td>18285.740234</td>
    </tr>
    <tr>
      <th>282</th>
      <td>2015-05-20</td>
      <td>18315.060547</td>
      <td>18350.130859</td>
      <td>18272.560547</td>
      <td>18285.400391</td>
      <td>80190000</td>
      <td>18285.400391</td>
    </tr>
    <tr>
      <th>283</th>
      <td>2015-05-19</td>
      <td>18300.480469</td>
      <td>18351.359375</td>
      <td>18261.349609</td>
      <td>18312.390625</td>
      <td>87200000</td>
      <td>18312.390625</td>
    </tr>
  </tbody>
</table>
</div>



### **df[['columnName','columnName']]**

Bu kod, istediğimiz sütunları seçmemize ve listelemimize yarar.


```python
df[['High','Low']].head()
# df.loc[:,["High","Low"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>High</th>
      <th>Low</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>18002.380859</td>
      <td>17916.910156</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17930.609375</td>
      <td>17711.800781</td>
    </tr>
    <tr>
      <th>2</th>
      <td>17704.509766</td>
      <td>17456.019531</td>
    </tr>
    <tr>
      <th>3</th>
      <td>17409.720703</td>
      <td>17190.509766</td>
    </tr>
    <tr>
      <th>4</th>
      <td>17355.210938</td>
      <td>17063.080078</td>
    </tr>
  </tbody>
</table>
</div>



### **df.loc[:,"columnName1":"columnName2"]**

Bu kod, columnName1'den columnName2'ye kadar olan sütunları döndürür.


```python
df.loc[:,"Date":"Close"].head()
# OR
# data.loc[:3,"Date":"Close"]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.240234</td>
      <td>18002.380859</td>
      <td>17916.910156</td>
      <td>17949.369141</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.759766</td>
      <td>17930.609375</td>
      <td>17711.800781</td>
      <td>17929.990234</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456.019531</td>
      <td>17704.509766</td>
      <td>17456.019531</td>
      <td>17694.679688</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>17355.210938</td>
      <td>17355.210938</td>
      <td>17063.080078</td>
      <td>17140.240234</td>
    </tr>
  </tbody>
</table>
</div>



### **Filtre Oluştur** 


```python
filters = df.Date > '2016-06-27'
df[filters]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.240234</td>
      <td>18002.380859</td>
      <td>17916.910156</td>
      <td>17949.369141</td>
      <td>82160000</td>
      <td>17949.369141</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.759766</td>
      <td>17930.609375</td>
      <td>17711.800781</td>
      <td>17929.990234</td>
      <td>133030000</td>
      <td>17929.990234</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456.019531</td>
      <td>17704.509766</td>
      <td>17456.019531</td>
      <td>17694.679688</td>
      <td>106380000</td>
      <td>17694.679688</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>112190000</td>
      <td>17409.720703</td>
    </tr>
  </tbody>
</table>
</div>



### **df.filter(regex = 'code')**

Bu kod, regex yapısını kullanarak istediğimiz şekilde filtreleme işlemi yapmamıza yarar.


```python
df.filter(regex='^L').head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Low</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>17916.910156</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17711.800781</td>
    </tr>
    <tr>
      <th>2</th>
      <td>17456.019531</td>
    </tr>
    <tr>
      <th>3</th>
      <td>17190.509766</td>
    </tr>
    <tr>
      <th>4</th>
      <td>17063.080078</td>
    </tr>
  </tbody>
</table>
</div>



### **np.logical_and** 

Mantıksal ve ile filtreleme işlemi yapmamıza yarar.


```python
df[np.logical_and(df['Open']>18281.949219, df['Date']>'2015-05-20' )]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>280</th>
      <td>2015-05-22</td>
      <td>18286.869141</td>
      <td>18286.869141</td>
      <td>18217.140625</td>
      <td>18232.019531</td>
      <td>78890000</td>
      <td>18232.019531</td>
    </tr>
    <tr>
      <th>281</th>
      <td>2015-05-21</td>
      <td>18285.869141</td>
      <td>18314.890625</td>
      <td>18249.900391</td>
      <td>18285.740234</td>
      <td>84270000</td>
      <td>18285.740234</td>
    </tr>
  </tbody>
</table>
</div>



### **& ile filtreleme** 


```python
df[(df['Open']>18281.949219) & (df['Date']>'2015-05-20')]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>280</th>
      <td>2015-05-22</td>
      <td>18286.869141</td>
      <td>18286.869141</td>
      <td>18217.140625</td>
      <td>18232.019531</td>
      <td>78890000</td>
      <td>18232.019531</td>
    </tr>
    <tr>
      <th>281</th>
      <td>2015-05-21</td>
      <td>18285.869141</td>
      <td>18314.890625</td>
      <td>18249.900391</td>
      <td>18285.740234</td>
      <td>84270000</td>
      <td>18285.740234</td>
    </tr>
  </tbody>
</table>
</div>



## **Verileri Sıralama** 

### **df.sort_values('columnName')**

Bu kod, belirttiğimiz sütunu, küçükten büyüğe doğru sıralar.


```python
df.sort_values('Open').head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1842</th>
      <td>2009-03-10</td>
      <td>6547.009766</td>
      <td>6926.490234</td>
      <td>6546.609863</td>
      <td>6926.490234</td>
      <td>640020000</td>
      <td>6926.490234</td>
    </tr>
    <tr>
      <th>1844</th>
      <td>2009-03-06</td>
      <td>6595.160156</td>
      <td>6755.169922</td>
      <td>6469.950195</td>
      <td>6626.939941</td>
      <td>425170000</td>
      <td>6626.939941</td>
    </tr>
    <tr>
      <th>1843</th>
      <td>2009-03-09</td>
      <td>6625.740234</td>
      <td>6709.609863</td>
      <td>6516.859863</td>
      <td>6547.049805</td>
      <td>365990000</td>
      <td>6547.049805</td>
    </tr>
    <tr>
      <th>1846</th>
      <td>2009-03-04</td>
      <td>6726.500000</td>
      <td>6979.220215</td>
      <td>6726.419922</td>
      <td>6875.839844</td>
      <td>464830000</td>
      <td>6875.839844</td>
    </tr>
    <tr>
      <th>1847</th>
      <td>2009-03-03</td>
      <td>6764.810059</td>
      <td>6855.290039</td>
      <td>6705.629883</td>
      <td>6726.020020</td>
      <td>445280000</td>
      <td>6726.020020</td>
    </tr>
  </tbody>
</table>
</div>



### **df.sort_values('columnName', ascending=False)**

Bu kod, büyükten küçüğe doğru sütunu sıralamamıza yarar.


```python
df.sort_values('Date', ascending=False).head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.240234</td>
      <td>18002.380859</td>
      <td>17916.910156</td>
      <td>17949.369141</td>
      <td>82160000</td>
      <td>17949.369141</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.759766</td>
      <td>17930.609375</td>
      <td>17711.800781</td>
      <td>17929.990234</td>
      <td>133030000</td>
      <td>17929.990234</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456.019531</td>
      <td>17704.509766</td>
      <td>17456.019531</td>
      <td>17694.679688</td>
      <td>106380000</td>
      <td>17694.679688</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>112190000</td>
      <td>17409.720703</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>17355.210938</td>
      <td>17355.210938</td>
      <td>17063.080078</td>
      <td>17140.240234</td>
      <td>138740000</td>
      <td>17140.240234</td>
    </tr>
  </tbody>
</table>
</div>



### **df.sort_index()**

Bu kod DataFrame indeksine göre küçükten büyüğe doğru sıralam yapar.


```python
df.sort_index().head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.240234</td>
      <td>18002.380859</td>
      <td>17916.910156</td>
      <td>17949.369141</td>
      <td>82160000</td>
      <td>17949.369141</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.759766</td>
      <td>17930.609375</td>
      <td>17711.800781</td>
      <td>17929.990234</td>
      <td>133030000</td>
      <td>17929.990234</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456.019531</td>
      <td>17704.509766</td>
      <td>17456.019531</td>
      <td>17694.679688</td>
      <td>106380000</td>
      <td>17694.679688</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>112190000</td>
      <td>17409.720703</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>17355.210938</td>
      <td>17355.210938</td>
      <td>17063.080078</td>
      <td>17140.240234</td>
      <td>138740000</td>
      <td>17140.240234</td>
    </tr>
  </tbody>
</table>
</div>



## **Yeniden Adlandırma & Yeniden Tanımla & Sütun Adını Değiştirme**

### **df.rename(columns= {'columnName' : 'newColumnName'})** 

Bu kod sütun adını değiştirmemize yardımcı olur. Aşağıda yazdığım kod ID değerini değiştiriyor, ancak değişikliği DF değişkenine atamadığımız için, aşağıda gördüğünüz gibi değişmemiş olarak görünüyor.


```python
df.rename(columns= {'Adj Close' : 'Adjclose'}).head()
# df = df.rename(columns= {'Id' : 'Identif'}, inplace=True) -> Doğru Kod
# inplace= True or False; Bu durum veri setinin üzerine yazıp yazmama durumu belirtir.
# Other Way
# df.columns = ['date', 'open', 'high', 'low', 'close', 'volume', 'adjclose']
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adjclose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.240234</td>
      <td>18002.380859</td>
      <td>17916.910156</td>
      <td>17949.369141</td>
      <td>82160000</td>
      <td>17949.369141</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.759766</td>
      <td>17930.609375</td>
      <td>17711.800781</td>
      <td>17929.990234</td>
      <td>133030000</td>
      <td>17929.990234</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456.019531</td>
      <td>17704.509766</td>
      <td>17456.019531</td>
      <td>17694.679688</td>
      <td>106380000</td>
      <td>17694.679688</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>112190000</td>
      <td>17409.720703</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>17355.210938</td>
      <td>17355.210938</td>
      <td>17063.080078</td>
      <td>17140.240234</td>
      <td>138740000</td>
      <td>17140.240234</td>
    </tr>
  </tbody>
</table>
</div>



###  **Yeni Sütun Tanımlama** 

Yeni sütun oluşturma


```python
df["Difference"] = df.High - df.Low
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
      <th>Difference</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.240234</td>
      <td>18002.380859</td>
      <td>17916.910156</td>
      <td>17949.369141</td>
      <td>82160000</td>
      <td>17949.369141</td>
      <td>85.470703</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.759766</td>
      <td>17930.609375</td>
      <td>17711.800781</td>
      <td>17929.990234</td>
      <td>133030000</td>
      <td>17929.990234</td>
      <td>218.808594</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456.019531</td>
      <td>17704.509766</td>
      <td>17456.019531</td>
      <td>17694.679688</td>
      <td>106380000</td>
      <td>17694.679688</td>
      <td>248.490235</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>112190000</td>
      <td>17409.720703</td>
      <td>219.210937</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>17355.210938</td>
      <td>17355.210938</td>
      <td>17063.080078</td>
      <td>17140.240234</td>
      <td>138740000</td>
      <td>17140.240234</td>
      <td>292.130860</td>
    </tr>
  </tbody>
</table>
</div>



### **İndeks Adını Değiştir** 

İndeks adını belirttiğimiz şekilde değiştirir.


```python
print(df.index.name)
df.index.name = "index_name"
df.head()
```

    None





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Adj Close</th>
      <th>Difference</th>
    </tr>
    <tr>
      <th>index_name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.240234</td>
      <td>18002.380859</td>
      <td>17916.910156</td>
      <td>17949.369141</td>
      <td>82160000</td>
      <td>17949.369141</td>
      <td>85.470703</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.759766</td>
      <td>17930.609375</td>
      <td>17711.800781</td>
      <td>17929.990234</td>
      <td>133030000</td>
      <td>17929.990234</td>
      <td>218.808594</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456.019531</td>
      <td>17704.509766</td>
      <td>17456.019531</td>
      <td>17694.679688</td>
      <td>106380000</td>
      <td>17694.679688</td>
      <td>248.490235</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>112190000</td>
      <td>17409.720703</td>
      <td>219.210937</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>17355.210938</td>
      <td>17355.210938</td>
      <td>17063.080078</td>
      <td>17140.240234</td>
      <td>138740000</td>
      <td>17140.240234</td>
      <td>292.130860</td>
    </tr>
  </tbody>
</table>
</div>



### **Bütün sütunların adını küçük yapma** 


```python
#df.columns = map(str.lower(), df.columns)
```

### **Bütün sütunların adını büyük yapma**


```python
#df.columns = map(str.upper(), df.columns)
```

## **Veri Çıkarma**

### **df.drop(columns=['columnName'])** 

Bu kod belirlediğimiz sütunu siler.Ancak burada da inplace değerini belirtmemiz gerekiyor.


```python
df.drop(columns=['Adj Close']).head()
# df = df.drop(columns=['Id']) -> True way
# OR
# df = df.drop('col', axis=1)
# axis = 1 is meaning delete columns
# axis = 0 is meaning delete rows
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Difference</th>
    </tr>
    <tr>
      <th>index_name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>17924.240234</td>
      <td>18002.380859</td>
      <td>17916.910156</td>
      <td>17949.369141</td>
      <td>82160000</td>
      <td>85.470703</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>17712.759766</td>
      <td>17930.609375</td>
      <td>17711.800781</td>
      <td>17929.990234</td>
      <td>133030000</td>
      <td>218.808594</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>17456.019531</td>
      <td>17704.509766</td>
      <td>17456.019531</td>
      <td>17694.679688</td>
      <td>106380000</td>
      <td>248.490235</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>17190.509766</td>
      <td>17409.720703</td>
      <td>112190000</td>
      <td>219.210937</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>17355.210938</td>
      <td>17355.210938</td>
      <td>17063.080078</td>
      <td>17140.240234</td>
      <td>138740000</td>
      <td>292.130860</td>
    </tr>
  </tbody>
</table>
</div>



### **mySeries.drop(['a'])** 

Bu kod, dizide belirtilen değeri silmemize yarar.


```python
mySeries.drop(['a'])
```




    b   -5
    c    7
    d    4
    dtype: int64



### **Satır Silme** 


```python
# df.drop(['2016-07-01', '2016-06-27'])
```

### **Veri Silme** 

Not: axis = 1, bir satıra değil bir sütuna işaret ettiğimizi gösterir.


```python
# df.drop('Volume', axis=1)
```

## **Veri Tiplerini Çevirme** 

### **df.dtypes**

Bu kod hangi sütunların hangi veri tipini olduğunu gösterir. Boolean, int, float, object (String), tarih ve kategorik.


```python
df.dtypes
```




    Date           object
    Open          float64
    High          float64
    Low           float64
    Close         float64
    Volume          int64
    Adj Close     float64
    Difference    float64
    dtype: object



### **df['columnName'] = df['columnName'].astype('dataType')**

Bu kod, belirlediğimiz sütunu, belirlediğimiz veri türüne dönüştürür.


```python
df.Date.astype('category').dtypes
# OR Convert Datetime
# df.Date= pd.to_datetime(df.Date)
```




    CategoricalDtype(categories=['2008-08-08', '2008-08-11', '2008-08-12', '2008-08-13',
                      '2008-08-14', '2008-08-15', '2008-08-18', '2008-08-19',
                      '2008-08-20', '2008-08-21',
                      ...
                      '2016-06-20', '2016-06-21', '2016-06-22', '2016-06-23',
                      '2016-06-24', '2016-06-27', '2016-06-28', '2016-06-29',
                      '2016-06-30', '2016-07-01'],
                     ordered=False)



### **pd.melt(frame=dataFrameName,id_vars = 'columnName', value_vars= ['columnName'])** 

Bu kod biraz kafa karıştırıcı, bu nedenle örneğe bakalım.


```python
df_new = df.head()
melted = pd.melt(frame=df_new,id_vars = 'Date', value_vars= ['Low'])
melted
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>variable</th>
      <th>value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2016-07-01</td>
      <td>Low</td>
      <td>17916.910156</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2016-06-30</td>
      <td>Low</td>
      <td>17711.800781</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2016-06-29</td>
      <td>Low</td>
      <td>17456.019531</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2016-06-28</td>
      <td>Low</td>
      <td>17190.509766</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2016-06-27</td>
      <td>Low</td>
      <td>17063.080078</td>
    </tr>
  </tbody>
</table>
</div>



## **Apply Fonksiyonu**

### **Yöntem 1**


```python
def examples(x):   #create a function
    return x*2

df.Open.apply(examples).head()  #use the function with apply() 
```




    index_name
    0    35848.480468
    1    35425.519532
    2    34912.039062
    3    34381.019532
    4    34710.421876
    Name: Open, dtype: float64



### **Yöntem 2**


```python
df.Open.apply(lambda x: x*2).head()
```




    index_name
    0    35848.480468
    1    35425.519532
    2    34912.039062
    3    34381.019532
    4    34710.421876
    Name: Open, dtype: float64



# **Faydalı Kodlar**


```python
# pd.get_option OR pd.set_option
# pd.reset_option("^display")

# pd.reset_option("display.max_rows")
# pd.get_option("display.max_rows")
# pd.set_option("max_r",102)                 -> Gösterilecek maksimum satır sayısını belirtir.
# pd.options.display.max_rows = 999          -> Gösterilecek maksimum satır sayısını belirtir.

# pd.get_option("display.max_columns")
# pd.options.display.max_columns = 999       -> Görüntülenecek maksimum sütun sayısını belirtir.

# pd.set_option('display.width', 300)

# pd.set_option('display.max_columns', 300)  -> Gösterilecek maksimum satır sayısını belirtir.
# pd.set_option('display.max_colwidth', 500) -> Görüntülenecek maksimum sütun sayısını belirtir.

# pd.get_option('max_colwidth')
# pd.set_option('max_colwidth',40)
# pd.reset_option('max_colwidth')

# pd.get_option('max_info_columns')
# pd.set_option('max_info_columns', 11)
# pd.reset_option('max_info_columns')

# pd.get_option('max_info_rows')
# pd.set_option('max_info_rows', 11)
# pd.reset_option('max_info_rows')

# pd.set_option('precision',7) -> Çıktı görüntüleme hassasiyetini ondalık basamak cinsinden ayarlar. Bu sadece bir öneri.
# OR
# pd.set_option('display.precision',3)

# pd.set_option('chop_threshold', 0) -> Bir DataFrame dizisi görüntülediğinde Pandas'ın sıfıra ne kadar döndüğünü belirler. Bu ayar, numaranın kaydedildiği hassasiyeti değiştirmez.
# pd.reset_option('chop_threshold') 
```

> Son Güncelleme: 28 Aralık 2019 - Cumartesi
