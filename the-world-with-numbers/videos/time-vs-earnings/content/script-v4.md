# Script: Time vs Earnings
> version: script-v4
> based_on: research-v2, research-v3
> changes_from_prev: Complete structural rewrite based on 19-point user feedback. New 10-section structure: Hook (curiosity-first, no data assault) → Raw salary rankings (setup) → PPP explanation (rug-pull) → Quadrant introduction → 4 quadrant explorations (outlier-focused, camera stays on chart) → Ugly Truth (6 non-OECD countries) → Closing (birth lottery punchline). Added raw nominal salary section before PPP. Added "Ugly Truth" segment with non-OECD data (India, Bangladesh, Cambodia, Pakistan, Nigeria, Philippines). Reduced country listing — focus on outliers and stories. Quadrant camera never leaves the scatter plot once introduced. SSML mode (was markup). Voice changed to Sulafat. Speed 1.05.
> date: 2026-03-22

## Metadata
- **Word count:** ~1,499 spoken words (voiceover only, SSML stripped)
- **Word budget:** ~1,596-1,729 words (target 12:00-13:00, 136.6 WPM calibrated)
- **Estimated duration:** ~12:14 total (659s speech + 75.5s SSML pauses)
- **Tone:** Neutral-analytic, authoritative, curiosity-driven — numbers speak for themselves
- **Target audience:** 18-35, globally curious, English-speaking, prefers facts over opinions
- **TTS engine:** Google Cloud TTS — Chirp 3: HD, voice: Sulafat, input mode: SSML, speed: 1.05

---

## Hook (0:00–0:35)

[VISUAL NOTE] Dark screen. A single clock icon ticks. Then a question fades in as white text: "What is one hour of your life worth?" Hold for 2 seconds. The text dissolves. A world map silhouette appears — dots light up across countries, each a different size. No labels yet. The dots pulse gently.

[VOICEOVER]
<speak>
<p>
<s>What is one hour of your life worth?</s>
<break time="1200ms"/>
<s>The answer depends almost entirely on one thing.</s>
<break time="600ms"/>
<s>Where you were born.</s>
<break time="1500ms"/>
<s>In some countries, an hour of work buys a full meal for a family.</s>
<s>In others, it barely covers a cup of coffee.</s>
<break time="800ms"/>
<s>And the countries where people work the longest hours... are almost never the ones where people earn the most.</s>
<break time="1200ms"/>
<s>Here's what the data actually shows.</s>
</p>
</speak>

---

## Section: Raw Salary Rankings (0:35–1:35)

[VISUAL NOTE] A horizontal bar chart builds on screen. Title: "Average Annual Salary (Nominal USD)." Bars appear one by one from the top: Switzerland ($106K nominal — placeholder visual, exact nominal not used in voiceover), Luxembourg, Iceland, USA, etc. About 10 countries shown. The USA bar is highlighted. The chart looks straightforward — rich countries at the top, poorer at the bottom. This is the "obvious" ranking the viewer thinks they understand.

[VOICEOVER]
<speak>
<p>
<s>Start with the obvious.</s>
<break time="600ms"/>
<s>Average annual salary, in raw US dollars.</s>
<break time="400ms"/>
<s>Switzerland near the top.</s>
<s>Luxembourg.</s>
<s>Iceland.</s>
<s>The United States.</s>
<break time="600ms"/>
<s>Down the list: Germany, Canada, Australia, the United Kingdom.</s>
<s>Further down: Spain, Portugal, Poland.</s>
<s>At the bottom: Greece, Hungary, Mexico.</s>
<break time="800ms"/>
<s>This is the ranking most people picture when they think about global salaries.</s>
<s>Rich countries earn more, poorer countries earn less.</s>
<break time="600ms"/>
<s>Simple.</s>
<s>Intuitive.</s>
<break time="1000ms"/>
<s>And misleading.</s>
<break time="600ms"/>
<s>Because a dollar in Zurich does not buy what a dollar buys in Warsaw.</s>
<s>Or in Mexico City.</s>
<s>Or in Tokyo.</s>
<break time="800ms"/>
<s>To compare salaries honestly, you have to account for what that money actually buys.</s>
</p>
</speak>

---

## Section: Purchasing Power Parity (1:35–3:15)

[VISUAL NOTE] Split screen animation: an identical grocery basket appears in two cities — Zurich (left) and Mexico City (right). Same items: bread, milk, eggs, rice, chicken. Price tags float above each item — Zurich prices are 3-4× higher. The total at the bottom shows the gap. Then a title card: "Purchasing Power Parity (PPP)." The OECD logo appears with text: "~3,000 goods & services tracked." Then the bar chart from the previous section re-sorts with PPP-adjusted values. Some countries jump up, others slide down. USA moves to 4th. Luxembourg takes #1.

