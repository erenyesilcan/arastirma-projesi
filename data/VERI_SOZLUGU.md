# Veri sözlüğü: Higher Education Students Performance Evaluation

Kaynak: UCI ML Repository, DOI 10.24432/C51G82, CC BY 4.0. Kodlar UCI sayfasındaki değişken tablosundan alınmıştır.

| Sütun | Değişken | Kodlar | Bu projede |
|---|---|---|---|
| STUDENT ID | Öğrenci sıra no | STUDENT1–145 | `ogrenci_no` |
| 1 | Yaş | 1: 18-21, 2: 22-25, 3: 26+ | `yas_grubu` |
| 2 | Cinsiyet | 1: kadın, 2: erkek | `cinsiyet` |
| 3 | Mezun olunan lise türü | 1: özel, 2: devlet, 3: diğer | – |
| 4 | Burs türü | 1: yok, 2: %25, 3: %50, 4: %75, 5: tam | – |
| **5** | **Ek işte çalışma** | **1: evet, 2: hayır** | `ek_is` → `calisiyor` |
| 6 | Düzenli sanat/spor etkinliği | 1: evet, 2: hayır | – |
| 7 | Partner | 1: evet, 2: hayır | – |
| 8 | Toplam gelir | 1: 135-200 USD … 5: 410+ USD | – |
| 9 | Üniversiteye ulaşım | 1: otobüs, 2: özel araç/taksi, 3: bisiklet, 4: diğer | – |
| 10 | Konaklama | 1: kira, 2: yurt, 3: aile, 4: diğer | – |
| 11–16 | Anne/baba eğitimi, kardeş sayısı, aile durumu, anne/baba mesleği | – | – |
| **17** | **Haftalık ders çalışma** | **1: hiç, 2: <5 sa, 3: 6-10 sa, 4: 11-20 sa, 5: >20 sa** | `haftalik_calisma` |
| 18–21 | Okuma sıklığı, seminer katılımı, projelerin etkisi | – | – |
| **22** | **Derse devam** | **1: her zaman, 2: bazen, 3: hiç** | `devam` → `derse_her_zaman` |
| 23–28 | Sınava hazırlık, not alma, dinleme, tartışma, ters yüz sınıf | – | – |
| **29** | **Son dönem kümülatif GNO** | **1: <2.00, 2: 2.00-2.49, 3: 2.50-2.99, 4: 3.00-3.49, 5: >3.49** | `kum_gno` → `gno_3_ustu` |
| 30 | Beklenen mezuniyet GNO | 29 ile aynı | `beklenen_gno` |
| COURSE ID | Ders kodu | 1–9 | `ders` (karıştırıcı kontrolü) |
| **GRADE** | **Dönem sonu notu** | **0: FF, 1: DD, 2: DC, 3: CC, 4: CB, 5: BB, 6: BA, 7: AA** | `not_kodu` |
