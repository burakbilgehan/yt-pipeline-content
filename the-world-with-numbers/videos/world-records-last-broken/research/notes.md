# Research notes: The Last Time Every World Record Was Broken

Researched 27 Sep 2026. All ages are calendar-year differences against 2026 (claim `year-now`). Every number below has a claim id in `claims.json`; ids are given in brackets.

## What changed since the brief was written

The brief's memory numbers are stale in four places, and one of them changes the shape of the video.

1. The men's marathon record is no longer Kiptum's 2:00:35 (2023). Sabastian Sawe ran 1:59:30 in London on 26 Apr 2026, the first sub-two-hour time in a record-eligible race, ratified by World Athletics on 23 Jul 2026 [mmar-mark, mmar-year, mmar-sawe-gain]. An exhibition run in Vienna in 2019 had already dipped under two hours but was not record-eligible; its time is not a claim (World Athletics and the event organiser round it differently), so the script mentions the run without a number. The century-of-improvement beat now runs 1908 to 2026.
2. Duplantis has moved the pole vault record from 6.25 (Paris, Aug 2024) through 6.27, 6.28, 6.29, 6.30 (Tokyo Worlds, 15 Sep 2025) to 6.31 in Uppsala on 12 Mar 2026, indoors, ratified 23 Jul 2026 [mpv-mark, mpv-tokyo-2025-mark, mpv-paris-2024-mark, mpv-gain-2024-2026]. World Athletics treats indoor and outdoor field-event marks as one record list, so 6.31i is the world record.
3. Two more long-standing men's records fell in 2026: the 110 m hurdles (Merritt 12.80 of 2012 to Tharp 12.75, Eugene, 10 Jun 2026, ratified 3 Sep 2026) [m110h-mark, m110h-age-when-broken] and the 1000 m (Ngeny 2:11.96 of 1999 to Wanyonyi 2:11.83, Monaco, 10 Jul 2026) [m1000-mark, m1000-age-when-broken]. The 1000 m is not an Olympic event and is outside the 40-event timeline set, but it is a good example of a 27-year record falling.
4. Three marks are pending ratification as of 27 Sep 2026 and must not be mixed into the timeline: Josh Kerr's mile 3:42.66 (London, 18 Jul 2026; El Guerrouj's 3:43.13 of 1999 is still the ratified record) [pending-mmile-mark, mmile-mark], Alison dos Santos's 400 m hurdles 45.80 (Zurich, 27 Aug 2026; Warholm 45.94 of 2021 stands) [pending-m400h-mark, m400h-mark], Masai Russell's 100 m hurdles 12.09 (Zurich, 27 Aug 2026; Amusan 12.12 of 2022 stands) [pending-w100h-mark, w100h-mark], plus Kejelcha's half marathon 56:51 (Buenos Aires, 23 Aug 2026) [pending-mhalf-mark]. The 3 Sep 2026 World Athletics release explicitly lists Kejelcha's run as "subject to the usual ratification procedure"; the Zurich report and Kerr report carry the same asterisk. If either hurdles mark is ratified before the script is locked, the 2021 and 2022 entries on the timeline move to 2026 and the "since 2020" count stays 17 but "since 2023" rises to 14.

## The timeline set: 40 records

Choice made here: the timeline uses the 40 individual events of the Olympic programme (20 men, 20 women): 100, 200, 400, 800, 1500, 5000, 10,000 m, marathon, sprint hurdles, 400 m hurdles, 3000 m steeplechase, high jump, pole vault, long jump, triple jump, shot, discus, hammer, javelin, and the decathlon or heptathlon [events-men, events-women, events-total]. Relays (team marks) and race walks (judged events) are excluded because they dilute the "one body, one event" reading; 1000 m, mile, 2000 m, 3000 m, road 5 km, 10 km and half marathon are excluded as non-Olympic. The women's marathon uses the mixed-race record (2:09:56), which is what World Athletics calls "the" world record; the women-only record (Assefa 2:15:41, London 2026) is listed separately [wmar-wo-mark, wmar-wo-prev-mark]. Two records were set indoors and count as absolute world records under World Athletics rules: men's pole vault 6.31 (2026) and women's triple jump 15.74 (Rojas, Belgrade, 20 Mar 2022) [wtj-mark].

