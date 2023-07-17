# Attribute'ler


Attribute, bir programlama dilinde bir tanımı veya bir program öğesini belirli bir özellik veya davranışla işaretlemek için kullanılan bir yapıdır. Attributeler, derleyicilere veya çalışma zamanına belirli talimatlar veya meta veriler sağlar ve bu sayede programın derleme veya çalışma sürecinde özel bir işlem yapılmasını veya belirli bir davranışın uygulanmasını sağlar.

Attributeler, programın işlevselliğini veya performansını etkilemek, hata ayıklama veya hata kontrolünü sağlamak, bellek veya kaynak yönetimini optimize etmek, kod analizi yapmak veya veri serileştirmeyi kontrol etmek gibi birçok farklı amaç için kullanılabilir.

Attributeler, programcılara kodlarını daha esnek ve belirli gereksinimlere uygun hale getirme imkanı sağlar ve genellikle bir derleyici veya çalışma zamanı tarafından kullanılarak belirli işlemlerin gerçekleştirilmesini sağlar.

## Attribute'lerin Tanımlanması
Jule içerisinde Attributeler, tanımları belirli nedenlerle işaretlemek ve bunları derleyiciye bildirmek için kullanılır. Her bir attribute, yorum pragma (jule:) ile tanımlanır ve attribute kendisi pragma'dan hemen sonra gelmelidir.
```jule
//jule: ornek_attribute
fn my_func(): int {
    // ...
}
```

```jule
//jule: ornek_attribute_2
//jule: bir_diger_attribute
fn my_func(): int {
    // ...
}
```