[VOICEOVER]
<speak>
<p>
<s>Three thousand dollars a month.</s>
<break time="400ms"/>
<s>In parts of Mexico, that covers rent, food, and transport — with room to spare.</s>
<s>In Zurich, it barely covers a studio apartment.</s>
<break time="800ms"/>
<s>Same number.</s>
<s>Completely different lives.</s>
</p>
<break time="1000ms"/>
<p>
<s>So economists use something called Purchasing Power Parity — or PPP.</s>
<break time="600ms"/>
<s>The OECD tracks prices of roughly three thousand goods and services in each country — bread, rice, electricity, rent, haircuts, public transport — and calculates a conversion factor for every currency.</s>
<break time="600ms"/>
<s>That conversion factor adjusts each country's wages so they reflect actual buying power, not just a raw dollar amount.</s>
<break time="600ms"/>
<s>When the OECD says a Swiss worker earns eighty-seven thousand PPP dollars, it means that salary buys the same amount of stuff as eighty-seven thousand dollars would in the United States.</s>
<break time="400ms"/>
<s>Apples to apples.</s>
</p>
<break time="800ms"/>
<p>
<s>After this adjustment, the rankings shift.</s>
<break time="600ms"/>
<s>Luxembourg takes the top spot — ninety-four thousand four hundred forty-seven dollars.</s>
<s>Iceland second at almost ninety thousand.</s>
<s>Switzerland third at eighty-seven thousand four hundred sixty-eight.</s>
<s>The United States fourth at eighty-two thousand nine hundred thirty-three.</s>
<break time="800ms"/>
<s>At the bottom of thirty-four OECD countries: Greece at thirty-two thousand two hundred fifty-seven.</s>
<break time="400ms"/>
<s>And Mexico at twenty thousand four hundred thirty-three.</s>
<break time="1200ms"/>
<s>Now you know what people actually earn — in real purchasing power.</s>
<break time="600ms"/>
<s>But that's only half the picture.</s>
</p>
</speak>

---

## Section: Introducing the Quadrant (3:15–4:15)

[VISUAL NOTE] The PPP bar chart tilts and transforms. The salary axis becomes the Y-axis of a scatter plot. A new X-axis extends: "Annual Hours Worked." A crosshair fades in at the origin point: $59,200 (Y) and 1,633 hours (X). Label: "34-country average." Four quadrant labels appear one by one with subtle color fills: DREAM (top-left, green), GRIND (top-right, amber), CHILL (bottom-left, blue), TRAP (bottom-right, red). Then ALL 34 country dots animate in simultaneously — no labels yet. Just dots scattered across the four quadrants.

[VOICEOVER]
<speak>
<p>
<s>How many hours do people work for that salary?</s>
<break time="800ms"/>
<s>Because sixty-nine thousand dollars means one thing if you work one thousand three hundred forty hours a year.</s>
<break time="400ms"/>
<s>That's Germany.</s>
<break time="400ms"/>
<s>It means something very different at two thousand two hundred twenty-six hours.</s>
<break time="400ms"/>
<s>That's Mexico.</s>
</p>
<break time="600ms"/>
<p>
<s>Plot salary on one axis, hours on the other.</s>
<break time="400ms"/>
<s>The crosshair sits at the thirty-four-country average: fifty-nine thousand two hundred dollars and one thousand six hundred thirty-three hours.</s>
<break time="800ms"/>
<s>Four quadrants.</s>
<break time="600ms"/>
<s>Top left — high pay, low hours.</s>
<s>We call it the DREAM.</s>
<break time="400ms"/>
<s>Top right — high pay, high hours.</s>
<s>The GRIND.</s>
<break time="400ms"/>
<s>Bottom left — low pay, low hours.</s>
<s>The CHILL.</s>
<break time="400ms"/>
<s>Bottom right — low pay, high hours.</s>
<s>The TRAP.</s>
<break time="1200ms"/>
<s>Thirty-four countries.</s>
<s>Four stories.</s>
</p>
</speak>

---

## Section: The Dream Quadrant (4:15–5:45)

[VISUAL NOTE] Camera stays on the full quadrant chart. The DREAM quadrant (top-left) gets a subtle green glow. Country labels appear on the 13 dots in this quadrant. Luxembourg pulses at the top. Germany pulses at the far left (fewest hours). A tooltip appears near Germany's dot: "$69,433 | 1,340 hrs | $51.82/hr." Then Luxembourg's tooltip: "$94,447 | 1,473 hrs | $64.12/hr." A small annotation: "13 of 34 countries." The other quadrants remain visible but slightly dimmed.

