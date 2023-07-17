# Bloklar

Jule dilinde bloklar, bir veya daha fazla ifadeyi gruplamak ve bu ifadelerin birlikte çalışmasını sağlamak için kullanılan yapısal bir bileşendir. Bloklar, genellikle kontrol yapıları (if, for, while vb.), fonksiyonlar veya anonim fonksiyonlar içinde kullanılır ve bir kod parçasını belirli bir kapsam veya çalışma birimi olarak tanımlar.

Bloklar, istisnai durumlar dışında süslü parantezlerle belirtilir. Her blok bir kapsamı temsil eder. Bir blok genellikle bir algoritma alanını belirtmek için kullanılsa da, başka amaçlar için de kullanılır.

Bir blok, tekrardan dediğimiz gibi genellikle süslü parantezler ``{}`` arasında tanımlanır ve içerisindeki ifadeleri içerir. Blok içindeki ifadeler, belirli bir sıra veya mantık çerçevesinde çalıştırılır. <b>Aynı zamanda, blok içinde tanımlanan değişkenler de yalnızca blok içinde erişilebilir olabilir.</b>

Blok yapısı, kodun okunabilirliğini artırır ve ifadelerin bir grup olarak işlenmesini sağlar. Örneğin, bir kontrol yapısı içinde belirli bir koşula bağlı olarak birden fazla ifadeyi çalıştırmak veya bir döngü içinde tekrarlanan ifadeleri gruplamak için bloklar kullanılabilir.

## Anonim Bloklar

Anonim bloklar, Jule içerisinde isimsiz veya adlandırılmamış bloklardır. Bu bloklar genellikle belirli bir kod parçasını gruplamak ve bir kapsam içinde çalıştırmak için kullanılır

Anonim bloklar genellikle şu durumlarda kullanılır:

* Özel bir fonksiyon tanımlamadan veya mevcut bir fonksiyon dışında bir kod parçasını çalıştırmak istediğinizde. Bu bloklar, bir blok içindeki değişkenlerin kapsamlarını sınırlar ve geçici işlemler için kullanışlıdır.
* Bir kontrol yapısı içinde, belirli bir koşula bağlı olarak çalışacak ek kod parçacıkları eklemek için kullanılır.
* Bir döngü içinde tekrarlanan işlemleri gruplamak ve bu işlemleri farklı bir kapsam içinde yürütmek için kullanılabilir.

Örneğin, aşağıdaki örnekte, ``main`` fonksiyonu içerisinde anonim bir fonksiyon tanımlanmıştır. 

 ```jule
fn main() {
    {
       // Burası anonim bir bloktur.    
    }
}
```

## Deferred (Ertelenmiş) Bloklar

Jule içerisinde ertelenmiş bloklar, bir işlemi veya bir kod parçasını içerisinde bulunduğu kapsam bitene kadar erteler. Bu bloklar, genellikle bir kaynak açma, kapatma veya temizleme işlemi gibi özel işlemlerin gerçekleştirilmesi gereken durumlarda kullanılır.

Ertelenmiş bloklar genellikle şu durumlarda kullanılır:
* Hata temizleme: Bir işlem sırasında bir hata oluşursa, işlemin geri kalanını temizlemek ve kaynakları serbest bırakmak gerekebilir. Ertelenmiş bloklar, hata durumunda çalıştırılacak olan kod parçalarını belirlemek ve otomatik olarak temizlik işlemlerini gerçekleştirmek için kullanılabilir.

Örneğin, aşağıdaki örnekte, çıktı "Hello World" ifadesinden önce görünür. Bunun nedeni, ertelenmiş bloğun fonksiyonun kapsamında tanımlanmış olması ve yürütülmesinin fonksiyonun kapsamından çıkıncaya kadar ertelenmiş olmasıdır.

```jule
fn main() {
    defer {
        outln("Hello Defer")
    }
    outln("Hello World")
}
```

## Unsafe (Güvensiz) Bloklar

Jule içerisinde güvensiz bloklar, güvenlik önlemlerini kaldıran veya devre dışı bırakan özel bloklardır. Bu bloklar, genellikle düşük seviye işlemler yapmak veya bellek yönetimini doğrudan kontrol etmek gibi özel durumlar için kullanılır.

Örneğin, aşağıda ``main`` fonksiyonu içerisinnde güvensiz bir blok tanımlanmıştır.

```jule
fn main() {
    unsafe {
        // Burası güvensiz bir bloktur.
    }
}
```

## Deferred Unsafe Bloklar 

Ertelenmiş güvensiz bloklar, Jule içerisinde güvensiz (unsafe) işlemlerin gerçekleştirilmesini ertelemek için kullanılan bir yapıdır. Bu bloklar, güvensiz işlemleri, içerisinde bulunduğu kapsam bitene kadar ertelemek ve güvenlik katmanlarını geri yüklemek için kullanılır.

Örneğin, aşağıda ``main`` fonksiyonu içerisinnde ertelenmiş güvensiz bir blok tanımlanmıştır.

```jule
fn main() {
    unsafe defer {
      // Burası ertelenmiş güvensiz bir bloktur.
    }
}
```