The full list (event, mark, holder, nationality, date) is in claims `m100` through `mdec` and `w100` through `whep`, one `-mark` and one `-year` claim per event.

## The shape of the timeline

Sorted by year, the 40 records fall into three blocks.

Before 1990: 9 records (22.5%) [records-pre-1990, share-pre-1990]. Eight of them are women's records (40% of the women's set) [records-pre-1990-women, share-pre-1990-women]; the only men's survivor from that decade is Sedykh's hammer 86.74 from Stuttgart, 30 Aug 1986, now 40 years old [mht-mark, mht-age, records-pre-1990-men]. The women's block: 800 m (Kratochvilova 1:53.28, Munich, 26 Jul 1983), 400 m (Koch 47.60, 1985), shot (Lisovskaya 22.63, 1987), and five from 1988: 100 m and 200 m (Griffith Joyner 10.49 and 21.34), long jump (Chistyakova 7.52), discus (Reinsch 76.80), heptathlon (Joyner-Kersee 7291). Show as dates; the brief rules out commentary.

1990 to 2019: 14 records (35%) [records-1990-2019, share-1990-2019]. Ten of them are men's: Powell 1991, Sotomayor 1993, Edwards 1995, Zelezny 1996, El Guerrouj 1998, Bolt 2009 twice, Rudisha 2012, van Niekerk 2016, Mayer 2018. Four women's: Spotakova 2008, Isinbayeva 2009, Wlodarczyk 2016, Chepkoech 2018.

2020 or later: 17 records (42.5%) [records-since-2020, share-since-2020]; 12 of them since 2023 (30%) [records-since-2023, share-since-2023]. Nine men's (both Cheptegei distances 2020, Warholm 2021, Girma and Crouser 2023, Alekna 2025, Sawe, Tharp and Duplantis 2026) and eight women's (Amusan and Rojas 2022, Chebet 10,000 m, Chepngetich, McLaughlin-Levrone and Mahuchikh 2024, Kipyegon and Chebet 5000 m 2025).

The median record year is 2016 (the 20th and 21st sorted values are both 2016: men's 400 m and women's hammer), so the median standing record is 10 years old [median-year, median-age]. Half the records are older than a current U20 athlete's career; the other half are younger than the last Olympic cycle.

Cutoff choice: the video should say "2020 or later" and tie it to the World Athletics shoe rule of 31 Jan 2020 [shoe-rule-year], because that is a federation date with a quotable text (40 mm sole, one plate, four months on retail sale from 30 Apr 2020) [shoe-rule-sole-mm, shoe-rule-plates, shoe-rule-retail-months]. The alternative cutoff, the first carbon-plate racing shoe on general sale (Nike Zoom Vaporfly 4%, 20 Jul 2017) [vaporfly-retail-year], is sourced only from a sneaker-news article because Nike's own release page has been taken down; the counts barely change (2017 or later adds Mayer 2018 and Chepkoech 2018: 19 of 40). No record in the set was set in 2019, so "2019 or later" and "2020 or later" give the same 17.

## The oldest record

The women's 800 m, 1:53.28 by Jarmila Kratochvilova in Munich on 26 Jul 1983, is 43 years old [w800-mark, w800-year, w800-age]. World Athletics itself has called it "the oldest official IAAF World record" since 4 Jun 2011 [w800-oldest-since-year]. Oldest men's record: Sedykh's hammer, 1986, 40 years [mht-age]. The women's 100 m (10.49, 1988) is 38 years old [w100-age].

## Old records that fell in 2024 to 2026

Women's high jump: Kostadinova's 2.09 (Rome, 30 Aug 1987) fell to Mahuchikh's 2.10 in Paris on 7 Jul 2024, ratified 24 Oct 2024; 37 calendar years, by one centimetre [whj-prev-mark, whj-prev-year, whj-mark, whj-age-when-broken, whj-gain].

Men's discus: Schult's 74.08 (Neubrandenburg, 6 Jun 1986) fell to Alekna's 74.35 in Ramona on 14 Apr 2024 (ratified 27 Jul 2024), 38 calendar years; Alekna then threw 74.89 and 75.56 on the same Ramona ring on 13 Apr 2025 (ratified 10 Sep 2025) [mdt-prev-mark, mdt-2024-mark, mdt-age-when-broken, mdt-mark, mdt-gain-since-1986]. Ramona, Oklahoma is a purpose-built throwing venue known for strong, favourable wind; World Athletics has ratified all three marks and says nothing about wind, so the video may name the venue but not the cause.

