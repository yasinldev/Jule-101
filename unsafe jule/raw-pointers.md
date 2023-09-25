# Ham İşaretçiler (Raw Pointers)

## Ham İşaretçiler Nedir?

Ham işaretçiler, işaretçilerin en temel halidir. Ham işaretçiler, işaret ettiği verinin türünü bilmezler. Bu nedenle, ham işaretçileri kullanırken, işaret ettiği verinin türünü kendiniz belirtmeniz gerekir. Ham işaretçiler, `*const T` ve `*mut T` olmak üzere iki türe ayrılır. `*const T` işaretçileri, `const` anahtar kelimesi ile tanımlanmış değişkenlerin işaretçilerini tutar. `*mut T` işaretçileri ise `mut` anahtar kelimesi ile tanımlanmış değişkenlerin işaretçilerini tutar.

## Ham İşaretçilere Başvurmak

Güvenli olmayan Jule (Unsafe Jule), ham işaretçilere başvurmanıza izin verir.

Örneğin: 
```jule
fn main() {
    let x = 200;
    let ptr = &x;
    unsafe { outln(*ptr); }
}
```

Bu örnekte, `x` adlı bir değişken oluşturuyoruz ve bu değişkenin işaretçisini `ptr` adlı bir değişkene atıyoruz. Ardından, `unsafe` bloğu içinde, işaretçiyi kullanarak `x` değişkenini derecelendiriyoruz `(*ptr)`. Bu, güvenli olmayan bir işlem olduğu için "unsafe" olarak işaretlenir ve güvenlik sağlanmaz. Dangling işaretçilere, bellek taşmalarına ve benzeri bellek sorunlarına karşı kendiniz önlem almalısınız.

## Ham İşaretçiler İçin Sonekler (Postfixes)

Güvenli olmayan Jule (Unsafe Jule), ham işaretçiler için sonekleri (postfixes) destekler.

Örneğin: 
```jule
fn print_slice_components_with_unsafe(slc: []int) {
    unsafe {
        let mut ptr = &slc[0];
        let mut end = &slc[slc.len - 1];
        end++;
        while ptr < end {
            outln(*ptr);
            ptr++;
        }
    }
}
```

Bu örnekte, `print_slice_components_with_unsafe` adlı bir fonksiyon tanımlıyoruz. Bu fonksiyon, bir kesit (slice) alır ve bu kesitin ilk elemanına işaret eden `ptr` ve son elemanına işaret eden `end` ham işaretçilerini kullanarak kesitin elemanlarını yazdırır.

## Ham İşaretçilerle İndeksleme (Indexing with Raw Pointers)

Bu özellik özellikle bir dizinin işaretçisine sahipseniz (örneğin, std::mem::c paketi ile oluşturulan bir dizi işaretçisi gibi), işareti bir dizi gibi kullanmanıza izin verir. Offset için uzunluğa yardımcı olması için bir sarma (wrapper) kullanmayı tercih edebilirsiniz, çünkü bunlar sadece ham işaretçilerdir ve Jule'ün kesit (slice) veya dizi yapıları gibi hemen uzunluğu almanın bir yolu yoktur.

Bu işlemi Güvenli Olmayan Jule tarafından kapsandığı gerçeği, sadece yaygın işaretçi güvensizliğine sahip olması nedeniyle değil, aynı zamanda taşma olasılığı ve bunun kontrol edilmemesi nedeniyle de kaynaklanır. Örneğin, kesit (slice) ve dizi bu konuda güvenli ve kontrol altındadır.

Bir dizi işaretçisine sahip olduğunuzda, bu semantik olarak şöyle yorumlanabilir: Bu, bileşen türüne işaret eden bir işarettir, çünkü işaretçi genellikle bellek alanlarından birine işaret eder. Bu nedenle, bir dizinin bir elemanının alanına işaret eden bir alanın işareti gibi düşünün. İndeksleme, ofsete bağlı olarak veri tipine duyarlıdır, bellekte bu kadar alanı atlayarak ofsetin konumunu bulur ve bu alanı seçer.

Veri tipi örnekleme konusunu daha iyi anlamak için dizi işaretçileri şu şekilde yorumlanabilir:
* `*int = []int`
* `*str = []str`

Örneğin: 
```jule
ptr[9]
```

Varsayalım ki `ptr` adlı değişken bir `*int` işaretçisidir. Bu işaretçinin bir dizi işaretçisi olduğunu düşünelim. Yukarıdaki ifade, bu dizinin 9. indisindeki veriyi alır.

## Ham İşaretçileri Dönüştürme (Cast Raw Pointers)

Bir işaretçiyi geçerli tamsayı türleriyle bir tamsayıya dönüştürebilir veya bir tamsayıdan ham bir işaretçiye dönebilirsiniz. Ancak aynı zamanda farklı bir türün işaretçisini başka bir türe dönüştürebilirsiniz.

Örnek olarak:
```jule
let ptr: int = 0;
let unsafe_ptr = unsafe { (*str)(ptr); }
```

## İşareti Bir Referansa Geçirme (Pass Pointer to Reference)

Eğer işaretçilerinizi bir referans parametresine geçirmek isterseniz, bunu basit bir işaretçi derecelendirmesi ile yapabilirsiniz. Bu zaten Güvenli Olmayan Jule kullanarak gerçekleştireceğiniz bir eylem olduğunuzun bilincindesinizdir.

Örnek olarak:
```jule
my_function(unsafe { *my_pointer });
```