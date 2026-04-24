# Storyboard Summary — v1
**Video:** The 5 Chokepoints That Control Global Trade
**Scenes:** 25 | **Duration:** 785s (~13:05) | **Target:** 750s (4.7% over — within 15% tolerance)

## Scene Map

| ID | Section | Time | Duration | Visual Type | Key Visual |
|----|---------|------|----------|-------------|------------|
| 001 | Hook | 0:00-0:18 | 18s | world-map | 5 pulsing chokepoint dots on dark world map |
| 002 | Hook | 0:18-0:31 | 13s | counter | Brent crude $73→$119 stat card, glow surface |
| 003 | Hook | 0:31-0:35 | 4s | world-map | Map zoom out, bridge to next section |
| 004 | Five Chokepoints | 0:35-1:11 | 36s | title-card | Section title + EIA source |
| 005 | Five Chokepoints | 1:11-1:57 | 46s | horizontal-bar-chart | All 5 chokepoints compared by mb/d |
| 006 | Strait of Hormuz | 1:57-2:28 | 31s | world-map | Persian Gulf zoom, shipping lanes |
| 007 | Strait of Hormuz | 2:28-3:15 | 47s | composite (map→timeline) | Stats + Feb 28 strikes → Mar 2 closure |
| 008 | Strait of Hormuz | 3:15-3:51 | 36s | composite (line→progress-ring) | Price chart $73→$119 + bypass gauge |
| 009 | Strait of Hormuz | 3:51-3:58 | 7s | world-map | BLOCKED status, red indicator |
| 010 | Strait of Malacca | 3:58-4:33 | 35s | world-map | SE Asia zoom, ship traffic density |
| 011 | Strait of Malacca | 4:33-5:30 | 57s | composite (counter→map) | China 80% dependency + BRI routes |
| 012 | Strait of Malacca | 5:30-5:46 | 16s | world-map | "Never closed" — green pulse |
| 013 | Suez Canal | 5:46-6:21 | 35s | world-map | Route comparison: Suez vs Cape |
| 014 | Suez Canal | 6:21-6:57 | 36s | composite (counter→counter) | 4.9 mb/d stats + Ever Given $79.6B |
| 015 | Suez Canal | 6:57-7:25 | 28s | composite (timeline→bar) | 1967-75 closure + Houthi traffic drop |
| 016 | Panama Canal | 7:25-7:57 | 32s | composite (map→progress-ring) | Lock system + drought gauge |
| 017 | Panama Canal | 7:57-8:36 | 39s | composite (counter→bar) | $2.85M slot bid + LNG collapse |
| 018 | Panama Canal | 8:36-9:00 | 24s | counter | 2.3 mb/d + El Niño warning |
| 019 | Bab el-Mandeb | 9:00-9:35 | 35s | world-map | Red Sea zoom, 18-mile gap |
| 020 | Bab el-Mandeb | 9:35-10:26 | 51s | composite (timeline→bar) | Houthi attacks + traffic collapse |
| 021 | Bab el-Mandeb | 10:26-10:54 | 28s | world-map | Cascade arrows: Hormuz→Yanbu→Bab |
| 022 | Cascade Effect | 10:54-11:41 | 47s | world-map | All 5 connected by cascade arrows |
| 023 | Cascade Effect | 11:41-12:26 | 45s | composite (counter→map) | Oxford Martin $14B + dual crisis map |
| 024 | CTA | 12:26-12:58 | 32s | world-map | Recap cards per chokepoint |
| 025 | CTA | 12:58-13:05 | 7s | closing-sequence | Channel name + subscribe |

## NEEDS_COMPONENT

**WorldMapScene** — The primary new component needed for this video:
- Renders world map from GeoJSON polygons (Natural Earth 110m)
- SVG-based, Remotion-native (useCurrentFrame, interpolate, spring)
- Capabilities: zoom to region, highlight countries, animated chokepoint pins, shipping lane lines, pulse effects, route animations, sequential annotations
- Used in 14 of 25 scenes (001, 003, 006, 009, 010, 012, 013, 016, 019, 021, 022, 023, 024 + composites)
- Must be brand-palette compatible (bg=#2A2A32, country fills, accent highlights)

**counter-up (L3 motion)** — Status: planned (not yet implemented). Used in scenes 002, 011, 014, 017, 018, 023. Fallback: text-rotate or Counter template.

## Atmosphere Distribution
- **dot-grid**: 13 scenes (data-heavy, analytical)
- **film-grain**: 6 scenes (crisis/historical moments)
- **none**: 6 scenes (map-only scenes)

## Timing Concern
785s vs 750s target — 4.7% over. Acceptable within tolerance. TTS actual output may compress slightly at 1.15x speed.
