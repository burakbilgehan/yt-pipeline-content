# Fabric Health Comparison — Feedback

<!-- Aşağıya feedback'lerini yaz. Scene bazlı, genel, görsel, ses, ne varsa. -->

## Genel İzlenim
- cok kotu video. hala bisuru konustugumuz sey uygulanmamis. 
- her sey hala cok kucuk. ![alt text](image.png) su sence ekranin yuzde 80 kullanimi mi? aptal ozurlu
  - **DURUM: KISMİ** — HorizontalBarChart, BarChart, PieChart boyutlandırmaları artırıldı ama hâlâ yeterli değil. Tüm chart componentlerinde padding/margin agresif azaltılmalı.
- pauselar cok uzun. ayrica arada narrator pause falan diyo. hala su ssml isini cozemedin aq. hala konusmalar cok inorganik
  - **DURUM: YAPILDI** — `convertPauseMarkup()` + `escapeForSSML()` eklendi. TTS yeniden üretildi, 27/27 blok hatasız. "PAUSE" diyen narrator sorunu çözüldü. Sahne sonu padding 1.0s'ye düşürüldü (eskisi daha fazlaydı).
- ozellikle her sahnenin sonunda anlamsiz bi uzunlukta bekleme var
  - **DURUM: KISMİ** — Timing yeniden hesaplandı, scene padding 1.0s'ye düşürüldü + 0.5s gap. Ama hâlâ fazla olabilir, daha agresif kısılabilir.
- su amina kodugumun videosunu MOBILE FRIENDLY YAP
  - **DURUM: YAPILMADI** — Font boyutları DS VB-4'e uygun ama genel ekran kullanımı hâlâ yetersiz.
- ozellikle sayisal bi iddiada bulundugun her sahnenin altina disclaimer olarak kaynak vereceksin
  - **DURUM: YAPILDI** — 27 scene dosyasına `sourceText` eklendi, MainComposition'a citation overlay (bottom-right, 16px, faded) eklendi.
