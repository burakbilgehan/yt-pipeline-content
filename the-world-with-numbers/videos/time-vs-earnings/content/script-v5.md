# Script: Time vs Earnings
> version: script-v5
> based_on: script-v4
> changes_from_prev: SSML naturalization — removed excessive <s> tags, reduced breaks from ~55 to ~20, naturalized repeated numbers (casual/rounded on 2nd+ mention), lowercased all emphasis words (DREAM→dream etc.), removed all <prosody pitch> tags, improved sentence flow within <p> blocks for Chirp 3: HD Sulafat voice. Speed bumped to 1.15, break times reduced (1000→600, 800→400, 500→250, 300→150).
> date: 2026-03-22

## Metadata
- **Word count:** ~1,493 spoken words (voiceover only, SSML stripped)
- **Word budget:** ~1,596-1,729 words (target 12:00-13:00, 136.6 WPM calibrated)
- **Estimated duration:** ~11:16 raw (656s speech + 20.5s pauses); ~11:50 at 1.05x speed
- **Tone:** Neutral-analytic, authoritative, curiosity-driven — numbers speak for themselves
- **Target audience:** 18-35, globally curious, English-speaking, prefers facts over opinions
- **TTS engine:** Google Cloud TTS — Chirp 3: HD, voice: Sulafat, input mode: SSML, speed: 1.15

---

## Hook (0:00–0:35)

[VISUAL NOTE] Dark screen. A single clock icon ticks. Then a question fades in as white text: "What is one hour of your life worth?" Hold for 2 seconds. The text dissolves. A world map silhouette appears — dots light up across countries, each a different size. No labels yet. The dots pulse gently.

[VOICEOVER]
<speak>
<p>
What is one hour of your life worth?
<break time="600ms"/>
The answer depends almost entirely on one thing. Where you were born.
</p>
<break time="400ms"/>
<p>
In some countries, an hour of work buys a full meal for a family. In others, it barely covers a cup of coffee. And the countries where people work the longest hours... are almost never the ones where people earn the most.
<break time="250ms"/>
Here's what the data actually shows.
</p>
</speak>

---

## Section: Raw Salary Rankings (0:35–1:35)

[VISUAL NOTE] A horizontal bar chart builds on screen. Title: "Average Annual Salary (Nominal USD)." Bars appear one by one from the top: Switzerland ($106K nominal — placeholder visual, exact nominal not used in voiceover), Luxembourg, Iceland, USA, etc. About 10 countries shown. The USA bar is highlighted. The chart looks straightforward — rich countries at the top, poorer at the bottom. This is the "obvious" ranking the viewer thinks they understand.

[VOICEOVER]
<speak>
<p>
Start with the obvious. Average annual salary, in raw US dollars. Switzerland near the top. Luxembourg. Iceland. The United States.
<break time="150ms"/>
Down the list: Germany, Canada, Australia, the United Kingdom. Further down: Spain, Portugal, Poland. At the bottom: Greece, Hungary, Mexico.
</p>
<break time="250ms"/>
<p>
This is the ranking most people picture when they think about global salaries. Rich countries earn more, poorer countries earn less. Simple. Intuitive.
<break time="400ms"/>
And misleading.
</p>
<break time="150ms"/>
<p>
Because a dollar in Zurich does not buy what a dollar buys in Warsaw. Or in Mexico City. Or in Tokyo. To compare salaries honestly, you have to account for what that money actually buys.
</p>
</speak>

---

## Section: Purchasing Power Parity (1:35–3:15)

[VISUAL NOTE] Split screen animation: an identical grocery basket appears in two cities — Zurich (left) and Mexico City (right). Same items: bread, milk, eggs, rice, chicken. Price tags float above each item — Zurich prices are 3-4× higher. The total at the bottom shows the gap. Then a title card: "Purchasing Power Parity (PPP)." The OECD logo appears with text: "~3,000 goods & services tracked." Then the bar chart from the previous section re-sorts with PPP-adjusted values. Some countries jump up, others slide down. USA moves to 4th. Luxembourg takes #1.

