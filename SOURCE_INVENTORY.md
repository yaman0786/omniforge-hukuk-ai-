# Kaynak Envanteri — 2026-11-07

Bu dosya, GitHub API üzerinden gerçekten görülen dosya yollarını kaydeder. Bunlar **çalıştırılmış test sonucu değildir**.

## Kaynak A: hukuk-bosluk-tarayici
- Kaynak ağacı SHA: `641f81decef29a8d302d5cfd3ba540ed3462145d`
- Swift uygulaması: `HukukBoslukTarayici/`
- Testler: `HukukBoslukTarayiciTests/EngineTests.swift`, `SQLiteDatabaseTests.swift`, `SessizlikTests.swift`
- Linux testleri: `LinuxTests/main.swift`, `LinuxTests/SessizlikTests.swift`, `LinuxTests/run_linux_tests.sh`
- Yapılandırma: `project.yml`
- Kaynak: https://github.com/yaman0786/hukuk-bosluk-tarayici

## Kaynak B: hukuk-asistani
- Kaynak ağacı SHA: `5902c47077a34a1e355ae7c276fa89bf3de00cad`
- Web uygulaması: `src/`, `package.json`, `vitest.config.ts`
- Testler: `src/data/case-law-corpus.test.ts`, `src/lib/abuse-guard.server.test.ts`, `src/lib/citations.test.ts`, `src/lib/rag-contract.test.ts`, `src/lib/rate-limits.test.ts`
- iOS köprüsü: `ios/App/CapApp-SPM/`
- Kaynak: https://github.com/yaman0786/hukuk-asistani

## İnceleme kararı
İki kaynak farklı mimariler kullanıyor: A Swift/iOS; B TypeScript/web + iOS köprüsü. Rastgele birleştirmek yerine iki ayrı bileşen adayı olarak tutulacak. Bir sonraki işlem, her iki test grubunun içeriğini ve çalıştırılabilir komutlarını doğrulamaktır. Kod henüz taşınmadı; testler çalıştırılmadı. 38 özellikten kanıtlanmış tamamlanan: 0.
