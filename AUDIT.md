# OmniForge Hukuk AI — doğrulama başlangıcı

Tarih: 2026-11-07

## Kanıt standardı
- 38 ana özelliğin kesin listesi henüz doğrulanmadı. Başlık veya kabul kriteri uydurulmaz.
- Daha önce tamamlandığı belirtilen 3–4 özellik, test çıktısı ve kaynak commit ile yeniden doğrulanmadan tamamlandı sayılmaz.
- Kaynakta kodun bulunması, çalışan ürün veya başarılı uçtan uca test anlamına gelmez.
- Her özellik için: gereksinim, kaynak yolu, commit SHA, test komutu, test sonucu, engel ve kanıt bağlantısı kaydedilir.
- Gerçek hukuki veriler, API anahtarları, özel dava belgeleri ve kişisel veriler herkese açık depoya taşınmaz.

## İncelenen kaynak adayları (henüz OmniForge ile eşleştirilmedi)
1. https://github.com/yaman0786/hukuk-asistani — web/iOS yapılandırması ve docs dizini.
2. https://github.com/yaman0786/hukuk-bosluk-tarayici — Swift iOS kaynakları, HukukBoslukTarayiciTests ve LinuxTests; README v0.4.

## 38 özellik için durum
- Hedef: 38
- Resmî 1–38 liste: bulunamadı
- Kabul testleriyle bu çalışmada doğrulanan: 0
- Henüz doğrulanamayan: 38 (bu, 38'inin bozuk olduğu anlamına gelmez)
- Kaynak kod aktarımı: yapılmadı; hangi deponun asıl ürün olduğu belirlenmeli.

## Öncelikli işlemler
1. Önceki kabul testlerinin ve 38 maddelik listenin asıl kaynaklarını tespit et.
2. Kaynak adaylarını bağımsız olarak incele; özelliklerin proje eşleşmesini kanıtla.
3. Kişisel veri ve sır taraması yapmadan public depoya kod/DB kopyalama.
4. Her maddeyi uçtan uca test et, düzelt, yeniden test et ve kanıtı burada kaydet.

Bu dosya bir başlangıç denetim kaydıdır; ürünün tamamlandığı iddiası değildir.