[VOICEOVER]
<speak>
<p>
Three thousand dollars a month. In parts of Mexico, that covers rent, food, and transport — with room to spare. In Zurich, it barely covers a studio apartment. Same number. Completely different lives.
</p>
<break time="400ms"/>
<p>
So economists use something called Purchasing Power Parity — or PPP. The OECD tracks prices of roughly three thousand goods and services in each country — bread, rice, electricity, rent, haircuts, public transport — and calculates a conversion factor for every currency. That conversion factor adjusts each country's wages so they reflect actual buying power, not just a raw dollar amount.
</p>
<p>
When the OECD says a Swiss worker earns eighty-seven thousand PPP dollars, it means that salary buys the same amount of stuff as eighty-seven thousand dollars would in the United States. Apples to apples.
</p>
<break time="250ms"/>
<p>
After this adjustment, the rankings shift. Luxembourg takes the top spot — ninety-four thousand four hundred forty-seven dollars. Iceland second at almost ninety thousand. Switzerland third at eighty-seven thousand four hundred sixty-eight. The United States fourth at eighty-two thousand nine hundred thirty-three.
<break time="250ms"/>
At the bottom of thirty-four OECD countries: Greece at thirty-two thousand two hundred fifty-seven. And Mexico at twenty thousand four hundred thirty-three.
</p>
<break time="400ms"/>
<p>
Now you know what people actually earn — in real purchasing power. But that's only half the picture.
</p>
</speak>

---

## Section: Introducing the Quadrant (3:15–4:15)

[VISUAL NOTE] The PPP bar chart tilts and transforms. The salary axis becomes the Y-axis of a scatter plot. A new X-axis extends: "Annual Hours Worked." A crosshair fades in at the origin point: $59,200 (Y) and 1,633 hours (X). Label: "34-country average." Four quadrant labels appear one by one with subtle color fills: DREAM (top-left, green), GRIND (top-right, amber), CHILL (bottom-left, blue), TRAP (bottom-right, red). Then ALL 34 country dots animate in simultaneously — no labels yet. Just dots scattered across the four quadrants.

[VOICEOVER]
<speak>
<p>
How many hours do people work for that salary? Because sixty-nine thousand dollars means one thing if you work one thousand three hundred forty hours a year — that's Germany. It means something very different at two thousand two hundred twenty-six hours — that's Mexico.
</p>
<break time="250ms"/>
<p>
Plot salary on one axis, hours on the other. The crosshair sits at the thirty-four-country average: fifty-nine thousand two hundred dollars and one thousand six hundred thirty-three hours.
<break time="250ms"/>
Four quadrants.
</p>
<p>
Top left — high pay, low hours. We call it the dream. Top right — high pay, high hours. The grind. Bottom left — low pay, low hours. The chill. Bottom right — low pay, high hours. The trap.
<break time="400ms"/>
Thirty-four countries. Four stories.
</p>
</speak>

---

## Section: The Dream Quadrant (4:15–5:45)

[VISUAL NOTE] Camera stays on the full quadrant chart. The DREAM quadrant (top-left) gets a subtle green glow. Country labels appear on the 13 dots in this quadrant. Luxembourg pulses at the top. Germany pulses at the far left (fewest hours). A tooltip appears near Germany's dot: "$69,433 | 1,340 hrs | $51.82/hr." Then Luxembourg's tooltip: "$94,447 | 1,473 hrs | $64.12/hr." A small annotation: "13 of 34 countries." The other quadrants remain visible but slightly dimmed.

[VOICEOVER]
<speak>
<p>
Thirteen countries land in the dream quadrant. Above-average salary, below-average hours.
<break time="250ms"/>
Luxembourg sits at the very top — roughly ninety-four and a half thousand dollars on about fourteen hundred seventy hours. That's sixty-four dollars and twelve cents per hour — the highest in the dataset.
</p>
<p>
But the most notable position belongs to Germany. Germany works the fewest hours of any country in the dataset — one thousand three hundred forty per year. Its salary of roughly sixty-nine and a half thousand dollars translates to almost fifty-two dollars an hour.
</p>
<p>
Denmark sits close by — about thirteen hundred seventy hours, almost fifty-four dollars per hour. The second-fewest hours and the fourth-highest hourly rate in the dataset.
<break time="250ms"/>
The rest of this quadrant reads like a map of Western and Northern Europe. The Netherlands, Norway, Belgium, Austria, Switzerland, Iceland. Then the UK, France, Finland, Slovenia.
<break time="400ms"/>
Not a single country outside Europe appears here.
</p>
</speak>

---

## Section: The Grind Quadrant (5:45–7:15)

