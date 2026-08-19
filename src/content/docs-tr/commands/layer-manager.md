---
title: LayerManager Komutu — Tüm Katmanları Tek Tabloda Yönetin
description: LayerManager komutu, çizimdeki tüm katmanların tablosunu açar; katman ekleyebilir ve her katman için dondurma, kilitleme, yazdırma, renk, çizgi kalınlığı ve çizgi türünü doğrudan düzenleyebilirsiniz.
keywords: [layer manager CAD, CAD katman tablosu, katmanları yönet CAD, katman ekle CAD, dondur kilitle yazdır katman, kulmanlab katman yönetimi]
group: layer
order: 1
---

# LayerManager

`LayerManager` komutu, çizimdeki tüm katmanları listeleyen bir tablo açar; **Freeze** (dondur), **Lock** (kilitle), **Plot** (yazdır), **Renk**, **Çizgi Kalınlığı** ve **Çizgi Türü** ayarları doğrudan satırda düzenlenebilir. Yeni katmanlar eklemek ve mevcut katmanların davranışını ayarlamak için merkezi yerdir — diğer katman komutları ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) her biri onu açmadan tek bir odaklı işi yapar.

## Layer Manager'ı Açma

- Terminale `LayerManager` yazın, **veya**
- Katman panelindeki **Layer Manager** düğmesine tıklayın.

İletişim kutusu yüzen bir panel olarak açılır; önceden hiçbir şey seçili olması gerekmez.

## Katman Tablosu

| Sütun | Neyi kontrol eder |
|-------|----------------------|
| Name | Katmanın adı, tabloda salt okunur gösterilir (yalnızca oluşturulurken bir kez ayarlanır) |
| Freeze | Katmanın nesnelerini gizler ve çözülene kadar seçimden hariç tutar |
| Lock | Katmandaki nesnelerin gizlenmeden düzenlenmesini engeller |
| Plot | Katmanın nesnelerinin yazdırma veya PDF dışa aktarmaya dahil edilip edilmeyeceği |
| Color | Katmanın ACI rengi — renk seçiciyi açmak için örneğe tıklayın |
| Lineweight | Katmanın çizgi kalınlığı — kalınlık seçiciyi açmak için çipe tıklayın |
| Linetype | Katmanın çizgi deseni — çizgi türü seçiciyi açmak için çipe tıklayın |

Freeze, Lock veya Plot'u değiştirmek anında etkili olur — ayrı bir kaydetme adımı yoktur. Renk, çizgi kalınlığı veya çizgi türü için **ByLayer** (varsayılan) olarak ayarlanmış nesneler burada belirlediğinizi alır; kendi açık geçersiz kılmasına sahip nesneler etkilenmez.

## Katman Ekleme

1. Tablonun altındaki **+ Add Layer**'a tıklayın.
2. Bir ad yazın ve onaylamak için **Enter**'a, iptal etmek için **Escape**'e basın.

Katman adları harf, rakam, boşluk ve `_`, `-`, `$` içerebilir. Boş, zaten kullanımda olan veya başka bir karakter içeren bir ad, satır içi bir hatayla reddedilir ve satır yeni bir deneme için açık kalır.

Yeni katmanlar **çözülmüş, kilitlenmemiş, yazdırılabilir** olarak başlar; renk 7 (beyaz/siyah), çizgi kalınlığı Default ve çizgi türü Continuous ile — [Import](../import/)'un boş bir çizimde `0` katmanına atadığı varsayılanlarla aynıdır.

## Burada Yapamayacaklarınız

Silme düğmesi yoktur — katmanlar oluşturulduktan sonra asla kaldırılmaz, yalnızca dondurulabilir veya kullanılmadan bırakılabilir. Tablo ayrıca hangi katmanın *geçerli* olduğunu da göstermez; bu, katman panelindeki açılır menüden veya [LayerMakeCurrent](../layer-make-current/) ile ayarlanır, bu iletişim kutusundan değil.

## Klavye Referansı

| Tuş | İşlem |
|-----|-------|
| `Enter` | Yeni bir katmanın adını onayla (eklerken) |
| `Escape` | Katman eklemeyi iptal et, veya iletişim kutusunu kapat |

## İlgili Komutlar

| Komut | Ne yapar |
|-------|----------|
| [LayerMakeCurrent](../layer-make-current/) | Tıklanan nesneye göre geçerli katmanı ayarlar |
| [LayerMatch](../layer-match/) | Seçili nesneleri kaynak nesnenin katmanına yeniden atar |
| [LayerIsolate](../layer-isolate/) | Seçili nesnelerin katmanları dışındaki tüm katmanları dondurur |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Tüm katmanları tek adımda çözer |
