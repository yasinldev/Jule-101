# Söz Dizimi
## Parçalar
Herhangi bir parça beyanını takip etmelidir. Örneğin, bir işlev tanımlıyorsunuz, gövde aynı satırda başlamalıdır. Alt satırdan başlarsanız, bir derleyici hatası alırsınız.

Bir işlevin beyanını takip etmesinin sebebi, Jule derleyicisinin, bir işlevin başlangıcını bulmak için bir işlevin sonunu aramasıdır. Bu, bir işlevin sonunu bulmak için tüm dosyayı aramak zorunda kalmayacağı anlamına gelir.

Örneğin
```jule
// Doğru tanımlama.
fn main() {
    outln("Hello, World!");
}

// Yanlış tanımlama.
fn main()
{
    outln("Hello, World!");
}
```
## Ifadeler

###  Statements

Statements, Jule dilinde bir görevi veya eylemi ifade etmek için kullanılan yapısal bir bileşendir. Statements, programın çalışma zamanında bir işlemi gerçekleştirmek, bir değeri atamak, bir döngüyü kontrol etmek, bir koşulu değerlendirmek, bir fonksiyon çağırmak veya başka bir eylemi gerçekleştirmek için kullanılır.

Bir statement, bir veya daha fazla operatör, operatörler arasında geçerli değerler veya değişkenler, sabitler veya fonksiyon çağrıları gibi temel yapı taşlarından oluşur. Statements'ler, genellikle bir satırda ifade edilir ve noktalı virgül (;) ile sonlandırılır.

> **Note** <br>
> Jule dilinde Statements'ler semicolon(```;```) ile ayrıldığını söyledik, ancak semicolon'un her zaman gerekli olmadığını unutmayın. Semicolon yalnızca birden fazla statementi yan yana yazdığınızda birbirinden ayrımak gereklidir.

```jule
fn main() {
    [STATEMENT_1]; [STATEMENT_2] // Semicolon yalnızca aynı satırda birden fazla ifade yazdığınızda gereklidir.
    [STATEMENT_3]
    [STATEMENT_4]
}
```

###  Expressions

Expressions, Jule dilinde bir değeri üretmek için kullanılan yapısal bir bileşendir. Bir expression, bir veya daha fazla operatör, operatörler arasında geçerli değerler veya değişkenler, sabitler veya fonksiyon çağrıları gibi temel yapı taşlarından oluşur. Expressions'ler, genellikle bir satırda ifade edilir ve noktalı virgül (;) ile sonlandırılması gerekmez.

Eğer uzun bir expression yazıyorsanız, expression'ı parantez içine almanız veya binary expression kullanmanız gerekebilir.

#### Parantez içine almak
Parantezler, ifadeyle birlikte kullanıldığında kapatılana kadar tüm belirteçleri kabul eder. Bu nedenle, sonraki satırlara devam edebilirsiniz. Bu aynı zamanda brace ve bracket için de geçerlidir.

Örneğin
```jule
let (x, y) = 20, false
if (x == 10 ||
         y == true) {
    /*
        ...
    */
}
```

#### Binary Expression

Binary expressions, programlama dillerinde iki operand ve bir operatör içeren ifadelerdir. Örneğin, ``a + b``, ``x * y``, ``c == d`` gibi ifadeler binary expressionsdır. Binary expressions, aritmetik, bit düzeyi, kaydırma, koşullu, karşılaştırma, birleşim veya dizi dizin oluşturma gibi çeşitli işlemleri gerçekleştirmek için kullanılabilir.

Jule dilinde Binary expressions, parantez olmadan bile bir operand'a ihtiyacı olup olmadığını sonraki satırda kontrol etmeye çalışır. Bu nedenle doğru bir kullanımla, ikili bir ifadeyle sonraki satıra geçebilirsiniz. Genellikle parantezlerden daha okunabilir bir yaklaşım olarak kabul edilir.

Örneğin
```jule
let (x, y) = 20, false
if x == 10 ||
	y == false {
	 /*
	 ...
	 */
}
```