[VISUAL NOTE] Camera stays on full quadrant. GRIND quadrant (top-right) gets amber glow. Five dots labeled: USA, AUS, CAN, NZL, IRL. Country flags appear next to each dot. A text overlay: "5 countries. All English-speaking." A connector line draws from USA's dot to Denmark's dot (in DREAM). Stats along the line: "439 hours apart | DNK earns 18% more per hour." USA tooltip: "$82,933 | 1,810 hrs | $45.82/hr." Denmark tooltip: "$74,022 | 1,371 hrs | $53.99/hr."

[VOICEOVER]
<speak>
<p>
Five countries in the grind. Above-average salary, above-average hours.
<break time="250ms"/>
The United States. Australia. Canada. New Zealand. Ireland. Every single one is English-speaking. The entire Anglosphere — and no one else.
</p>
<break time="400ms"/>
<p>
The United States earns the highest total salary in this quadrant — almost eighty-three thousand dollars. But at eighteen hundred ten hours per year. Compare that to Denmark, in the dream quadrant. Denmark earns about eleven percent less in total salary, but nearly eighteen percent more per hour — roughly fifty-four dollars versus about forty-six.
<break time="250ms"/>
The difference is four hundred thirty-nine hours. Fifty-five eight-hour workdays. Nearly eleven extra work weeks per year — for about eleven percent more pay.
</p>
<p>
Australia and Canada sit in the middle of this quadrant — both around forty-one dollars per hour. Nearly the same hourly rate as Sweden, which sits in the chill quadrant on far fewer hours.
</p>
</speak>

---

## Section: The Trap Quadrant (7:15–9:00)

[VISUAL NOTE] Camera stays on full quadrant. TRAP quadrant (bottom-right) gets red glow. Eleven dots labeled. Germany's dot (in DREAM) and Greece's dot (in TRAP) both pulse. A connector line draws diagonally across the chart between them — it spans nearly the entire plot. Stats on the line: "3× more per hour | 546 fewer hours." Then the connector fades and Korea's dot and Italy's dot pulse side by side — nearly same Y position, different X. Tooltip: Korea "$50,947 | 1,901 hrs" vs Italy "$51,019 | 1,694 hrs." Text: "207 extra hours. $72 difference." Mexico's dot pulses at the far extreme corner.

[VOICEOVER]
<speak>
<p>
Eleven countries in the trap. Below-average salary, above-average hours.
<break time="250ms"/>
This is where the gaps are widest.
</p>
<p>
Draw a line from Greece to Germany. Both are in the European Union. A German worker earns roughly three times as much per hour — almost fifty-two dollars versus about seventeen — while working five hundred forty-six fewer hours per year.
<break time="400ms"/>
Same economic bloc. Same currency. Completely different quadrants.
</p>
<p>
South Korea and Italy tell a quieter story. Korea earns fifty thousand nine hundred forty-seven dollars. Italy earns fifty-one thousand nineteen. A difference of seventy-two dollars. But Korea works two hundred seven more hours per year for that nearly identical paycheck. Twenty-six extra workdays. Same salary. A month more of work.
</p>
<break time="250ms"/>
<p>
And then there's Mexico — the far extreme. Two thousand two hundred twenty-six hours per year — the most in the OECD. At nine dollars and eighteen cents per hour. Luxembourg earns seven times more per hour than Mexico, while working about seven hundred fifty fewer hours.
</p>
</speak>

---

## Section: The Chill Quadrant (9:00–9:50)

[VISUAL NOTE] Camera stays on full quadrant. CHILL quadrant (bottom-left) gets blue glow. Five dots labeled: SWE, JPN, LTU, LVA, SVK. Sweden's dot pulses very close to the horizontal salary mean line — an annotation shows it's just $142 below. Japan's dot gets a small "?" icon. Tooltip for Japan: "$49,446 | 1,607 hrs." A brief text overlay: "karoshi — death from overwork."

[VOICEOVER]
<speak>
<p>
Five countries in the chill quadrant. Below-average salary, below-average hours.
<break time="250ms"/>
Sweden is the first thing you notice. At fifty-nine thousand fifty-eight dollars, it sits just one hundred forty-two dollars below the salary mean. Its hourly rate — forty-one dollars — matches Australia and Canada, both in the grind, working hundreds of hours more. Sweden is chill by a rounding error.
</p>
<break time="250ms"/>
<p>
Then there's Japan. The country synonymous with overwork — with karoshi, a word that literally means death from overwork — logs about sixteen hundred hours per year. Below the OECD average. The catch: the OECD counts all workers, including part-time. Japan has a large and growing part-time workforce that pulls the average down. Full-time Japanese workers still log extreme hours. The statistic is accurate — it just measures something different than most people expect.
</p>
</speak>