Men's 1000 m: 27 years (1999 to 2026) [m1000-age-when-broken]. Men's 110 m hurdles: 14 years (2012 to 2026) [m110h-age-when-broken]. Men's marathon: Kiptum's 2023 record lasted under three years [mmar-kiptum-year, mmar-year].

Caveat on ages: "37 years" for the high jump is a calendar-year difference (2024 minus 1987); the exact interval was 36 years 10 months. Same for the discus (37 years 10 months, stated as 38). Script wording should be "set in 1987, broken in 2024" or "in its 37th year", not "exactly 37 years".

## The current wave, with ratification status

- Men's marathon 1:59:30, Sawe, London, 26 Apr 2026, ratified 23 Jul 2026 [mmar-mark]. Previous: Kiptum 2:00:35, Chicago, 8 Oct 2023, ratified 6 Feb 2024 [mmar-kiptum-mark]; before that Kipchoge 2:01:09, Berlin, 25 Sep 2022 [mmar-kipchoge-2022-mark]. World Athletics refers to "the late Kelvin Kiptum"; he died in February 2024. Not needed for the video.
- Women's marathon 2:09:56, Chepngetich, Chicago, 13 Oct 2024, ratified 11 Dec 2024, a 117-second cut from Assefa's 2:11:53 (Berlin 2023) [wmar-mark, wmar-prev-mark, wmar-gain-2024]. Status: the holder tested positive for hydrochlorothiazide in a sample of 14 Mar 2025 (estimated 3800 ng/mL), accepted the violation, and was banned for three years by the Athletics Integrity Unit in October 2025 [wmar-holder-ban-years, wmar-holder-sample-concentration, wmar-holder-sample-year]. Results from the sample date onward are disqualified; the Chicago 2024 record predates it and remains ratified. Wikipedia's list still shows it as the record as of 27 Sep 2026. Source quality: the AIU decision PDF (AIU 25-059) is the primary document but is a secured PDF I could not read; the ban, concentration and "record stands" statements are quoted from Athletics Weekly and CITIUS Mag reporting the AIU statement. One discrepancy: Athletics Weekly writes that results "since March 24, 2025" are disqualified, CITIUS Mag and CNN say from 14 March. Either way the record is unaffected. The verifier should try the AIU PDF.
- Women-only marathon 2:15:41, Assefa, London, 26 Apr 2026, ratified 23 Jul 2026; previous 2:15:50, same race, 27 Apr 2025 [wmar-wo-mark, wmar-wo-prev-mark].
- Women's 5000 m 13:58.06, Chebet, Eugene, 5 Jul 2025, ratified 10 Sep 2025; previous Tsegay 14:00.21 (2023) [w5000-mark, w5000-prev-mark].
- Women's 10,000 m 28:54.14, Chebet, Eugene, 25 May 2024, ratified 11 Dec 2024; previous Gidey 29:01.03 (2021) [w10000-mark, w10000-prev-mark].
- Women's 1500 m 3:48.68, Kipyegon, Eugene, 5 Jul 2025, ratified 13 Sep 2025; previous her own 3:49.04, Paris, 7 Jul 2024 [w1500-mark, w1500-prev-mark].
- Women's 400 m hurdles 50.37, McLaughlin-Levrone, Paris, 8 Aug 2024, ratified 11 Dec 2024 [w400h-mark].
- Pole vault: see above.

## A century of improvement in two flagship events

Men's 100 m: 10.6 (Lippincott, Stockholm, 6 Jul 1912, the first IAAF-ratified mark) to 9.58 (Bolt, Berlin, 16 Aug 2009) is a 9.6% improvement over 97 years, about 0.10% per year [m100-first-mark, m100-mark, m100-pct-1912-2009, m100-span-1912-2009, m100-rate-1912-2009]. Split at Hines's 9.95 (Mexico City, 1968, the first fully automatic sub-10): 1912 to 1968 ran at 0.11% per year, 1968 to 2009 at 0.09% per year [m100-rate-1912-1968, m100-rate-1968-2009]. The record has now stood 17 years, the longest gap in its history [m100-age]. The slowdown in the 100 m is mild; the honest reading is "still creeping, then stopped in 2009".

