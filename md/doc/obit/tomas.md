# Tomáš Kalibera (1978–2026)


Tomáš Kalibera, PhD, R core member, died on April 1, 2026, aged 48.


At the end of September 2025, the R Core Team met in Vienna, and, during the social events, Tomáš showed us pictures of his baby son. He was his usual self, sharp-witted in discussions and as always intent on documenting his work and demonstrating that he was worth his salary, as if anyone could doubt that he was. 

Only two months later we received the disturbing news that he had been
diagnosed with a brain tumour.  He was operated on and was quite optimistic for a while. He worked intensively on several R matters during the early months of 2026, but  it was not to last.  In late March he told us that his situation was again desperate, new tumours were inoperable and that he was in palliative care. Only a week later, he died.

His wife told us that he managed to hold a get-together with old friends. Those present describe him as "lucid, characteristically understated, himself". He then died in his sleep the following day.

Tomáš leaves behind his wife Anna, his young son Filip, and both his parents, Jiří and Eva.


## Career

Tomáš studied computer science at Charles University in Prague, earning his Mgr (MSc) in 2002 and his PhD in 2006, with a thesis on statistically rigorous regression benchmarking. Between degrees, he worked at the Czech Hydrometeorological Institute, where he built operational software for weather forecasting and nuclear debris dispersion modeling — porting legacy Fortran across platforms from NEC supercomputers to DEC Alphas.


He then went to Purdue in 2007 and worked with Jan Vitek on a real-time Java virtual machine. He implemented a complete real-time garbage collection framework and collaborated on porting software for the European Space Agency. He then worked at the University of Kent for a few years and then came back to Jan Vitek in 2012, now in Palo Alto. 

In Palo Alto, Tomáš was part of a project to develop FastR, an experimental reimplementation of R built on a framework from Oracle. However, after a while, he changed his focus towards improving the existing R from the inside. 

One of his first targets within R was the notorious `PROTECT` bugs, that would lead to crashes at seemingly random times, if temporarily allocated storage was not properly protected against being garbage collected. He presented this work at the R Summit Workshop in Copenhagen in 2015. 

In 2016 Tomáš contributed to the resolution of a friction between the release management of R and the CRAN policy. He was very constructive and helpful and could immediately see the issues that were at the root of the problem. In addition to his clear technical merits, this was something that clearly convinced us to make him a member of the R Foundation and R Core later that year.

Over the next decade, Tomáš quietly became part of R's infrastructure. We managed to secure funding from the _R Foundation_ and the _R Consortium_, recently supplemented by an investment from the _Sovereign Tech Fund_, so that he could work full-time on R on a consultancy basis.

## Contributions to R

Tomáš worked on so many aspects of R that probably no single member of
R Core has a full in-depth view of the things he did. Here is a small selection:
        
- **The JIT compiler.** Tomáš did the painstaking work of making the bytecode compiler safe to enable by default. He debugged the packages that broke, pushed their maintainers to fix them, and benchmarked every change.

- **rchk.** He built a static analysis tool using `LLVM` that detects memory protection errors (`PROTECT` bugs) in R's C code. This class of bug had plagued R for years, causing rare, hard-to-reproduce crashes. Tomáš's tool made them findable, and he ran it against CRAN as part of regular infrastructure checks.

- **The Windows port.** Maintaining R on Windows — the compiler toolchains (`Rtools`), cross-compilation, console input handling for multi-byte characters, DLL loading, graphics device crashes, and decades of platform-specific workarounds.

- **The UCRT/UTF-8 transition.**  Migrating R on Windows from the legacy MSVCRT to the Universal C Runtime and enabling UTF-8 as the native encoding. This was years of work — building new toolchains, testing against thousands of CRAN and Bioconductor packages, coordinating with package maintainers.

- **ARM64 support on Windows.** He built the cross-compilation toolchain, discovered and fixed a subtle NaN-handling bug in ARM processors, and produced the first R installers for Windows on ARM64.

- **The parallel package.** He worked on the core of the parallel package, fixed socket handling for clusters, and debugged intermittent failures — TCP half-open connections, timeout enforcement on Linux.

- **mfuzz.** (unfinished) He worked on a toolset to help with issues of numerical precision leading to results differing between platforms, and even between operating system versions on the same platform.

- **Bug fixing.** He was responsible for fixing a wide range of issues: complex number NaN propagation, parser error context for multi-byte characters, encoding in the symbol table, timezone handling, graphics window crashes, connection handling, memory profiling output.
    
Tomáš regularly blogged about his work in R, starting in March 2018, after he created the [R Blog](https://blog.r-project.org/) site. He wrote blog posts on topics from ARM NaN handling to iconv issues on macOS. His blogs convey the many ways in which he was involved in advancing R and the R project. 

## Personal

In spite of the somewhat precarious work conditions associated with short-term contracts and grants, Tomáš was quite satisfied with his position. It enabled him to work full time on issues that he found challenging, meaningful, and fulfilling, and which had consequences for millions of users worldwide.

Jan Vitek heard him say many times that *Working on R is my dream job*. Tomáš had no love for the publishing games of academia and their associated politics and did not want to sell himself to a corporation. For him, R was the closest thing to doing good deeds.

Reflecting on his first year of full-time work on R, Tomáš wrote: "I've enjoyed the last year working on R, I believe it is a useful work and it is fun to do — the bug hunting that takes most of the time is surprisingly intellectually challenging work, and seeing that things get into the real 'product' that perhaps millions of people use is rewarding."

Tomáš Kalibera was a quiet man, methodical and tireless, who did important work. We shall miss him so much.


_The R Core Team and Jan Vitek_