---

## Section: The Ugly Truth (9:50–11:50)

[VISUAL NOTE] The full quadrant is visible with all 34 OECD dots. Then the camera slowly zooms OUT — the axes extend. The X-axis stretches past 2,500 hours. The Y-axis drops below $12,000. Six new dots appear in a cluster at the far bottom-right — deep red color, different marker shape (squares instead of circles). They're labeled one by one: India, Bangladesh, Cambodia, Pakistan, Nigeria, Philippines. A small disclaimer text appears in the corner: "⚠️ Non-OECD data: World Bank GNI per capita (PPP) + ILO hours. Different methodology." Connector line from Germany to Cambodia spans the entire chart diagonally. Stats: "22.5× more per hour | 1,049 fewer hours." The OECD origin crosshair ($59,200 / 1,633 hrs) stays in place — these new dots are far below and far to the right of it.

[VOICEOVER]
<speak>
<p>
Everything so far has been the OECD — thirty-four of the world's wealthier nations. Zoom out.
<break time="400ms"/>
Six more countries. India. Bangladesh. Cambodia. Pakistan. Nigeria. Philippines.
</p>
<p>
Now — these numbers come from different sources than our OECD data. World Bank and ILO estimates, which measure income differently. The comparison isn't perfectly apples to apples. But even with generous assumptions, the gap is so massive that the methodology differences don't change the story.
</p>
<break time="400ms"/>
<p>
Cambodia. Five thousand five hundred dollars a year. Two thousand three hundred eighty-nine hours. Two dollars and thirty cents per hour. A German worker earns twenty-two and a half times more per hour — while working over a thousand fewer hours per year.
</p>
<p>
Pakistan logs two thousand four hundred seventy-one hours — the most in the entire dataset — at two dollars and eighty-three cents per hour. India — one point four billion people — averages three dollars and sixty-one cents per hour. Luxembourg earns nearly eighteen times more per hour than India, while working fewer hours.
</p>
<p>
Bangladesh — about two ninety-five an hour, nearly twenty-four hundred hours a year. This is the country that produces a significant share of the world's garments. A German worker earns the entire Bangladeshi annual salary in about five weeks.
</p>
<break time="250ms"/>
<p>
Look at the chart. Mexico was the worst in the OECD at about nine dollars an hour. Every one of these six countries earns less than Mexico — and five of the six earn less than half. The bottom of the OECD is still far above the global average. That's not an opinion. That's what the data shows.
</p>
</speak>

---

## Section: Closing (11:50–13:00)

[VISUAL NOTE] The full chart is visible — all 40 countries (34 OECD + 6 ugly truth). Camera slowly pulls back to show the complete picture. The quadrant labels glow faintly. The massive diagonal gap between Luxembourg (top-left) and Cambodia (bottom-right) is visible. Then all dots except two fade: one in DREAM (Germany or Luxembourg), one in deep TRAP (Cambodia or Pakistan). The two remaining dots pulse gently on opposite ends of the chart. Then they fade too. The axes remain for a moment. Then the question from the hook returns as text: "What is one hour of your life worth?" Hold. Fade to black.

[VOICEOVER]
<speak>
<p>
Forty countries. Two axes. Four quadrants.
<break time="400ms"/>
A worker in Luxembourg earns about sixty-four dollars per hour on roughly fourteen hundred seventy hours per year. A worker in Cambodia earns two dollars and thirty cents per hour on almost twenty-four hundred hours. One earns nearly twenty-eight times more. The other works nine hundred sixteen more hours. And both show up to work every morning.
</p>
<break time="400ms"/>
<p>
Salary alone doesn't tell you who's better off. Time matters. But even time and salary together don't explain the full picture. Because the single biggest predictor of which quadrant you land in... is which country you were born in.
<break time="600ms"/>
Not how hard you work. Not how many hours you put in.
</p>
<p>
<prosody rate="slow">Where you were born.</prosody>
<break time="400ms"/>
The numbers don't tell you what an hour of your life is worth. They just show you how differently the world answers that question.
</p>
</speak>