Men's marathon: 2:55:18.4 (Hayes, London Olympics, 24 Jul 1908) to 1:59:30 (2026) is a 31.8% improvement over 118 years, 0.27% per year [mmar-first-mark, mmar-pct-1908-2026, mmar-rate-1908-2026]. Split at Clayton's 2:09:36.4 (Fukuoka, 3 Dec 1967), exactly 59 years each side: 0.44% per year to 1967, 0.13% per year since [mmar-rate-1908-1967, mmar-rate-1967-2026]. That contrast (three times slower in the second half, yet the second half contains the sub-two) is the clearest single chart for the "slowdown but no wall" argument.

Caveat: the IAAF only ratified marathon world records from 1 Jan 2004 (world bests from 2003); earlier marks are "world bests" from the IAAF statistics handbook progression. Say "fastest time" or "world best" for 1908 and 1967, "record" from 2004. Also, 1908 and 1967 courses were not measured to today's standard; the progression is the IAAF's own list, so the caveat is about wording, not about the numbers.

Per-decade rates were not computed because the claim schema has no constant-divisor operation; the per-year rates above are exact derivations and the script can say "roughly one percent per decade" only if it adds a derived claim for it.

## Contested and annulled marks in the standing set

- Women's 100 m 10.49 (1988): wind gauge read 0.0; the triple jump anemometer about 10 m away read 4.3 m/s at the same time. The IAAF ratified the mark and has never annulled it [w100-mark, w100-tj-anemometer]. The 1995 report often cited as "IAAF-commissioned" could not be found on a World Athletics page; the anemometer fact is quoted from Wikipedia's progression page (secondary). State it as "statisticians dispute the wind reading; the federation lists the record".
- Women's marathon 2:09:56: holder banned in 2025 for a 2025 sample; record stands (above).
- No other record in the 40-event set carries a sanction or annulment on the World Athletics list. Annulled marks that would otherwise be relevant are outside the set (e.g. Kipruto's 26:24 road 10 km, disqualified; Kejelcha's 26:31 ratified in its place on 1 Jun 2026).
- Javelin: both records are on the current implements (men's 1986 redesign, women's 1999 redesign); Zelezny's 98.48 (1996) and Spotakova's 72.28 (2008) are the records for the current specification, which is what World Athletics lists [mjt-mark, wjt-mark].

## The 2008 prediction (closing beat)

Berthelot G, Thibault V, Tafflet M, Escolano S, El Helou N, Jouven X, Hermine O, Toussaint J-F (2008), "The Citius End: World Records Progression Announces the Completion of a Brief Ultra-Physiological Quest", PLoS ONE 3(2): e1552, published 6 Feb 2008 [citius-publication-year]. Abstract sentence, verbatim including the French decimal comma: "Starting at 75% of their estimated asymptotic values in 1896, WR have now reached 99%, and, present conditions prevailing, half of all WR will not be improved by more than 0,05% in 2027." [citius-forecast-year, citius-forecast-threshold, citius-start-share-1896, citius-share-2008]. Main text: "By 2027, half of the records will reach 99.95% of their asymptotic value, within a [2002–2120] credibility interval." [citius-asymptote-share-2027]. Data: 3263 world records in 147 measurable Olympic events across five disciplines, 1896 to 2007 [citius-records-analysed, citius-events-analysed]. Note the paper covers five Olympic sports (athletics, swimming, cycling, weightlifting, speed skating), not athletics alone, and predicts "half of all WR", not a stop.

How close we are in 2026: the forecast date is one year away [citius-years-to-forecast]; the paper is 18 years old [citius-years-since-paper]. The data in this file are consistent with "half frozen, half moving": 20 of the 40 records are 10 or more years old, 17 were set in the last seven seasons. Do not go further; the late-2027 video settles it.

## Angles the numbers support

