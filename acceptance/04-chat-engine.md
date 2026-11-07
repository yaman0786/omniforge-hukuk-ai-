# Özellik 4 — Profesyonel yapay zekâ sohbet motoru: kabul incelemesi

Tarih: 2026-11-07
Kaynak: https://github.com/yaman0786/hukuk-asistani

## İncelenen kod
- `src/routes/api/chat.ts`: POST sohbet, kimlik doğrulama, konuşma sahipliği, kullanıcı bazlı kota, dosya limitleri, RAG bağlamı ve streaming.
- `src/lib/ai-gateway.server.ts`: Lovable AI gateway bağlantısı.
- `src/lib/rag-contract.ts` ve `src/lib/rag-contract.test.ts`: kaynak işaretçisi kontrolü.
- `package.json`: `npm test` = `vitest run`; `npm run build` = `vite build`.

## Tespit edilen doğruluk açığı
`assessGrounding` herhangi bir `[Kaynak: ...]` veya `[Genel İlke]` işaretçisini yeterli sayıp `requiresVerification: false` döndürüyor. İşaretçi, kararın/kanun maddesinin gerçekten var olduğunu, güncel olduğunu veya iddiayı desteklediğini doğrulamaz. Mevcut `rag-contract.test.ts` bu davranışı 'grounded' olarak bekliyor. Bu nedenle yalnızca mevcut testlerin geçmesi, hukuki doğruluk kabul kriterini karşılamaz.

## Kabul testleri (henüz yürütülmedi)
1. Yetkisiz POST -> 401; başkasına ait konuşma -> 404.
2. Geçerli kullanıcı ve konuşmada mesaj gönderimi -> akış yanıtı ve kayıt.
3. Sahte `[Kaynak: Yargıtay E.9999/9999]` -> doğrulanmış kaynak olarak işaretlenmemeli.
4. `[Genel İlke]` -> doğrulanmış hukuki dayanak olarak işaretlenmemeli.
5. Gerçek kaynak doğrulaması başarısızsa -> açık doğrulama uyarısı.
6. 429 kota, 413 büyük girdi, 400 geçersiz dosya, sağlayıcı kesintisi ve yarım kalan akış senaryoları.
7. Kaynak erişimi, hukuki cevap, alıntı ve atıf doğruluğu; Türkçe ve mobil istemci akışı.

## Durum
- Kaynak kodu incelendi: EVET.
- Açık tespit edildi: EVET (kaynak işaretçisi doğrulama yerine geçiyor).
- Çalışan servis üzerinde uçtan uca test: HAYIR.
- Düzeltme kaynak depoya uygulandı: HAYIR.
- %100 kabul: HAYIR.

Sonraki adım: kaynak işaretçisi kontrolünü 'kaynak beyanı var' olarak yeniden adlandırıp bağımsız kaynak doğrulama kapısı eklemek, mevcut beklentileri düzeltmek ve testleri gerçek ortamda çalıştırmak.
