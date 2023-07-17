# ``init`` ve ``main`` fonksiyonları

``init`` ve ``main`` fonksiyonları, Jule programlama dilinin en önemli fonksiyonlarındandır.

## ``init`` Fonksiyonu
``init`` fonksiyonu, program başladığında <b>ilk olarak çağırılan fonsiyondur.</b> Eğer ana paketteyse ``main`` fonksiyonundan önce çağırılır.
``init`` fonksiyonunun ilk olarak çağırılma sebebi ise ``init`` fonksiyonun içerisinde program için gerekli olan kodların initialize edilip ayarlanmasıdır.

Bunu kısa bir örnekle açıklayalım.

Örneğin bir program yazıyorsunuz ve bu programda bir dosyaya yazma işlemi yapacaksınız. Bu dosyayı açmadan önce dosyanın var olup olmadığını kontrol etmeniz gerekiyor, eğer dosya yoksa dosyayı oluşturmanız gerekiyor.

Bu işlemleri ``main`` fonksiyonu içerisinde yaparsanız kodunuzun okunması zorlaşır. Bu yüzden bu işlemleri ``init`` fonksiyonu içerisinde yaparsanız kodunuz daha okunabilir olur.

Ayrıca ``init`` fonksiyonu içerisinde yapılan işlemler main fonksiyonundan önce çağırıldığı için main fonksiyonu içerisinde bu işlemleri tekrar yapmanıza gerek kalmaz.

<b>Kısacası Package Consturctor gibi düşünebilirsiniz.</b>

``init`` fonksiyonu, fonksiyonun başına `init` anahtar kelimesi yazılarak tanımlanır.

```jule
fn init() {
    outln("Hello World from Init Function!")
}
```

## ``main`` Fonksiyonu

``main`` fonksiyonu ise programın çalıştırıldığı yani programın ana girdi noktasıdır. Yazdığınız herhangi bir fonksiyonu kullanmak için veya derleyicinin``(julec)``'nin algılayabilmesi için ``main`` fonksiyonu içerisinde çağırmanız gerekmektedir.

<b>Eğer ``main`` fonksiyonu içerisinde çağırmazsanız derleyici herhangi fonksiyonu algılayamaz ve çalıştıramaz.</b>

Örneğin:

```jule
fn main() {
    outln("Hello World from Main Function!")
}
```

## Notlar

- ``init`` fonksiyonu parametre <b>alamaz</b>.
- ``main`` fonksiyonu, <b>Giriş noktası void fonksiyonu olmalı ve herhangi bir parametreye sahip olmamalıdır</b>.
- ``init`` fonksiyonu, ``main`` fonksiyonundan önce çağırılır.
- ``init`` fonksiyonu, ``main`` fonksiyonundan önce çağırıldığı için main fonksiyonu içerisinde bu işlemleri tekrar yapmanıza gerek kalmaz.