# Değişmezlik (Immutability)

## Değişmezlik Nedir?

Jule dilinde, değişkenler default olarak değiştirilemezdir. Bu, bir değişkenin değerinin bir kez tanımlandıktan sonra değiştirilemeyeceği anlamına gelir. Eğer bir değişkenin değerini değiştirmek istiyorsanız, değişkeni `mut` anahtar kelimesi ile tanımlamanız gerekir.

```jule
let x = 10 // Değişkenin değeri 10'dur.
x = 20 // Hata: Değişkenin değeri değiştirilemez.
```

```jule
let mut x = 10 // Değişkenin değeri 10'dur.
x = 20 // Değişkenin değeri 20'dir.
```

## Değişmezliği Bozmak

Eğer bir değişken değişmez (immutable) ise ve içinde değiştirilebilir (mutable) veri tipi bulunuyorsa, Güvenli Jule (Safe Jule) bu değişkeni değiştirilebilir bir değişkene atamanıza izin vermez. Bellek güvenliği, bu konuyla ilgili olarak değişmezlik belgelerinde bahsedilir. Ancak bunu bozmanın bir yolu vardır. Bu, doğal olarak güvenliği de ihlal etmek anlamına gelir, ancak bu bilinciniz dahilindedir. Güvensiz Jule (Unsafe Jule), bu tür durumlar için güvenlik önlemleri almanızı teşvik etmez.

Bu bağlamda, işaretçilerin alındıklarında değiştirilebilir olduğunu bilmeniz önemlidir. Bu nedenle, bir değişmez bir değişkenin işaretçisini alır ve bu işareti değiştirilebilir bir şekilde kullanırsanız, değişmez değişkenin verisini değiştirebilirsiniz. Güvensiz Jule ile yalnızca işaretçilere atama yapabilirsiniz, bu nedenle bu işlemin zaten bir güvenlik riski oluşturabileceğinin farkında olacaksınız.

Örneğin: 
```jule
fn main() {
    let x = 10;
    let mut xp = &x;
    unsafe { *xp += 20; }
    println!("{}", x); // 30
}
```

Bu örnekte, `x` adlı değişmez bir değişken oluşturuyoruz ve bu değişkenin işaretçisini `xp` adlı bir değişkene atıyoruz. Ardından, unsafe bloğu içinde, işaretçiyi kullanarak `x` değişkeninin değerini değiştiriyoruz. Bu, değişmezlik kavramını ihlal ettiği için "unsafe" olarak işaretlenir ve güvenlik riski oluşturabilir. Sonuç olarak, println! fonksiyonu ile `x` değişkeninin değerini yazdırdığımızda, sonuç 30 olacaktır, çünkü `x` değiştirilmiştir.