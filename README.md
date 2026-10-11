# Kelime Koşusu 🏃📚

Türkçe yazım kurallarını çalıştıran, mahalle sokaklarında geçen iki şeritli koşu oyunu.

## Nasıl oynanır?

- **Normal tur:** İki şeritte iki farklı yazım görünür. Koşucuyu doğru yazımın olduğu şeride geçir.
- **Her üçüncü tur:** **2 şerit × 2 yükseklik = 4 seçenek** çıkar; bunlardan yalnızca biri doğrudur. Alttaki kelimeden geçmek için yerde kal, üsttekine ulaşmak için zıpla.
- **Yol engelleri:** Engelin bulunduğu şeridi değiştir veya üzerinden zıpla. Her zaman engelsiz bir şerit vardır; engeller kelime kapılarıyla aynı çizgide oluşturulmaz.
- Yanlış yazımı seçmek ya da engele çarpmak bir can kaybettirir. Toplam **3 can** vardır.
- Doğru cevaplarla puan ve seri bonusları kazanılır. Oyun sonunda doğru, yanlış ve engele çarpma sayıları gösterilir.

## Kontroller

| Eylem | Bilgisayar | Telefon / tablet |
| --- | --- | --- |
| Şerit değiştir | Sol / sağ ok veya A / D | Ekranın sol / sağ tarafına dokun veya sağa / sola kaydır |
| Zıpla | Yukarı ok, W veya Boşluk | **ZIPLA** düğmesi veya ekranın üzerinde yukarı kaydırma |
| Hızlan | Shift (basılı tut) | **HIZLAN** düğmesine basılı tut, ya da kısa dokunarak 2,5 saniyelik turbo başlat |
| Üstteki kelimeyi seç | Şeride geç ve doğru zamanda zıpla | Üst kelime kartına dokun: zıplama geçişe yakın otomatik zamanlanır |

> Dört seçenekli turda üstteki kelimeye tıklamak otomatik zıplamayı hazırlar; manuel zıplama da kullanılabilir.

## Proje yapısı

- `index.html`: Oyun, Three.js sahnesi, kontroller, müzik ve soru havuzu.
- İnternet bağlantısı ilk açılışta Three.js kütüphanesini CDN üzerinden yüklemek için gereklidir.
- Soru havuzu `WORD_PAIRS`, dört seçenekli özel sorular `FOUR_CHALLENGES` dizisinde yer alır.

Bu sürümde oyun içi reklam veya uygulama içi satın alma **eklenmemiştir**; Google Play yayını ayrı bir paketleme, test ve mağaza süreci gerektirir.

## iPhone ve mobil ses

Safari'de ses motoru oyunu başlatma dokunuşuyla etkinleştirilir. Destekleyen cihazlarda müzik için `navigator.audioSession.type = 'playback'` kullanılır. Ses açma/kapatma düğmesi puan-can göstergesinin yanındadır. Müzik duyulmuyorsa medya ses düzeyini kontrol edin; Safari/iOS sürümüne ve sessiz mod ayarına bağlı farklar olabilir. Mobil sürüm etiketi: **1.4**.

## Cevap değerlendirmesi (1.4)

Bir sözcük kartına dokunarak cevap verildiğinde oyunda tam olarak o seçenek değerlendirilir. Dört seçenekli sorularda özellikle üstteki sözcüğün zıplama animasyonu gecikse bile seçimin yanlış sayılması önlenmiştir. Yalnızca koşarak veya zıplayarak geçişte fiilî şerit/yükseklik kullanılır. Önceki turun geri bildirimi 1,5 saniye sonra temizlenir; sonraki sorunun cevabıymış gibi kalmaz.
