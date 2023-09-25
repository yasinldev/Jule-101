# Güvensiz Tanımlar

## Güvensiz Fonksiyonlar veya Metotları Çağırma

Güvensiz Jule (Unsafe Jule) ile güvensiz fonksiyonları çağırabilirsiniz. Güvensiz olarak nitelendirilen fonksiyonlar veya metotlar yalnızca Güvensiz Jule ile çağrılabilirler. Güvensiz olarak nitelendirilen fonksiyonlar yalnızca Güvensiz Jule ile çağrılabilir ve bu fonksiyonlar tüm vücutları boyunca bir Güvensiz Jule içermelidir.

Örnek olarak:
```jule
unsafe fn my_unsafe_fn() { /* ... */ }
```
> **İpucu** <br>
> Bir fonksiyonu veya metodu güvensiz olarak nitelendirmeden önce, fonksiyonun her zaman güvenli olmadığından emin olun. Eğer fonksiyon güvensiz işlemler gerçekleştiriyorsa, güvenlik garanti altındaysa, fonksiyonun güvenli bir sarmalayıcı olarak çalışması, güvensiz olarak nitelendirmekten daha iyidir. <br><br>
> Eğer güvenlik parametrelere ve diğer dış faktörlere bağlıysa, o zaman güvensiz olarak nitelendirmek daha iyidir.

