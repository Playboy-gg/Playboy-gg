<div align="center">

# Playboy-gg

**Native Android Developer — Kotlin · Jetpack Compose · Media Systems · Clean Architecture**

<img src="https://readme-typing-svg.demolab.com?font=Poppins&weight=600&size=22&pause=2000&color=00D4FF&center=true&vCenter=true&width=650&lines=Production+Android+architecture.;Debugging+at+the+ExoPlayer%2FHilt%2FRoom+layer.;Material+3+Expressive%2C+done+correctly.;I+ship+complete+features%2C+not+demos."/>

<br>

<img src="https://komarev.com/ghpvc/?username=Playboy-gg&style=flat-square&label=PROFILE%20VIEWS&color=00D4FF"/>
<img src="https://img.shields.io/github/followers/Playboy-gg?style=flat-square&logo=github&color=00D4FF"/>

</div>

---

## About

I build native Android applications from architecture through shipped feature — not prototypes. My work centers on media playback systems, dependency injection at scale, and UI that matches Material 3 Expressive's actual motion and theming spec rather than a superficial color swap.

What separates my projects from portfolio filler: I do full-codebase audits and fix root causes, not symptoms. A "duplicate album art" bug isn't a UI patch — it's tracing whether the collision is in MediaStore's art-existence check, the cache key, or a blank-URI guard, and fixing the one that's actually broken.

---

## Engineering Highlights

**MediaVault — Compose Music/Video Player** (Kotlin, Hilt, Media3/ExoPlayer, Room, Coil)
A 33-issue architecture audit surfaced problems most reviews miss:
- **Hilt DI conflict**: two `ExoPlayer` instances were being injected without qualifiers, causing playback state to silently desync between the service and UI. Fixed with `@ServicePlayer`/`@SharedPlayer` qualifier annotations — the kind of bug that passes every manual test and fails only under real usage patterns.
- **Main-thread I/O**: `ContentResolver` queries were running synchronously on the main thread, causing frame drops during library scans. Moved to coroutine dispatchers with proper cancellation.
- **Security**: found a hardcoded keystore password committed to version control — flagged and removed before it shipped.
- **Rendering**: rebuilt the frosted-glass nav bar using `android.graphics.RenderEffect` applied directly to leaf `Box` nodes, not wrapped `ComposeView` blur hacks that break on scroll.

**NexaDial — Production Dialer** (Kotlin, XML, MVVM, Room)
Replaced Material Components' `BottomNavigationView` after it caused reproducible inflate crashes — built a custom bottom nav instead of working around a framework component that didn't fit the use case. Also implemented `RoleManager`-based default-dialer prompting and a custom `BarChartView` for call statistics, drawn with raw `Canvas` rather than pulling in a charting dependency for one screen.

**M3E Showcase — Material 3 Expressive Reference Implementation**
Full documentation and working Android project covering `DynamicColors`, spring-based motion physics, and `MaterialContainerTransform`. Debugged AAPT2 build failures caused by `cornerSizePercent` and namespace collisions between `android.R.attr` and Material's own `R.attr` — a class of error that's poorly documented and easy to misdiagnose as a Gradle problem.

---

## How I Approach a Codebase

Given an unfamiliar or broken codebase, I don't patch the first symptom I find. I look for the root cause, and I care whether the fix is defensible under load, not just under a manual test pass. On DI-heavy Android projects specifically, most subtle bugs live at qualifier boundaries and lifecycle scope mismatches — that's where I look first.

I default to complete, production-grade output over stubs or `// TODO` placeholders, and I treat XML/Views versus Compose as a real architectural decision per project, not a default I don't question.

---

## Stack

<p align="left">
<img src="https://skillicons.dev/icons?i=kotlin,java,androidstudio,git,github,firebase,tensorflow"/>
</p>

| Layer | Tools |
|---|---|
| Language | Kotlin, Java |
| UI | Jetpack Compose, Material 3 Expressive, classic XML/Views |
| Architecture | MVVM, Clean Architecture, Hilt |
| Persistence | Room, SQLCipher |
| Media | Media3/ExoPlayer, Coil |
| Async | Kotlin Coroutines, Flow/StateFlow |
| ML | TensorFlow Lite (on-device inference) |

---

## GitHub Stats

<p align="center">
<img height="165" src="https://github-readme-stats.vercel.app/api?username=Playboy-gg&show_icons=true&theme=transparent&hide_border=true&count_private=true"/>
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Playboy-gg&layout=compact&theme=transparent&hide_border=true"/>
</p>

---

## Get in Touch

<!-- Fill in real links before publishing -->
<p align="left">
<a href="mailto:your-email@example.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white"/></a>
<a href="https://linkedin.com/in/your-handle"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white"/></a>
</p>

</div>