[VOICEOVER]
<speak>
<p>
<s>Thirteen countries land in the DREAM quadrant.</s>
<break time="400ms"/>
<s>Above-average salary, below-average hours.</s>
<break time="800ms"/>
<s>Luxembourg sits at the very top — ninety-four thousand four hundred forty-seven dollars on one thousand four hundred seventy-three hours.</s>
<s>That's sixty-four dollars and twelve cents per hour — the highest in the dataset.</s>
</p>
<break time="600ms"/>
<p>
<s>But the most notable position belongs to Germany.</s>
<break time="600ms"/>
<s>Germany works the fewest hours of any country in the dataset — one thousand three hundred forty per year.</s>
<s>Its salary of roughly sixty-nine and a half thousand dollars translates to fifty-one dollars and eighty-two cents per hour.</s>
<break time="600ms"/>
<s>Denmark sits close by — one thousand three hundred seventy-one hours, fifty-three ninety-nine per hour.</s>
<s>The second-fewest hours and the fourth-highest hourly rate in the dataset.</s>
<break time="800ms"/>
<s>The rest of this quadrant reads like a map of Western and Northern Europe.</s>
<break time="400ms"/>
<s>The Netherlands, Norway, Belgium, Austria, Switzerland, Iceland.</s>
<s>Then the UK, France, Finland, Slovenia.</s>
<break time="1000ms"/>
<s>Not a single country outside Europe appears here.</s>
</p>
</speak>

---

## Section: The Grind Quadrant (5:45–7:15)

[VISUAL NOTE] Camera stays on full quadrant. GRIND quadrant (top-right) gets amber glow. Five dots labeled: USA, AUS, CAN, NZL, IRL. Country flags appear next to each dot. A text overlay: "5 countries. All English-speaking." A connector line draws from USA's dot to Denmark's dot (in DREAM). Stats along the line: "439 hours apart | DNK earns 18% more per hour." USA tooltip: "$82,933 | 1,810 hrs | $45.82/hr." Denmark tooltip: "$74,022 | 1,371 hrs | $53.99/hr."

[VOICEOVER]
<speak>
<p>
<s>Five countries in the GRIND.</s>
<break time="400ms"/>
<s>Above-average salary, above-average hours.</s>
<break time="800ms"/>
<s>The United States.</s>
<s>Australia.</s>
<s>Canada.</s>
<s>New Zealand.</s>
<s>Ireland.</s>
<break time="600ms"/>
<s>Every single one is English-speaking.</s>
<break time="400ms"/>
<s>The entire Anglosphere — and no one else.</s>
</p>
<break time="1000ms"/>
<p>
<s>The United States earns the highest total salary in this quadrant — eighty-two thousand nine hundred thirty-three dollars.</s>
<s>But at one thousand eight hundred ten hours per year.</s>
<break time="600ms"/>
<s>Compare that to Denmark, in the DREAM quadrant.</s>
<break time="400ms"/>
<s>Denmark earns about eleven percent less in total salary.</s>
<s>But nearly eighteen percent more per hour — fifty-three ninety-nine versus forty-five eighty-two.</s>
<break time="800ms"/>
<s>The difference is four hundred thirty-nine hours.</s>
<break time="400ms"/>
<s>Fifty-five eight-hour workdays.</s>
<break time="600ms"/>
<s>Nearly eleven extra work weeks per year — for about eleven percent more pay.</s>
</p>
<break time="800ms"/>
<p>
<s>Australia and Canada sit in the middle of this quadrant — both around forty-one dollars per hour.</s>
<break time="400ms"/>
<s>Nearly the same hourly rate as Sweden, which sits in the CHILL quadrant on far fewer hours.</s>
</p>
</speak>

---

## Section: The Trap Quadrant (7:15–9:00)

[VISUAL NOTE] Camera stays on full quadrant. TRAP quadrant (bottom-right) gets red glow. Eleven dots labeled. Germany's dot (in DREAM) and Greece's dot (in TRAP) both pulse. A connector line draws diagonally across the chart between them — it spans nearly the entire plot. Stats on the line: "3× more per hour | 546 fewer hours." Then the connector fades and Korea's dot and Italy's dot pulse side by side — nearly same Y position, different X. Tooltip: Korea "$50,947 | 1,901 hrs" vs Italy "$51,019 | 1,694 hrs." Text: "207 extra hours. $72 difference." Mexico's dot pulses at the far extreme corner.

