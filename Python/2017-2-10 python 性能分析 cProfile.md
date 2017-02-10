---
title: 2017-2-10 python 性能分析 cProfile
tags: python, cProfile,
grammar_cjkRuby: true
---

####  Python标准库中提供了三种用来分析程序性能的模块，分别是cProfile, profile和hotshot，另外还有一个辅助模块stats。这些模块提供了对Python程序的确定性分析功能，同时也提供了相应的报表生成工具，方便用户快速地检查和分析结果。 这三个性能分析模块的介绍如下： 

> cProfile：基于lsprof的用C语言实现的扩展应用，运行开销比较合理，适合分析运行时间较长的程序，推荐使用这个模块； 

> profile：纯Python实现的性能分析模块，接口和cProfile一致。但在分析程序时增加了很大的运行开销。不过，如果你想扩展profiler的功能，可以通过继承这个模块实现； 

> hotshot：一个试验性的C模块，减少了性能分析时的运行开销，但是需要更长的数据后处理的次数。目前这个模块不再被维护，有可能在新版本中被弃用。 由于hotshot基本不再使用，而profile和cProfile的用法基本一致，所以下面就只介绍一下cProfile的用法。