- cogu ekrani, ekranin sadce 1/4, 1/5ini kaplayacak bir dikdortgenin icinde verip geciyosun. accent olarak da mor bir renk seciyosun. cok kotu bu
  - **DURUM: KISMİ** — Mor (#6C63FF) Root.tsx'ten ve PieChart'tan tamamen temizlendi. Ama ekran kullanımı hâlâ yetersiz.
- yatay bar chartlarda cubuklarinin kalinligi cok kisa. barlar ince uzun cizgiler gibi dum ekran boyunca uzuyo. okumak cok zor. bu kadar az ogenin oldugu bar chartlari daha kalin ve daha okunabilir yap. simdi sanki ekranin dikey olarak yuzde 10una 3-4 tane ince cubugu sigdirip kalanini bos birakiyoruz
  - **DURUM: KISMİ** — Bar kalınlıkları artırıldı (56/44/36 dinamik) ama hâlâ yeterli olmayabilir. İkinci geçiş gerekli.
- bar chartlarin kimini dikdortgen yapiyosun kimini yuvarlak koseli sanki elips gibi. iste bu yuzden bir markamiz olamiyor
  - **DURUM: YAPILDI** — Tüm bar chart'larda borderRadius: 6 olarak standardize edildi.
- tilt motionini hic kullanmamissin sanki
  - **DURUM: YAPILMADI** — TiltCard motion primitive var ama hiçbir sahne scene dosyasında kullanılmıyor.
- 2 yeni doku ekledim. bi bak bakalim. belki de de senin o tekduze dikdortgen cercevelerinden buna degisiriz. arka planlari da hafif renklendiririz ki mat camin o guzel goruntusu ortaya ciksin. bu ikisini kendimize adapte et (decompose, classify, adapt vs). ikisini de yukle ve sakin kendi yorumunu katma. su anki yari gecirgen ama ayni zamanda parlamayan mat arkaplan cok iyi. bunlari repertuarda istiyorum
  - **DURUM: YAPILDI** — Glass Calendar → FrostedPanelSurface (L4, 'frosted-panel'), Glassmorphism Trust Hero → CardSurface (L4, 'card'). 4-step intake gate tamamlandı: Decompose ✅, Adapt ✅, Register ✅, Showcase ✅ (SurfaceShowcase3.tsx → Root.tsx 'FrostedPanel-Card'). component-catalog.json güncellendi. DESIGN-SYSTEM.md inventory güncellendi.


## Scene Bazlı Notlar
- scene 1, her sey hem cok kucuk hem de glowa koydugun renk ne? glow renk secimi ne oyle, neye dayanarak o renk? ayrica sahne sonu asiri fazla duraksama var
- scene 2 ayni yorumlar gecerli. bu mor renkli acentlr nerden geliyo aq? bu kanalin kendi renk semasi yok mu? ayrica PAUSE diyo narrator. saka mi 
- scene 3-4 ekran kullanimi yine rezalet. ![alt text](image-1.png)
- scene 5, ![alt text](image-2.png) ya madem her seyi boyle bi sectiona sarip onun rengini baska yapacaksin, ne diye backgroundla ugrasiyoruz. mesela bu kadar basit ekranda hem bg hem ustune alakasiz bir renkte bgsi olan bir sectioninin icinde grafigi neden veriyoruz
- 6, ![alt text](image-3.png) alignment saka mi? yazilar ayni yerde baslamiyo bile. hayir bi de 73yi full yapip 61i neden kesik yapiyosun
- 7, ![alt text](image-4.png).yani en basit bilgi verdigin sahneleri bile bu sekilde sikici bi sekilde veriyosun. amina koyim ekranin yuzde 20sini bile kaplamiyo faydali alanlar. sunu her yerde cozmelisin. her seyi dip dibe ve ekran limitimiz varmis gibi kullanamazsin. ayrica bu dikdortgenleri bi siyah veriyosun bi arkaplanla ayni renkte. 
- 8, ![alt text](image-5.png) yine yerimiz yok gibi her seyi tikistirdigin icin amina koyim, yazilar bile tasmis. bu da bi diger ornek ![alt text](image-6.png)
- 11, ![alt text](image-7.png) bundan emin miyiz? cotton daha kotu cikiyo. ayrica bu kez neden dairelerle ifade ettik ayni seyi? 15te de bu tarz grafik kullanmissin, ne alaka?
- 12, daha once yaptigim tum yorumlarin gecerli oldugu bi sahne. cok fazla yanlisi var
- 13, yine ayni sekil, ekran kullanimi, renk kotulugu, tum yorumlar gecerli
- 14 ve 16, yine igrenc bir bar chart. yukarida verdigim yorumlar gecerli, ekrani fakir gibi kullaniyosun. yazilar bile sigmamis
- 17-18 bence hic bizim tarzimiza uygun degil. artistik olarak daha isabetli promptlar vermeliydin. ayrica gemini logosu gozukuyo. daha zoom in yapsana.
- 19 burada gorselin uzerine grafik koymak ne kadar iyi fikir? ![alt text](image-9.png) yani belki yukarida bahsettigim yeni glassmorphism arka planlarini eklersek o zaman belki ise yarar. sahe 24e kadar ayni yorumlar gecerli. ayrica sahnelerin hepsinde ayri sey denemissin. kiminde arkaplanda dortgen yok. kiminde var, kiminda yarisaydam var, kiminde arkaplan kararmis. neyin pesindesin? salak misin?
- sahne 22 direkt bos
- 25 yine igrenc ekran kullanimi
- sahne 26 tam yeni VerticalTabScene i kullanmalikmis. neden bunu dusunemedin? ![alt text](image-10.png) ayni sahnede bu renk secimi ne aq? bizim ne zaman yesil renk accentimiz oldu? hele bi de oyle bi ton ki, kanala hic uymuyo. salak
- 27de yine anlik olarak resim gozukuyo ama yarim saniye bile degil. direkt salaklik 


## Teknik Sorunlar


## Diğer

## Glass Calendar

Buradaki calendarin arka plan yapisini cok begendim. liquid glass gibi degil, mat bir buzlu cam gibi. bunu kendi DS'imize entegre edebiliriz. senin o sik sik kullandigin her seyi dikdortgene sarma metodu bi ise yarar.

You are given a task to integrate an existing React component in the codebase

The codebase should support:
- shadcn project structure  
- Tailwind CSS
- Typescript

If it doesn't, provide instructions on how to setup project via shadcn CLI, install Tailwind or Typescript.

Determine the default path for components and styles. 
If default path for components is not /components/ui, provide instructions on why it's important to create this folder
Copy-paste this component to /components/ui folder:
```tsx
glass-calendar.tsx
import * as React from "react";
import { Settings, Plus, Edit2, ChevronLeft, ChevronRight } from "lucide-react";
import { format, addMonths, subMonths, isSameDay, isToday, getDate, getDaysInMonth, startOfMonth } from "date-fns";
import { motion } from "framer-motion";
import { cn } from "@/lib/utils"; // Assuming you have a `cn` utility from shadcn

// --- TYPE DEFINITIONS ---
interface Day {
  date: Date;
  isToday: boolean;
  isSelected: boolean;
}

interface GlassCalendarProps extends React.HTMLAttributes<HTMLDivElement> {
  selectedDate?: Date;
  onDateSelect?: (date: Date) => void;
  className?: string;
}

// --- HELPER TO HIDE SCROLLBAR ---
const ScrollbarHide = () => (
  <style>{`
    .scrollbar-hide::-webkit-scrollbar {
      display: none;
    }
    .scrollbar-hide {
      -ms-overflow-style: none;
      scrollbar-width: none;
    }
  `}</style>
);


// --- MAIN COMPONENT ---
export const GlassCalendar = React.forwardRef<HTMLDivElement, GlassCalendarProps>(
  ({ className, selectedDate: propSelectedDate, onDateSelect, ...props }, ref) => {
    const [currentMonth, setCurrentMonth] = React.useState(propSelectedDate || new Date());
    const [selectedDate, setSelectedDate] = React.useState(propSelectedDate || new Date());

    // Generate all days for the current month
    const monthDays = React.useMemo(() => {
        const start = startOfMonth(currentMonth);
        const totalDays = getDaysInMonth(currentMonth);
        const days: Day[] = [];
        for (let i = 0; i < totalDays; i++) {
            const date = new Date(start.getFullYear(), start.getMonth(), i + 1);
            days.push({
                date,
                isToday: isToday(date),
                isSelected: isSameDay(date, selectedDate),
            });
        }
        return days;
    }, [currentMonth, selectedDate]);

    const handleDateClick = (date: Date) => {
      setSelectedDate(date);
      onDateSelect?.(date);
    };
    
    const handlePrevMonth = () => {
        setCurrentMonth(subMonths(currentMonth, 1));
    };

    const handleNextMonth = () => {
        setCurrentMonth(addMonths(currentMonth, 1));
    };

    return (
      <div
        ref={ref}
        className={cn(
          "w-full max-w-[360px] rounded-3xl p-5 shadow-2xl overflow-hidden",
          "bg-black/20 backdrop-blur-xl border border-white/10",
          "text-white font-sans",
          className
        )}
        {...props}
      >
        <ScrollbarHide />
        {/* Header: Tabs and Settings */}
        <div className="flex items-center justify-between">
          <div className="flex items-center space-x-1 rounded-lg bg-black/20 p-1">
            <button className="rounded-md bg-white px-4 py-1 text-xs font-bold text-black shadow-md">
              Weekly
            </button>
            <button className="rounded-md px-4 py-1 text-xs font-semibold text-white/60 transition-colors hover:text-white">
              Monthly
            </button>
          </div>
          <button className="p-2 text-white/70 transition-colors hover:bg-black/20 rounded-full">
            <Settings className="h-5 w-5" />
          </button>
        </div>

        {/* Date Display and Navigation */}
        <div className="my-6 flex items-center justify-between">
            <motion.p 
              key={format(currentMonth, "MMMM")}
              initial={{ opacity: 0, y: -10 }} 
              animate={{ opacity: 1, y: 0 }} 
              transition={{ duration: 0.3 }}
              className="text-4xl font-bold tracking-tight"
            >
                {format(currentMonth, "MMMM")}
            </motion.p>
            <div className="flex items-center space-x-2">
                <button onClick={handlePrevMonth} className="p-1 rounded-full text-white/70 transition-colors hover:bg-black/20">
                    <ChevronLeft className="h-5 w-5" />
                </button>
                <button onClick={handleNextMonth} className="p-1 rounded-full text-white/70 transition-colors hover:bg-black/20">
                    <ChevronRight className="h-5 w-5" />
                </button>
            </div>
        </div>

        {/* Scrollable Monthly Calendar Grid */}
        <div className="overflow-x-auto scrollbar-hide -mx-5 px-5">
            <div className="flex space-x-4">
                {monthDays.map((day) => (
                    <div key={format(day.date, "yyyy-MM-dd")} className="flex flex-col items-center space-y-2 flex-shrink-0">
                        <span className="text-xs font-bold text-white/50">
                            {format(day.date, "E").charAt(0)}
                        </span>
                        <button
                            onClick={() => handleDateClick(day.date)}
                            className={cn(
                                "flex h-8 w-8 items-center justify-center rounded-full text-sm font-semibold transition-all duration-200 relative",
                                {
                                    "bg-gradient-to-br from-pink-500 to-orange-400 text-white shadow-lg": day.isSelected,
                                    "hover:bg-white/20": !day.isSelected,
                                    "text-white": !day.isSelected,
                                }
                            )}
                        >
                            {day.isToday && !day.isSelected && (
                                <span className="absolute bottom-1 h-1 w-1 rounded-full bg-pink-400"></span>
                            )}
                            {getDate(day.date)}
                        </button>
                    </div>
                ))}
            </div>
        </div>
        
        {/* Divider */}
        <div className="mt-6 h-px bg-white/20" />

        {/* Footer Actions */}
        <div className="mt-4 flex items-center justify-between space-x-4">
           <button className="flex items-center space-x-2 text-sm font-medium text-white/70 transition-colors hover:text-white">
             <Edit2 className="h-4 w-4" />
             <span>Add a note...</span>
           </button>
           <button className="flex items-center space-x-2 rounded-lg bg-black/20 px-3 py-2 text-xs font-bold text-white shadow-md transition-colors hover:bg-black/30">
             <Plus className="h-4 w-4" />
             <span>New Event</span>
           </button>
        </div>
      </div>
    );
  }
);

GlassCalendar.displayName = "GlassCalendar";


demo.tsx
import * as React from "react";
import { GlassCalendar } from "@/components/ui/glass-calendar"; // Adjust the import path as needed

export default function GlassCalendarDemo() {
  const [selectedDate, setSelectedDate] = React.useState(new Date());
  
  // A high-quality, abstract background image for the glass effect
  const backgroundImageUrl = "https://plus.unsplash.com/premium_photo-1673873438024-81d29f555b95?w=900&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NjM2fHxjb2xvcnxlbnwwfHwwfHx8MA%3D%3D";

  return (
    <div 
      className="flex min-h-screen w-full items-center justify-center bg-cover bg-center p-4 bg-slate-900"
      style={{ backgroundImage: `url(${backgroundImageUrl})` }}
    >
      <GlassCalendar 
        selectedDate={selectedDate}
        onDateSelect={setSelectedDate}
        className="transform transition-transform duration-500 hover:scale-105"
      />
    </div>
  );
}

```

Install NPM dependencies:
```bash
date-fns, lucide-react, framer-motion
```


## Glassmorphism Trust Hero

Alternatif olarak ![alt text](image-8.png)burada ekranin sag tarafindaki sectionlarin arka plan yapisini cok begendim. liquid glass gibi degil, mat bir buzlu cam gibi. bunu kendi DS'imize entegre edebiliriz. senin o sik sik kullandigin her seyi dikdortgene sarma metodu bi ise yarar.

You are given a task to integrate an existing React component in the codebase

The codebase should support:
- shadcn project structure  
- Tailwind CSS
- Typescript

If it doesn't, provide instructions on how to setup project via shadcn CLI, install Tailwind or Typescript.

Determine the default path for components and styles. 
If default path for components is not /components/ui, provide instructions on why it's important to create this folder
Copy-paste this component to /components/ui folder:
```tsx
glassmorphism-trust-hero.tsx
import React from "react";
import { 
  ArrowRight, 
  Play, 
  Target, 
  Crown, 
  Star,
  // Brand Icons
  Hexagon,
  Triangle,
  Command,
  Ghost,
  Gem,
  Cpu
} from "lucide-react";

// --- MOCK BRANDS ---
// Replaced PNGs with Lucide icons to simulate tech logos
const CLIENTS = [
  { name: "Acme Corp", icon: Hexagon },
  { name: "Quantum", icon: Triangle },
  { name: "Command+Z", icon: Command },
  { name: "Phantom", icon: Ghost },
  { name: "Ruby", icon: Gem },
  { name: "Chipset", icon: Cpu },
];

// --- SUB-COMPONENTS ---
const StatItem = ({ value, label }: { value: string; label: string }) => (
  <div className="flex flex-col items-center justify-center transition-transform hover:-translate-y-1 cursor-default">
    <span className="text-xl font-bold text-white sm:text-2xl">{value}</span>
    <span className="text-[10px] uppercase tracking-wider text-zinc-500 font-medium sm:text-xs">{label}</span>
  </div>
);

// --- MAIN COMPONENT ---
export default function HeroSection() {
  return (
    <div className="relative w-full bg-zinc-950 text-white overflow-hidden font-sans">
      {/* 
        SCOPED ANIMATIONS 
      */}
      <style>{`
        @keyframes fadeSlideIn {
          from { opacity: 0; transform: translateY(20px); }
          to { opacity: 1; transform: translateY(0); }
        }
        @keyframes marquee {
          from { transform: translateX(0); }
          to { transform: translateX(-50%); }
        }
        .animate-fade-in {
          animation: fadeSlideIn 0.8s ease-out forwards;
          opacity: 0;
        }
        .animate-marquee {
          animation: marquee 40s linear infinite; /* Slower for readability */
        }
        .delay-100 { animation-delay: 0.1s; }
        .delay-200 { animation-delay: 0.2s; }
        .delay-300 { animation-delay: 0.3s; }
        .delay-400 { animation-delay: 0.4s; }
        .delay-500 { animation-delay: 0.5s; }
      `}</style>

      {/* Background Image with Gradient Mask */}
      <div 
        className="absolute inset-0 z-0 bg-[url(https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/a72ca2f3-9dd1-4fe4-84ba-fe86468a5237_3840w.webp?w=800&q=80)] bg-cover bg-center opacity-40"
        style={{
          maskImage: "linear-gradient(180deg, transparent, black 0%, black 70%, transparent)",
          WebkitMaskImage: "linear-gradient(180deg, transparent, black 0%, black 70%, transparent)",
        }}
      />

      <div className="relative z-10 mx-auto max-w-7xl px-4 pt-24 pb-12 sm:px-6 md:pt-32 md:pb-20 lg:px-8">
        <div className="grid grid-cols-1 gap-12 lg:grid-cols-12 lg:gap-8 items-start">
          
          {/* --- LEFT COLUMN --- */}
          <div className="lg:col-span-7 flex flex-col justify-center space-y-8 pt-8">
            
            {/* Badge */}
            <div className="animate-fade-in delay-100">
              <div className="inline-flex items-center gap-2 rounded-full border border-white/10 bg-white/5 px-3 py-1.5 backdrop-blur-md transition-colors hover:bg-white/10">
                <span className="text-[10px] sm:text-xs font-semibold uppercase tracking-wider text-zinc-300 flex items-center gap-2">
                  Award-Winning Design
                  <Star className="w-3.5 h-3.5 text-yellow-400 fill-yellow-400" />
                </span>
              </div>
            </div>

            {/* Heading */}
            <h1 
              className="animate-fade-in delay-200 text-5xl sm:text-6xl lg:text-7xl xl:text-8xl font-medium tracking-tighter leading-[0.9]"
              style={{
                maskImage: "linear-gradient(180deg, black 0%, black 80%, transparent 100%)",
                WebkitMaskImage: "linear-gradient(180deg, black 0%, black 80%, transparent 100%)"
              }}
            >
              Crafting Digital<br />
              <span className="bg-gradient-to-br from-white via-white to-[#ffcd75] bg-clip-text text-transparent">
                Experiences
              </span><br />
              That Matter
            </h1>

            {/* Description */}
            <p className="animate-fade-in delay-300 max-w-xl text-lg text-zinc-400 leading-relaxed">
              We design interfaces that combine beauty with functionality,
              creating seamless experiences that users love and businesses thrive on.
            </p>

            {/* CTA Buttons */}
            <div className="animate-fade-in delay-400 flex flex-col sm:flex-row gap-4">
              <button className="group inline-flex items-center justify-center gap-2 rounded-full bg-white px-8 py-4 text-sm font-semibold text-zinc-950 transition-all hover:scale-[1.02] hover:bg-zinc-200 active:scale-[0.98]">
                View Portfolio
                <ArrowRight className="w-4 h-4 transition-transform group-hover:translate-x-1" />
              </button>
              
              <button className="group inline-flex items-center justify-center gap-2 rounded-full border border-white/10 bg-white/5 px-8 py-4 text-sm font-semibold text-white backdrop-blur-sm transition-colors hover:bg-white/10 hover:border-white/20">
                <Play className="w-4 h-4 fill-current" />
                Watch Showreel
              </button>
            </div>
          </div>

          {/* --- RIGHT COLUMN --- */}
          <div className="lg:col-span-5 space-y-6 lg:mt-12">
            
            {/* Stats Card */}
            <div className="animate-fade-in delay-500 relative overflow-hidden rounded-3xl border border-white/10 bg-white/5 p-8 backdrop-blur-xl shadow-2xl">
              {/* Card Glow Effect */}
              <div className="absolute top-0 right-0 -mr-16 -mt-16 h-64 w-64 rounded-full bg-white/5 blur-3xl pointer-events-none" />

              <div className="relative z-10">
                <div className="flex items-center gap-4 mb-8">
                  <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-white/10 ring-1 ring-white/20">
                    <Target className="h-6 w-6 text-white" />
                  </div>
                  <div>
                    <div className="text-3xl font-bold tracking-tight text-white">150+</div>
                    <div className="text-sm text-zinc-400">Projects Delivered</div>
                  </div>
                </div>

                {/* Progress Bar Section */}
                <div className="space-y-3 mb-8">
                  <div className="flex justify-between text-sm">
                    <span className="text-zinc-400">Client Satisfaction</span>
                    <span className="text-white font-medium">98%</span>
                  </div>
                  <div className="h-2 w-full overflow-hidden rounded-full bg-zinc-800/50">
                    <div className="h-full w-[98%] rounded-full bg-gradient-to-r from-white to-zinc-400" />
                  </div>
                </div>

                <div className="h-px w-full bg-white/10 mb-6" />

                {/* Mini Stats Grid */}
                <div className="grid grid-cols-3 gap-4 text-center">
                  <StatItem value="5+" label="Years" />
                  <div className="w-px h-full bg-white/10 mx-auto" />
                  <StatItem value="24/7" label="Support" />
                  <div className="w-px h-full bg-white/10 mx-auto" />
                  <StatItem value="100%" label="Quality" />
                </div>

                {/* Tag Pills */}
                <div className="mt-8 flex flex-wrap gap-2">
                  <div className="inline-flex items-center gap-1.5 rounded-full border border-white/10 bg-white/5 px-3 py-1 text-[10px] font-medium tracking-wide text-zinc-300">
                    <span className="relative flex h-2 w-2">
                      <span className="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-400 opacity-75"></span>
                      <span className="relative inline-flex rounded-full h-2 w-2 bg-green-500"></span>
                    </span>
                    ACTIVE
                  </div>
                  <div className="inline-flex items-center gap-1.5 rounded-full border border-white/10 bg-white/5 px-3 py-1 text-[10px] font-medium tracking-wide text-zinc-300">
                    <Crown className="w-3 h-3 text-yellow-500" />
                    PREMIUM
                  </div>
                </div>
              </div>
            </div>

            {/* Marquee Card */}
            <div className="animate-fade-in delay-500 relative overflow-hidden rounded-3xl border border-white/10 bg-white/5 py-8 backdrop-blur-xl">
              <h3 className="mb-6 px-8 text-sm font-medium text-zinc-400">Trusted by Industry Leaders</h3>
              
              <div 
                className="relative flex overflow-hidden"
                style={{
                  maskImage: "linear-gradient(to right, transparent, black 20%, black 80%, transparent)",
                  WebkitMaskImage: "linear-gradient(to right, transparent, black 20%, black 80%, transparent)"
                }}
              >
                <div className="animate-marquee flex gap-12 whitespace-nowrap px-4">
                  {/* Triple list for seamless loop */}
                  {[...CLIENTS, ...CLIENTS, ...CLIENTS].map((client, i) => (
                    <div 
                      key={i}
                      className="flex items-center gap-2 opacity-50 transition-all hover:opacity-100 hover:scale-105 cursor-default grayscale hover:grayscale-0"
                    >
                      {/* Brand Icon */}
                      <client.icon className="h-6 w-6 text-white fill-current" />
                      {/* Brand Name */}
                      <span className="text-lg font-bold text-white tracking-tight">
                        {client.name}
                      </span>
                    </div>
                  ))}
                </div>
              </div>
            </div>

          </div>
        </div>
      </div>
    </div>
  );
}

demo.tsx
import React from 'react';
import HeroSection from '@/components/ui/glassmorphism-trust-hero';

export default function HeroDemo() {
  return (
    <div className="w-full h-screen overflow-y-auto bg-zinc-950">
      <HeroSection />
    </div>
  );
}
```

Install NPM dependencies:
```bash
lucide-react
```
