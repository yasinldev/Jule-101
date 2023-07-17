# Veri Türleri

Jule, güçlü bir veri türüne sahiptir. Jule'de veri türleri, <b>değişkenlerin değerlerini tutmak için kullanılır.
</b>

## İlkel Veri Türleri

İlkel veri türleri, aşağıdaki tabloda listelenmiştir.

Tür | Tipik bit genişliği | Tipik değer aralığı
--- |---------------------| --- 
i8 | 1 bits              | -128 ila 127 
i16 | 2 bits              | -32,768 ila 32,767
i32 | 4 bits              | -2,147,483,648 ila 2,147,483,647
i64 | 8 bits              | <small>-9,223,372,036,854,775,808 ila 9,223,372,036,854,775,807</small>
int | Platforma bağlı     | Platforma göre değişiklik gösterir
u8 | 1 bits              | 0 ila 255
u16 | 2 bits              | 0 ila 65,535
u32 | 4 bits              | 0 ila 4,294,967,295
u64 | 8 bits              | 0 ila 18,446,744,073,709,551,615
uint | Platforma bağlı     | Platforma göre değişiklik gösterir
uintptr | Platforma bağlı     | Platforma göre değişiklik gösterir
f32 | 4 bits              | <small>-3,4028234663852886e+38 ila 3,4028234663852886e+38</small>
f64 | 8 bits              | <small>-1,7976931348623157e+308 ila 1,7976931348623157e+308</small>
Bool | 1 bits              | true veya false
str | - | UTF-8 karakter dizisi
any | - | Herhangi bir veri türü

## Tür Uyumluluğu

Jule, tür uyumluluğu için aşağıdaki tabloyu kullanır.

Tür | Uyumlu Türler
--- |---------------------
i8 | i8,
i16 | i8, i16
i32 | i8, i16, i32
i64 | i8, i16, i32, i64
int | Platforma bağlı (imzalı)
u8 | u8
u16 | u8, u16
u32 | u8, u16, u32
u64 | u8, u16, u32, u64
uint | Platforma bağlı (imzasız)
uintptr | Platforma bağlı (imzasız)
f32 | f32, i8, i16, i32, i64, u8, u16, u32, u64
f64 | f32, f64, i8, i16, i32, i64, u8, u16, u32, u64
Bool | Bool
str | str
any | any

## Tamsayı değiştirilemez değerler

### ondalık

```jule
12345
```

### ikili

```jule
0b0001010101
```

### sekizli

```jule
0455
```

### onaltılı

```jule
0xDFF90
```

## Kayan Noktalı Sayı Sabitler

Ondalık kayan noktalı sayıların doğrudan değerlerini ifade eden sabitlere atıfta bulunur. Ondalık kayan noktalı sayılar, ondalık kısmı ve üs (exponent) kısmıyla birleştirilmiş bir formatta ifade edilen sayılardır.

Örneğin, bir ondalık kayan noktalı sayı literali, 3.14 veya 2.0 gibi sayıların doğrudan temsil edilmesidir. Bu literaller, genellikle matematiksel hesaplamalar veya hassas sayı gerektiren uygulamalarda kullanılır.

Ondalık kayan noktalı sayılar, bilgisayarın sınırlı bir bellek yapısı olduğu ve tam kesirli sayıları tam olarak temsil edemediği gerçeği göz önüne alındığında bazen yaklaşık değerlere sahip olabilir.

```jule
3.14
```
```jule
32.60
```
```jule
032.60
```
```jule
3.
```
```jule
0.3
```
```jule
.12345E+6
```
```jule
1.e+0
```
```jule
0x1p-2
```
```jule
0x2.p10
```
```jule
0x1.Fp+0
```
```jule
0X.8p-0
```
```jule
0x1fffp-16
```
```jule
0x15e-2
```

## String Sabitler

String sabitleri, metin veya karakter dizilerini doğrudan temsil eden sabit değerlerdir. Bir dize sabiti, çift tırnak ("") veya tek tırnak ('') içinde yer alan karakterlerden oluşur.

```jule
"Jule içerisindeki string sabitleri"
```

String içerisindeki özel karakterler, aşağıdaki tabloda listelenmiştir.

Karakter | Anlamı
--- |---------------------
\a | ASCII bip sesi
\b | ASCII geri tuşu
\f | ASCII form besleme
\n | ASCII satır atlaması (newline)
\r | Satır başına dönme (carriage return)
\t | ASCII yatay sekme
\v | ASCII dikey sekme
\' | Tek tırnak işareti
\" | Çift tırnak işareti
\xhh | hh tarafından temsil edilen onaltılık sayısal değer, bir bayt olarak yorumlanır.
\uhhhh | hhhh tarafından temsil edilen Unicode kod noktası, 10000 onaltılının altında olmalıdır.
\Uhhhhhhhh | hhhhhhhh tarafından temsil edilen Unicode kod noktası.
\ooo | ooo tarafından temsil edilen sekizlik sayısal değer, bir bayt olarak yorumlanır.

## Ham Dize Sabitleri

Ham dize sabitleri, içerdikleri metinleri olduğu gibi temsil eden dize sabitleridir. Bu tür dize sabitleri genellikle kaçış dizilerini (escape sequences) yorumlamazlar, böylece içerdikleri metinlerdeki ters eğik çizgiler veya diğer özel karakterlerin anlamını korur. Ham dize sabitleri, genellikle metin dosyaları, çoklu satırlı dize ifadeleri veya düzenli ifadeler gibi durumlarda kullanılır.

Örneğin: 
```jule
`Ham dize sabitleri`
```

```jule
`Ham dize sabitleri
ama
çoklu satırlı
    hali`
```

## Nil

Nil sabiti, İşaretçiler için 0'ı temsil eder. Nil sabiti, bir işaretçi türüne sahip herhangi bir değişkene atanabilir.

```jule
nil
```

## Any

Any sabiti, herhangi bir veri türüne sahip değerleri temsil edebilir veya içerisinde ``nil`` değeri atanabilir. Any sabiti, herhangi bir veri türüne sahip herhangi bir değişkene atanabilir.
> Any sabiti, herhangi bir veri türüne sahip herhangi bir değişkene atanabilir.

``x == y:`` true ise x ve y nil ise true döner. x ve y aynı veri türüne sahipse ve veri türünün eşitlik operatörü iki değer için de true döndürüyorsa true döner.

Herhangi bir tipe dönüşüm yapmaya izin verir. Dönüşümle tip güvenli değeri alabilirsiniz. Örneğin:

```jule
let my_any: any = 10
let other_any = (int)(my_any)
```

any tipi gerektiğinde kendini değişmezlik karşısında korur. Örneğin, any tipinde bir değişkenle tutulan dilim değeri olduğunu varsayalım. Ve değişkeniniz değişmez (immutable) olsun. Bu durumda, değerinizi değişkene atamak için dilime dönüştürürseniz hata alırsınız. Çünkü dilim değiştirilebilir bir tiptir ve bu, değişmezliği bozar.

> **Warning** <br>
> Bu çok güvensiz bir yöntemdir ve türetilmemesine özen gösterilmelidir.