[VOICEOVER]
<speak>
<p>
<s>Eleven countries in the TRAP.</s>
<break time="400ms"/>
<s>Below-average salary, above-average hours.</s>
<break time="800ms"/>
<s>This is where the gaps are widest.</s>
</p>
<break time="600ms"/>
<p>
<s>Draw a line from Greece to Germany.</s>
<break time="600ms"/>
<s>Both are in the European Union.</s>
<break time="400ms"/>
<s>A German worker earns roughly three times as much per hour — fifty-one eighty-two versus seventeen ten — while working five hundred forty-six fewer hours per year.</s>
<break time="1200ms"/>
<s>Same economic bloc.</s>
<s>Same currency.</s>
<s>Completely different quadrants.</s>
</p>
<break time="800ms"/>
<p>
<s>South Korea and Italy tell a quieter story.</s>
<break time="400ms"/>
<s>Korea earns fifty thousand nine hundred forty-seven dollars.</s>
<s>Italy earns fifty-one thousand nineteen.</s>
<break time="400ms"/>
<s>A difference of seventy-two dollars.</s>
<break time="600ms"/>
<s>But Korea works two hundred seven more hours per year for that nearly identical paycheck.</s>
<s>Twenty-six extra workdays.</s>
<break time="400ms"/>
<s>Same salary.</s>
<s>A month more of work.</s>
</p>
<break time="800ms"/>
<p>
<s>And then there's Mexico — the far extreme.</s>
<break time="400ms"/>
<s>Two thousand two hundred twenty-six hours per year — the most in the OECD.</s>
<s>At nine dollars and eighteen cents per hour.</s>
<break time="600ms"/>
<s>Luxembourg earns seven times more per hour than Mexico, while working seven hundred fifty-three fewer hours.</s>
</p>
</speak>

---

## Section: The Chill Quadrant (9:00–9:50)

[VISUAL NOTE] Camera stays on full quadrant. CHILL quadrant (bottom-left) gets blue glow. Five dots labeled: SWE, JPN, LTU, LVA, SVK. Sweden's dot pulses very close to the horizontal salary mean line — an annotation shows it's just $142 below. Japan's dot gets a small "?" icon. Tooltip for Japan: "$49,446 | 1,607 hrs." A brief text overlay: "karoshi — death from overwork."

[VOICEOVER]
<speak>
<p>
<s>Five countries in the CHILL quadrant.</s>
<break time="400ms"/>
<s>Below-average salary, below-average hours.</s>
<break time="800ms"/>
<s>Sweden is the first thing you notice.</s>
<break time="400ms"/>
<s>At fifty-nine thousand fifty-eight dollars, it sits just one hundred forty-two dollars below the salary mean.</s>
<s>Its hourly rate — forty-one dollars — matches Australia and Canada, both in the GRIND, working hundreds of hours more.</s>
<break time="600ms"/>
<s>Sweden is CHILL by a rounding error.</s>
</p>
<break time="800ms"/>
<p>
<s>Then there's Japan.</s>
<break time="600ms"/>
<s>The country synonymous with overwork — with karoshi, a word that literally means death from overwork — logs one thousand six hundred seven hours per year.</s>
<break time="400ms"/>
<s>Below the OECD average.</s>
<break time="800ms"/>
<s>The catch: the OECD counts all workers, including part-time.</s>
<s>Japan has a large and growing part-time workforce that pulls the average down.</s>
<break time="400ms"/>
<s>Full-time Japanese workers still log extreme hours.</s>
<s>The statistic is accurate — it just measures something different than most people expect.</s>
</p>
</speak>

---

## Section: The Ugly Truth (9:50–11:50)

[VISUAL NOTE] The full quadrant is visible with all 34 OECD dots. Then the camera slowly zooms OUT — the axes extend. The X-axis stretches past 2,500 hours. The Y-axis drops below $12,000. Six new dots appear in a cluster at the far bottom-right — deep red color, different marker shape (squares instead of circles). They're labeled one by one: India, Bangladesh, Cambodia, Pakistan, Nigeria, Philippines. A small disclaimer text appears in the corner: "⚠️ Non-OECD data: World Bank GNI per capita (PPP) + ILO hours. Different methodology." Connector line from Germany to Cambodia spans the entire chart diagonally. Stats: "22.5× more per hour | 1,049 fewer hours." The OECD origin crosshair ($59,200 / 1,633 hrs) stays in place — these new dots are far below and far to the right of it.

