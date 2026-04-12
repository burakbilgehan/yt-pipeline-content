## genel yorumlar
- [x] container text flipler geldikleri sahnenin uzerinde gozuksunler. genellikle arkalarindaki sahne icerigi kayboluyor container text flip gelince, bunu yapma. text flipler zaten bir container icinde ve okunabilir durumda. ayrica arka planlarini frosted panel ya da FrostedPanel-Card buradaki card gibi yapacagimiz icin hicbir okuma sikintisi olmaz. sahne 2, 7, 15, 24
  - ✅ Sahne 2, 7: `keepChartVisible: true` + `position: "top-center"` — counter sahnelerde pill üstte, chart altta kalıyor
  - ✅ Sahne 15, 24: Bar chart sahnelerde annotation çakışması nedeniyle keepChartVisible kaldırıldı, standart phase 2 fade-out kullanılıyor
- [x] VerticalTabScene'in solundaki cetvelde yazanlarla sagdaki buyuk onizlemenin icinde yazanlar birebir ayni olmamali. solda daha overview. 1 baslik 1 cumle. sagda ise stok foto olabilir.
  - ✅ Sahne 22, 26: 8 adet stok foto (Pexels) indirildi, scene JSON'lara image field'ları eklendi — sağ panelde artık stok foto gösteriliyor

## sahne bazli yorumlar

- [x] sahne 2 ve 7de sonradan gelen kutucuklu yazilar sahnenin ustunde dursun, sahnenin ilk yarisinda gozuken ekran kaybolmasin
  - ✅ `keepChartVisible: true` + `position: "top-center"` ile çözüldü. PhaseAwareChart phase 2'de %55 opacity'ye düşüyor.
- [x] sahne 4, 5 ve 11 ekranin cok yukari kisminda toplanmis. biraz daha ortala
  - ✅ Sahne 4, 5: Centering doğrulandı, sorun yok. Sahne 11: bar-chart horizontal'a dönüştürüldü (sahne 6 referans).
- [x] sahne 4te ilk 3 numara mutlak, son numara yuzdeli. ilk 3unu de market share acisindan yuzdeli gosterebilir miyiz? datamiz var mi? tts'i degistirmememize gerek yok. ayrica gorsellerde yine mutlak rakamlar dursun, altlarina parantez icinde yuzdelik paylasim yazilsin
  - ✅ Timeline displayValue'larına parantez içinde market share % eklendi
- [x] sahne 10da iki baslik farkli renk ve sekillerde. ikisini de ayni stilde yapalim ![formaldehit content ve formaldehit emmision yazan yerler](image-19.png)
  - ✅ BarChart component'ında secondaryChart render edilirken `title` yerine `groupTitle` kullanılarak stil tutarsızlığı düzeltildi
- [x] 9, 11, 13, 15, 24u sahne 6daki gibi yap gorsel olarak. bu sahnelerin ekran kullanimi ve component secimlerini begenmedim. sahne 6 yeterince iyi
  - ✅ Tümü `comparison`/`scale-comparison` → `bar-chart` horizontal formatına dönüştürüldü (sahne 6 referans)
- [x] sahne 16da hem minimum hem maximumu pembe yap. human lifespan mavi
  - ✅ Minimum ve Maximum barlar pembe (#E88CA5), Human lifespan mavi (#7BA7C9) yapıldı
- [x] sahne 18 yine ContainerTextFlip with pill kullansin. arkaplanin dokusu olarak da FrostedPanel-Card'teki ikisinden birini kullan
  - ✅ textOverlay lines → ContainerTextFlip texts formatına dönüştürüldü + FrostedPanel surface eklendi
- [x] sahne 22 ve 26'nin sag panelindeki icerigi soldakinden farkli olsun. tiltli container iyi. ama icini gerekirse stok fotoyla doldurmaliyiz.
  - ✅ 8 adet stok foto (Pexels) indirildi, scene JSON'lara image field'ları eklendi
- [x] sahne 23 ![alt text](image-21.png) hem merino hem de polyesterin kendi containeri olmali. bu conteinerlar materyalin adi ve 3 kategorideki kendi iceriklerini tutmali. yani ekranin solunda 1 saginda 1 container bulunmali ve solunda pembeyle merino saginda maviyle ile polyester olmali. ayrica bu containerlar yavasca tilt etmeli. merinoya NeonGradient-Backlight buradaki gibi backlight da verelim.
  - ✅ SplitComparison'a "material-duel" modu eklendi — Merino (backlight, pembe) sol, Polyester (frosted-panel, mavi) sağ, TiltCard animasyonu
  - ✅ (Round 2) NeonGradient kaldırıldı, Backlight efekti çok subtle yapıldı (opacity 0.08-0.18, 4s pulse, 80px blur)

## feedback round 2

- [x] ContainerTextFlip render glitch — harfler random sırayla render oluyordu
  - ✅ Per-character stagger kaldırıldı, whole-text blur-fade'e geçildi. Render-safe.
- [x] Sahne 22/26 tilt çok hızlı ve agresif
  - ✅ TiltCard speed 1.5 → 0.3 (maxTilt=12 korundu, yavaş/smooth hareket)
- [x] Sahne 23 backlight efekti çok yapay ve abartılı
  - ✅ BacklightSurface yerine inline subtle glow: opacity 0.08-0.18, 4s pulse, 2.5px drift, radial-gradient
- [x] Sahne 24 chart hala kayboluyordu
  - ✅ keepChartVisible: true + position: top-center eklendi (önceki round'da halledildi)
