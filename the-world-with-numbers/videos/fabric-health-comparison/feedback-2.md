# Feedback Round 2

<!-- Videoyu izleyip notlarını buraya yaz -->

## Genel
- ✅ YAPILDI — sahneler ve scriptleri arasinda bir stalelik durumu mu var? → Video source of truth olarak kabul edildi, JSON description'lar güncellenmedi (video esas).
- ✅ YAPILDI — hala kucuk yazilar var, mobile friendly olamiyoruz → Counter font sizes %20-25 artırıldı (main 220px, title 36px, subtitle 28px, suffix 88px), bar maxWidth 1200px
- ✅ YAPILDI — genel olarak 14. sahne bence bar chart kullanimi icin iyi → Referans alındı, değişiklik gerekmedi
- ✅ YAPILDI — glitch textleri kullanma, ContainerTextFlip kullan → GlitchTextOverlay tamamen kaldırıldı, FlipTextOverlay component'i ContainerTextFlip pill kullanıyor. Sequence-based timing, dynamic fontSize (44-96px), tüm sahnelerde çalışıyor.
- genel olarak cok buyuk gelisme var eline saglik

## Sahne Bazli
- ✅ YAPILDI — 1, 2, 7, 8, 12, 21 sahne hala cok kucuk → Counter.tsx tüm font boyutları artırıldı, bar maxWidth 1200px
- ✅ YAPILDI — 2deki sonradan gelen yaziyi glitch yapma. ContainerTextFlip → texts: ["eco-friendly", "does not mean safe"] ile multi-text cycling, pill style
- ✅ YAPILDI — 4, ve 5 cok yukarida. 5. sahnede ses 67% diyo gorsel 69 → Timeline MID_Y 180→240, PieChart size 700→620, scene-005 value 69→67% düzeltildi, title "Fast Fashion Fiber Analysis"
- ✅ YAPILDI — 6 bence yatay barlar olmali → orientation: "vertical" → "horizontal" değiştirildi
- ✅ YAPILDI — 7de sonradan gelen kirmizi yaziyi ContainerTextFlip with pill ile getirelim → FlipTextOverlay pill, color #D94F4F, phase 2
- ✅ YAPILDI — 9 biraz daha dar ama uzun hale getir → maxWidth: 880 wrapper, bar height 48→72
- ✅ YAPILDI — 10 grafigin basligi yok, renk tutarsızlığı → groupTitle: "Formaldehyde Content" eklendi, secondary colors #E06070→#E88CA5
- ✅ YAPILDI — 11, 15 sahneler ekranin cok yukarisinda durmus → ScaleComparison flex:1 kaldırıldı (centering fix)
- ✅ YAPILDI — 13 barlar biraz daha kalin, yazilar kucucuk → DuelComparison bar height 44→70, fonts +4-6px, maxWidth 900, metric row gap 28→40
- ✅ YAPILDI — 15 ContainerTextFlip pill, konumu ortaya → position top-center→center, phase 2 pill
- ✅ YAPILDI — 16 bar kullanimi yanlis, baska bi sey bulalim → Counter type'a dönüştürüldü: 3 breakdown item (Min 58y, Max 1200y, Human lifespan 80y)
- ✅ YAPILDI — 19 daha genis kullansin ekrani → Vertical bar width ≤5 items: 120→160, gap 32→24
- ✅ YAPILDI — 20 cok ince barlar → Bar height 56→84, label/value fontSize 26→30
- ✅ YAPILDI — 21 bu grafik ne anlatiyo anlamak guc → Confusing breakdown items kaldırıldı, DNA damage info subtitle'a taşındı
- ✅ YAPILDI — 22 sag taraftaki paneli frosted panel ve tiltli yapalim + panel transition → FrostedPanelSurface+TiltCard InfoPanel'e uygulandı, translateX→translateY slide transition
- ✅ YAPILDI — 23 iki tarafi da frost panel ve tiltli yapalim, vs gereksiz → Both headers FrostedPanel+TiltCard, VS divider kaldırıldı
- ✅ YAPILDI — 24 glitch -> ContainerTextFlip pill, baslikla icerik uzak → FlipTextOverlay pill "FIBER ≠ SAFETY" phase 2 center, ScaleComparison title marginBottom 48→24
- ✅ YAPILDI — 25 kirmizi text gelince kalani kaybolmasin → keepChartVisible: true + FlipTextOverlay pill bottom-center phase 2
- ✅ YAPILDI — 26 22ye yapilan yorumlar gecerli → Aynı FrostedPanel+TiltCard+translateY fix uygulandı