[VOICEOVER]
<speak>
<p>
<s>Everything so far has been the OECD — thirty-four of the world's wealthier nations.</s>
<break time="600ms"/>
<s>Zoom out.</s>
<break time="1200ms"/>
<s>Six more countries.</s>
<s>India.</s>
<s>Bangladesh.</s>
<s>Cambodia.</s>
<s>Pakistan.</s>
<s>Nigeria.</s>
<s>Philippines.</s>
</p>
<break time="800ms"/>
<p>
<s>Now — these numbers come from different sources than our OECD data.</s>
<s>World Bank and ILO estimates, which measure income differently.</s>
<s>The comparison isn't perfectly apples to apples.</s>
<break time="400ms"/>
<s>But even with generous assumptions, the gap is so massive that the methodology differences don't change the story.</s>
</p>
<break time="1000ms"/>
<p>
<s>Cambodia.</s>
<break time="400ms"/>
<s>Five thousand five hundred dollars a year.</s>
<s>Two thousand three hundred eighty-nine hours.</s>
<s>Two dollars and thirty cents per hour.</s>
<break time="800ms"/>
<s>A German worker earns twenty-two and a half times more per hour — while working one thousand forty-nine fewer hours per year.</s>
</p>
<break time="600ms"/>
<p>
<s>Pakistan logs two thousand four hundred seventy-one hours — the most in the entire dataset.</s>
<s>At two dollars and eighty-three cents per hour.</s>
<break time="600ms"/>
<s>India — one point four billion people — averages three dollars and sixty-one cents per hour.</s>
<break time="800ms"/>
<s>Luxembourg earns seventeen point eight times more per hour than India, while working fewer hours.</s>
</p>
<break time="800ms"/>
<p>
<s>Bangladesh — two dollars and ninety-four cents per hour, two thousand three hundred eighty-three hours a year.</s>
<break time="400ms"/>
<s>This is the country that produces a significant share of the world's garments.</s>
<s>A German worker earns the entire Bangladeshi annual salary in about five weeks.</s>
</p>
<break time="1000ms"/>
<p>
<s>Look at the chart.</s>
<break time="400ms"/>
<s>Mexico was the worst in the OECD at nine dollars and eighteen cents per hour.</s>
<break time="400ms"/>
<s>Every one of these six countries earns less than Mexico — and five of the six earn less than half.</s>
<break time="800ms"/>
<s>The bottom of the OECD is still far above the global average.</s>
<break time="1200ms"/>
<s>That's not an opinion.</s>
<s>That's what the data shows.</s>
</p>
</speak>

---

## Section: Closing (11:50–13:00)

[VISUAL NOTE] The full chart is visible — all 40 countries (34 OECD + 6 ugly truth). Camera slowly pulls back to show the complete picture. The quadrant labels glow faintly. The massive diagonal gap between Luxembourg (top-left) and Cambodia (bottom-right) is visible. Then all dots except two fade: one in DREAM (Germany or Luxembourg), one in deep TRAP (Cambodia or Pakistan). The two remaining dots pulse gently on opposite ends of the chart. Then they fade too. The axes remain for a moment. Then the question from the hook returns as text: "What is one hour of your life worth?" Hold. Fade to black.

[VOICEOVER]
<speak>
<p>
<s>Forty countries.</s>
<s>Two axes.</s>
<s>Four quadrants.</s>
<break time="1000ms"/>
<s>A worker in Luxembourg earns sixty-four dollars and twelve cents per hour on one thousand four hundred seventy-three hours per year.</s>
<break time="400ms"/>
<s>A worker in Cambodia earns two dollars and thirty cents per hour on two thousand three hundred eighty-nine hours.</s>
<break time="1200ms"/>
<s>One earns nearly twenty-eight times more.</s>
<s>The other works nine hundred sixteen more hours.</s>
<break time="600ms"/>
<s>And both show up to work every morning.</s>
</p>
<break time="1000ms"/>
<p>
<s>Salary alone doesn't tell you who's better off.</s>
<s>Time matters.</s>
<break time="800ms"/>
<s>But even time and salary together don't explain the full picture.</s>
<break time="600ms"/>
<s>Because the single biggest predictor of which quadrant you land in... is which country you were born in.</s>
<break time="1500ms"/>
<s>Not how hard you work.</s>
<break time="600ms"/>
<s>Not how many hours you put in.</s>
<break time="1200ms"/>
<s><prosody rate="slow">Where you were born.</prosody></s>
</p>
<break time="1500ms"/>
<p>
<s>The numbers don't tell you what an hour of your life is worth.</s>
<break time="600ms"/>
<s>They just show you how differently the world answers that question.</s>
</p>
</speak>