1. "The frozen clock" as briefed: three blocks (1980s, quiet middle, 2020s), the 1980s block almost entirely women's records, the 2020s block dominated by running and the pole vault, with the throws split (men's discus moved, hammer and all women's throws frozen).
2. "Two halves of the marathon": 59 years each, 0.44% per year then 0.13% per year, and still the sub-two arrived. Best single chart for "slowing is not stopping".
3. "One centimetre, 37 years": the high jump and discus beats show how thin the margins are when an old record finally falls (0.01 m and 0.27 m).
4. "Pending" as a live element: on the day of writing three ratified records from 1999, 2021 and 2022 are under threat from marks awaiting ratification.

## Open questions

- Ratification of dos Santos 45.80, Russell 12.09 and Kerr 3:42.66 may land before publishing; re-check the World Athletics press releases (search "Ratified: world records") and update the affected `-mark`/`-year` claims and the two tallies.
- The AIU decision PDF should be read by the verifier for the exact disqualification start date (14 or 24 March 2025).
- `year-now` is sourced from a press-release date stamp; if the verifier objects, any dated World Athletics page from 2026 will do.

## Source notes

The World Athletics records pages (worldathletics.org/records/by-category/world-records and the per-discipline pages) are rendered client-side and return no table text to a fetch, so they could not be quoted. For records set before 2024 the row data are quoted from Wikipedia's "List of world records in athletics" (which cites World Athletics for each row) and the per-event progression pages; quotes are the table cells joined with " | " in the order mark, wind, athlete, nation, date, venue. Every record set in 2024 or later, and the previous records they replaced, is quoted from a World Athletics ratification press release or competition report. Counts (events, records before 1990, since 2020, since 2023, median year) are my tallies of the date cells and carry the tallied cells as their quote; the verifier should recount them against the list.

## Sources

