# Yarı Zamanlı Çalışmanın Üniversite Öğrencilerinin Akademik Başarısı ve Derse Devamıyla İlişkisi

**Araştırma Yöntem ve Teknikleri, 2026–2027 Güz** · Marmara Üniversitesi, Bilgisayar Programcılığı
**Hazırlayan:** Eren Yeşilcan

[![Colab'da aç](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/erenyesilcan/arastirma-projesi/blob/main/notebooks/analiz.ipynb)

## Problem
Pek çok üniversite öğrencisi okurken yarı zamanlı çalışıyor. Bunun not ortalaması ve derse devamla ilişkisi literatürde tutarlı değil. Bu proje, açık bir veri setiyle bu ilişkiyi tekrarlanabilir biçimde inceler.

**Problem cümlesi:** Üniversite öğrencilerinin ek bir işte çalışma durumu ile akademik başarıları ve derse devamları arasında ilişki var mıdır?

**Alt problemler**
1. Öğrencilerin yüzde kaçı ek bir işte çalışıyor?
2. Çalışan ve çalışmayanların kümülatif not ortalaması farklı mı?
3. Dönem sonu ders notları farklı mı?
4. Derse devam çalışma durumuna göre farklılaşıyor mu?
5. Haftalık ders çalışma süresi ve derse devam, not ortalamasıyla ilişkili mi?

**Hipotezler (α = 0,05):** H₀: Çalışan ve çalışmayan öğrenciler arasında not ortalaması, ders notu ve derse devam açısından fark yoktur. H₁: Fark vardır.

## Yöntem
- **Desen:** Nicel, ilişkisel tarama · ikincil veri analizi
- **Yöntem değişikliği:** Proje başlangıçta Google Forms anketi olarak planlanmıştı. 26.10.2026 tarihli ders duyurusu doğrultusunda katılımcılardan veri toplanmamış, proje açık veriyle yeniden düzenlenmiştir.
- **Testler:** Mann–Whitney U (ana test), Welch t (karşılaştırma), Fisher kesin testi, Spearman ρ · keşif amaçlı karar ağacı (5 katlı çapraz doğrulama)

## Veri seti
| | |
|---|---|
| Ad | Higher Education Students Performance Evaluation |
| Kaynak | UCI Machine Learning Repository · https://archive.ics.uci.edu/dataset/856 |
| DOI | https://doi.org/10.24432/C51G82 |
| Oluşturanlar | Nevriye Yılmaz, Boran Şekeroğlu |
| Lisans | CC BY 4.0 |
| Boyut | 145 öğrenci × 33 sütun, eksik değer yok |
| Erişim tarihi | 23.11.2026 |
| Kişisel veri | Yok (`STUDENT ID` yalnızca sıra numarası) |

Ham dosya `data/higher_education_students_performance.csv` olarak değiştirilmeden saklanmıştır. Sütun kodlarının açıklaması için `data/VERI_SOZLUGU.md` dosyasına bakın.

## Klasör yapısı
```
├── README.md
├── data/                     ham veri + veri sözlüğü
├── notebooks/analiz.ipynb    Colab'da çalışan analiz
├── outputs/
│   ├── figures/              Şekil 1–4 (PNG)
│   ├── tables/               betimsel ve test tabloları (CSV)
│   └── sonuc.json            özet sonuçlar
├── docs/uml/                 Use Case, Class, Activity (.puml + .png)
└── rapor/                    vize raporu (.docx)
```

## Nasıl çalıştırılır?
**Google Colab:** `notebooks/analiz.ipynb` dosyasını açın, ardından *Çalışma zamanı → Tümünü çalıştır*. Veri bulunamazsa hücre CSV dosyasını yüklemenizi ister (`data/` klasöründeki dosyayı seçin).

**Yerel:**
```bash
pip install pandas scipy matplotlib scikit-learn jupyter
jupyter notebook notebooks/analiz.ipynb
```

## Özet bulgular
| | Çalışmıyor (n=96) | Çalışıyor (n=49) | Test |
|---|---|---|---|
| GNO ≥ 3.00 oranı | %45,8 | %42,9 | Mann–Whitney p = 0,690 |
| Dönem sonu not medyanı | CC | DC | Mann–Whitney p = 0,051 (sınırda) |
| Derse her zaman devam | %75,0 | %77,6 | Fisher p = 0,839 |

Derse her zaman devam etmek, not ortalamasıyla zayıf ama anlamlı biçimde ilişkilidir (Spearman ρ = 0,179, p = 0,031). Ayrıntılar raporda ve notebook'ta yer almaktadır.

## Sınırlılıklar
Tek üniversite ve 2019 verisi kullanılmıştır. Çalışma yalnızca evet/hayır olarak ölçülmüş, haftalık çalışma saati veride bulunmamaktadır. Değişkenler aralık kodlu ve öz bildirime dayalıdır. Kesitsel desen nedeniyle bulgular neden-sonuç ilişkisi göstermez.

## Yapay zekâ kullanımı
Analiz kodunun taslağı, UML diyagramlarının PlantUML kodu ve metin düzenlemesi için Claude (Anthropic) yapay zekâ asistanından yardım alınmıştır. Bütün kaynaklar özgün yayın sayfalarından doğrulanmış, bütün sonuçlar notebook'ta yeniden üretilebilir durumdadır.
