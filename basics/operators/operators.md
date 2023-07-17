# Operatörler

Operatörler, aritmetik veya mantıksal görevleri tanımlayan ve belirten sembollerdir.

## Programlama Dillerinde Operatörler
### Operatörleri anlamak

Operatörler, programlama dillerinde kullanılan semboller veya işaretlerdir ve belirli işlemleri gerçekleştirmek için kullanılırlar. Operatörler, aritmetik, karşılaştırma, mantıksal, atama, bit işlemleri gibi farklı kategorilere ayrılabilir. Yaygın olarak kullanılan bazı operatörlerin örnekleri:

* Aritmetik Operatörler: Toplama (+), Çıkarma (-), Çarpma (*), Bölme (/), Modülüs (%), Artırma (++), Azaltma (--).

* Karşılaştırma Operatörleri: Eşit (==), Eşit Değil (!=), Büyük (>), Küçük (<), Büyük Eşit (>=), Küçük Eşit (<=).

* Mantıksal Operatörler: VE (&&), VEYA (||), DEĞİL (!), XOR (^).

* Atama Operatörleri: Eşitleme (=), Toplama ve Atama (+=), Çıkarma ve Atama (-=), Çarpma ve Atama (*=), Bölme ve Atama (/=).

* Bit İşlemi Operatörleri: VE (&), VEYA (|), Tersleme (~), Kaydırma Sola (<<), Kaydırma Sağa (>>).

* Bu operatörler, programlarda verilerin işlenmesi, karşılaştırılması, atama yapılması ve mantıksal işlemlerin gerçekleştirilmesi gibi birçok farklı amaç için kullanılırlar.

### Operatörlerin Önceliği


Operatörlerin önceliği, bir ifade içerisindeki operatörlerin hangi sırayla değerlendirileceğini belirleyen bir kuraldır. Bu öncelik, belirli bir operatörün diğerlerinden önce veya sonra değerlendirilmesini sağlar.

Genel olarak, operatörlerin önceliği şu sıraya göre belirlenir (en yüksek öncelikten en düşüğe doğru):

* Parantez içindeki ifadeler: () - Parantez içindeki ifadeler her zaman en önce değerlendirilir.

* Artırma ve azaltma operatörleri: ++, --

* Çarpma, bölme ve modülüs operatörleri: *, /, %

* Toplama ve çıkarma operatörleri: +, -

* Karşılaştırma operatörleri: ==, !=, >, <, >=, <=

* Mantıksal operatörler: ! (DEĞİL), && (VE), || (VEYA)

> **Note**<br>
> Operatörler aynı önceliğe sahipse, ifade solundan sağa doğru değerlendirilir. Örneğin, ``5 + 3 * 2`` ifadesinde çarpma işlemi önceliklidir, bu nedenle ``3 * 2`` önce yapılır ve <b>ardından sonuç olan 6, 5 ile toplanır</b>.

Operatörlerin önceliği, ifadelerin doğru bir şekilde değerlendirilmesi için önemlidir. Bu nedenle, karmaşık ifadelerde operatör önceliği ve parantez kullanımına dikkat etmek önemlidir.

## Aritmetik Operatörler

Aritmetik operatörler, yaygın matematiksel işlemleri gerçekleştirmek için kullanılır. Ve bazen sayısal olmayan tipler için de kullanılır.

Jule içerisindeki aritmetik operatörler şunlardır:

| Operatör | Açıklama | Desteklediği Tür(ler)       |
|:---------| :--- |:----------------------------|
| +        | Toplama | Integer, Float, String      |
| -        | Çıkarma | Integer, Float              |
| *        | Çarpma | Integer, Float              |
| /        | Bölme | Integer, Float              |
| %        | Modülüs | Integer                     |
| <<       | Kaydırma Sola | Integer << unsigned integer |
| \>>      | Kaydırma Sağa | Integer >> unsigned integer |
| ++       | Artırma | Soldaki değer ++            |
| --       | Azaltma | Soldaki değer --            |

## Karşılaştırma Operatörleri

Karşılaştırma operatörleri, Jule içerisinde kullanılan ve iki değeri karşılaştırmak için kullanılan operatörlerdir. Bu operatörler, iki değerin ilişkisini kontrol etmek ve sonucunda bir boolean değeri (true veya false) elde etmek için kullanılır.

Jule içerisindeki karşılaştırma operatörleri şunlardır:

| Operatör | Açıklama |
|:---------| :--- |
| ==       | Eşit |
| !=       | Eşit Değil |
| \>       | Büyük |
| <        | Küçük |
| \>=      | Büyük Eşit |
| <=       | Küçük Eşit |
| &&      | VE |
| \|\|     | VEYA |
| !        | DEĞİL |

## Bitwise Operatörleri


Bitwise operatörler, Jule içerisindeki verilerin bit seviyesinde manipülasyonu için kullanılan operatörlerdir. Bu operatörler, işlem yapılacak değerleri ikili (binary) formatta ele alır ve bu değerlerin bitlerine doğrudan müdahale eder.

Aşağıda Jule içerisinde kullanılan bitwise operatörler şunlardır:

| Operatör | Açıklama                     |
|:---------|:-----------------------------|
| &        | Bitwise VE                   |
| \|       | Bitwise VEYA                 |
| ~        | Bitwise XOR veya Bitwise NOT |


##  Öncelikli Operatörler
Aşağıda Jule içerisindeki öncelikli operatörler şunlardır:

| Öncelik(Azalan)  | Operatör(ler)   |
|:-----------------|:----------------|
| 5 | * % / << >> &   |
| 4 | + -             |
| 3 | == != < <= > >= |
| 2 | &&              |
| 1 | \|\|            |
 