# Kutuphane Yonetim Sistemi (Java Swing)

Kirklareli Universitesi **Yazilim Mimarisi ve Tasarimi** dersi icin dort
kisilik bir grupla gelistirilen masaustu uygulamasi. Kitap, ogrenci ve
ogretim gorevlisi kayitlarinin tutuldugu, odunc alma ve iade islemlerinin
yapildigi bir kutuphane otomasyonu.

> Ayrintili proje aciklamasi, grup uyeleri ve dosya listesi icin:
> [`javaodev/README.md`](javaodev/README.md)

## Uygulanan tasarim kaliplari

Dersin konusu geregi proje bir CRUD uygulamasindan cok, kaliplarin
uygulanmasi uzerine kuruldu:

| Kalip | Nerede |
|---|---|
| **Builder** | `BookBuilder.java` -- kitap nesnesinin adim adim olusturulmasi |
| **Factory** | `Factory.java` -- kullanici turune gore nesne uretimi |
| **State** | `IState.java`, `StateAvailable`, `StateTaken`, `StateHidden` -- kitabin durumu (musait / odunc alinmis / gizli) |
| **Observer** | `RAbstractObserver.java`, `ObserverBookInfo`, `ObserverNotice` -- iade tarihi bildirimleri |
| **Singleton benzeri oturum** | `Session.java` -- giris yapan kullanicinin tutulmasi |
| Arayuz sozlesmesi | `ICrud.java` -- ekleme/guncelleme/silme islemleri |

## Yetkilendirme

Uc ayri giris ekrani var ve yetkiler farkli:

- **Admin** -- kitap, ogrenci ve ogretmen kayitlari uzerinde tam yetki
- **Ogretmen** ve **Ogrenci** -- yalnizca kitap odunc alma ve iade; odunc
  aldiklari kitabin son teslim tarihini bildirim olarak goruyorlar

## Calistirma

Gereksinimler: JDK 8+, MySQL, MySQL Connector/J

1. Veritabanini olusturun -- komutlar
   [`javaodev/Database/SQLCreateDatabaseCommands.txt`](javaodev/Database/SQLCreateDatabaseCommands.txt)
   dosyasinda hazir duruyor (`library` veritabani, `admin`, `bookings` ve
   kitap/ogrenci/ogretmen tablolari).
2. `DatabaseConnector.java` icindeki baglanti bilgilerini kendi ortaminiza
   gore duzenleyin.
3. Projeyi NetBeans ile acin (`.form` dosyalari NetBeans'in Swing arayuz
   tasarimcisina ait) ve `StartPage.java` sinifini calistirin.

## Not

Bu bir grup projesidir; depodaki kodun tamami tek bir kisiye ait degildir.
Bu nedenle depoya acik kaynak lisansi eklenmedi.