1. World Athletics, "Ratified: world records for Sawe, Ehammer, Charlton and more", 23 Jul 2026. https://worldathletics.org/news/press-releases/ratified-world-records-sawe-ehammer-charlton-mcrae-yan-duplantis-assefa
2. World Athletics, "Ratified: world records for Kiplimo, Tharp and Wanyonyi", 3 Sep 2026. https://worldathletics.org/news/press-releases/ratified-world-records-kiplimo-tharp-wanyonyi
3. World Athletics, "Ratified: world records for Hoey, Kejelcha and Yamanishi", 1 Jun 2026. https://worldathletics.org/news/press-releases/ratified-world-records-hoey-kejelcha-yamanishi
4. World Athletics, "Sawe breaks two-hour barrier with 1:59:30 world record at London Marathon", 26 Apr 2026. https://worldathletics.org/news/report/sawe-two-hour-assefa-world-record-london-marathon
5. World Athletics, "Ratified: world records for Alekna, Chebet and Duplantis", 10 Sep 2025. https://worldathletics.org/news/press-releases/ratified-world-records-alekna-chebet-duplantis
6. World Athletics, "Ratified: world records for Duplantis, Troscianka, Yan and Zhang", 22 Oct 2025. https://worldathletics.org/news/press-releases/ratified-world-records-duplantis-troscianka-yan-zhang
7. World Athletics, "Ratified: Kipyegon's world 1500m record in Eugene", 13 Sep 2025. https://worldathletics.org/news/press-releases/ratified-faith-kipyegon-world-1500m-record-eugene
8. World Athletics, "Ratified: world records for Assefa, Stano and Dunfee", 4 Jul 2025. https://worldathletics.org/news/press-releases/ratified-world-records-assefa-stano-dunfee
9. World Athletics, "Ratified: world records for Chebet, Duplantis, Ingebrigtsen and Yamanishi", 18 Apr 2025. https://worldathletics.org/news/press-releases/ratified-world-records-chebet-duplantis-ingebrigtsen-yamanishi
10. World Athletics, "Ratified: world records for Duplantis, Ngetich, Wanyonyi and Myers", 29 Aug 2025. https://worldathletics.org/news/press-releases/world-records-ratified-duplantis-wanyonyi-ngetich-myers
11. World Athletics, "Ratified: world records for Chebet, Duplantis, McLaughlin-Levrone, Chepngetich and Kawano", 11 Dec 2024. https://worldathletics.org/news/press-releases/ratified-world-records-chebet-duplantis-mclaughlin-levrone-chepngetich-kawano
12. World Athletics, "Ratified: Mahuchikh's world high jump record", 24 Oct 2024. https://worldathletics.org/news/press-releases/ratified-world-records-mahuchikh-eisa-hibbert-yan
13. World Athletics, "Ratified: world records for McLaughlin-Levrone, Duplantis, Kipyegon, Chebet, Alekna and Ngetich", 27 Jul 2024. https://worldathletics.org/news/press-releases/ratified-world-records-mclaughlin-levrone-duplantis-kipyegon-chebet-alekna-ngetich
14. World Athletics, "Ratified: Kiptum's world marathon record", 6 Feb 2024. https://worldathletics.org/news/press-releases/ratified-world-marathon-record-kelvin-kiptum
15. World Athletics, "Mahuchikh and Kipyegon break world records in Paris", 7 Jul 2024. https://worldathletics.org/competitions/diamond-league/news/meeting-de-paris-diamond-league-2024-world-record
16. World Athletics, "Dos Santos and Russell break world records in unforgettable Zurich", 27 Aug 2026. https://worldathletics.org/news/report/zurich-weltklasse-dos-santos-world-400m-hurdles-record
17. World Athletics, "Kerr breaks world mile record with 3:42.66 in London", 18 Jul 2026. https://worldathletics.org/news/report/london-athletics-meet-2026-josh-kerr-world-mile-record
18. World Athletics, "30 years on" (Kratochvilova), 26 Jul 2013. https://worldathletics.org/news/news/30-years-on-jarmila-kratochvilovas-800m-wor
19. World Athletics, "100 years of the 100 metres World record - IAAF Centenary", 6 Jul 2012. https://worldathletics.org/news/press-release/100-years-of-the-100-metres-world-record-ia
20. World Athletics, "Bolt again! 9.58 World record in Berlin! - UPDATED", 16 Aug 2009. https://worldathletics.org/news/news/bolt-again-958-world-record-in-berlin-updat
21. World Athletics, "World Athletics modifies rules governing competition shoes for elite athletes", 31 Jan 2020. https://worldathletics.org/news/press-releases/modified-rules-shoes
22. Berthelot et al., "The Citius End", PLoS ONE 3(2): e1552, 6 Feb 2008. https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0001552
23. Wikipedia, "List of world records in athletics" (men's and women's tables, cites World Athletics per row), read 27 Sep 2026. https://en.wikipedia.org/wiki/List_of_world_records_in_athletics
24. Wikipedia, "Men's 100 metres world record progression". https://en.wikipedia.org/wiki/Men%27s_100_metres_world_record_progression
25. Wikipedia, "Women's 100 metres world record progression". https://en.wikipedia.org/wiki/Women%27s_100_metres_world_record_progression
26. Wikipedia, "Marathon world record progression". https://en.wikipedia.org/wiki/Marathon_world_record_progression
27. Wikipedia, "Women's high jump world record progression". https://en.wikipedia.org/wiki/Women%27s_high_jump_world_record_progression
28. Wikipedia, "Men's discus throw world record progression". https://en.wikipedia.org/wiki/Men%27s_discus_throw_world_record_progression
29. Wikipedia, "Men's hammer throw world record progression". https://en.wikipedia.org/wiki/Men%27s_hammer_throw_world_record_progression
30. Wikipedia, "2026 in the sport of athletics" (list of 2026 records and pending marks). https://en.wikipedia.org/wiki/2026_in_the_sport_of_athletics
31. Athletics Integrity Unit, decision AIU 25-059 Ruth Chepngetich (secured PDF, not readable by fetch). https://www.athleticsintegrity.org/downloads/pdfs/disciplinary-process/en/AIU-25-059-Ruth-CHEPNGETICH-Decision_FINAL_secured.pdf
32. Athletics Weekly, "Ruth Chepngetich banned for three years for doping", 23 Oct 2025. https://athleticsweekly.com/news/ruth-chepngetich-banned-for-three-years-for-doping-1040008418/
33. CITIUS Mag, "Marathon World Record Holder Ruth Chepngetich Banned Three Years...", 23 Oct 2025. https://citiusmag.com/articles/ruth-chepngetich-banned-three-years-doping-athletics-integrity-unit-admission
34. Complex, "Nike's First ZoomX Sneaker Releases on July 20", 18 Jul 2017. https://www.complex.com/sneakers/a/brendan-dunne/nike-zoomx-vaporfly-4-percent-release-date
