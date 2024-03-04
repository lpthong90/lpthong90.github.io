---
layout: lib
logo_url: "/assets/images/projects/async-iterator/thumbnail.png"
title:  async-iterator - Easy way to use async iterator without take care about asyncio’s TaskGroup
repo_name: async-iterator
repo_url: https://github.com/lpthong90/async-iterator
categories: Lib Asyncronous Python 
category_classes: lib asyncronous python
excerpt_separator: <!--more-->
# from_date:   2023-05-02
# to_date:   2023-05-04
---

<p align="center">
    <a href="/libs/099992-async-iterator.html">
        <img class="project-thumnail-small" src="/assets/images/projects/async-iterator/thumbnail.png" alt="Async Iterator">
    </a>
</p>
<p align="center">
    <em>Easy way to use async iterator without take care about asyncio’s TaskGroup</em>
</p>
<p align="center">
    <a href="https://github.com/lpthong90/async-iterator/actions?query=workflow%3ATest" target="_blank">
        <img src="https://github.com/lpthong90/async-iterator/workflows/Test/badge.svg" alt="Test">
    </a>
    <a href="https://github.com/lpthong90/async-iterator/actions?query=workflow%3APublish" target="_blank">
        <img src="https://github.com/lpthong90/async-iterator/workflows/Publish/badge.svg" alt="Publish">
    </a>
    <a href="https://coverage-badge.samuelcolvin.workers.dev/redirect/lpthong90/async-iterator" target="_blank">
        <img src="https://coverage-badge.samuelcolvin.workers.dev/lpthong90/async-iterator.svg" alt="Coverage">
    </a>
    <a href="https://pypi.org/project/async-iterator" target="_blank">
        <img src="https://img.shields.io/pypi/v/async-iterator?color=%2334D058&label=pypi%20package" alt="Package version">
    </a>
    <a href="https://pypi.org/project/async-iterator" target="_blank">
        <img alt="Downloads" src="https://img.shields.io/pypi/dm/async-iterator?color=%2334D058" />
    </a>
</p>

<p align="center">
    <img alt="PyPI - Python Version" src="https://img.shields.io/pypi/pyversions/async-iterator">
</p>

<!--more-->

---

**Documentation**: <a href="https://async-iterator.lpthong90.dev" target="_blank">https://async-iterator.lpthong90.dev</a>

**Source  Code**: <a href="https://github.com/lpthong90/async-iterator" target="_blank">https://github.com/lpthong90/async-iterator</a>

---

The package helps to use async iterator without take care about asyncio's taskgroup.

## Installation
<div id="termynal" class="termy" data-termynal>
    <span data-ty="input">pip install async-iterator</span>
    <span data-ty="progress"></span>
    <span data-ty>Successfully installed async-iterator</span>
</div>

## Basic Usage

<div class="highlight"><pre><span></span><code><span class="kn">import</span> <span class="nn">asyncio</span>
<span class="kn">import</span> <span class="nn">time</span>

<span class="kn">from</span> <span class="nn">async_iterator</span> <span class="kn">import</span> <span class="nb">aiter</span><span class="p">,</span> <span class="n">siter</span>

<span class="n">inputs</span> <span class="o">=</span> <span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="mi">3</span><span class="p">]</span>


<span class="k">async</span> <span class="k">def</span> <span class="nf">afunc</span><span class="p">(</span><span class="n">it</span><span class="p">:</span> <span class="nb">int</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
    <span class="k">await</span> <span class="n">asyncio</span><span class="o">.</span><span class="n">sleep</span><span class="p">(</span><span class="mi">2</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">it</span> <span class="o">+</span> <span class="mi">1</span>


<span class="k">def</span> <span class="nf">sfunc</span><span class="p">(</span><span class="n">it</span><span class="p">:</span> <span class="nb">int</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
    <span class="n">time</span><span class="o">.</span><span class="n">sleep</span><span class="p">(</span><span class="mi">2</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">it</span> <span class="o">+</span> <span class="mi">1</span>


<span class="k">async</span> <span class="k">def</span> <span class="nf">amain</span><span class="p">():</span>
    <span class="k">return</span> <span class="k">await</span> <span class="nb">aiter</span><span class="p">(</span><span class="n">afunc</span><span class="p">)(</span><span class="n">inputs</span><span class="p">)</span>


<span class="k">def</span> <span class="nf">smain</span><span class="p">():</span>
    <span class="k">return</span> <span class="n">siter</span><span class="p">(</span><span class="n">sfunc</span><span class="p">)(</span><span class="n">inputs</span><span class="p">)</span>


<span class="k">if</span> <span class="vm">__name__</span> <span class="o">==</span> <span class="s2">"__main__"</span><span class="p">:</span>
    <span class="nb">format</span> <span class="o">=</span> <span class="s2">"%Y-%m-</span><span class="si">%d</span><span class="s2"> %H:%M:%S"</span>

    <span class="nb">print</span><span class="p">(</span><span class="n">time</span><span class="o">.</span><span class="n">strftime</span><span class="p">(</span><span class="nb">format</span><span class="p">))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"async"</span><span class="p">,</span> <span class="n">asyncio</span><span class="o">.</span><span class="n">run</span><span class="p">(</span><span class="n">amain</span><span class="p">()))</span>  <span class="c1"># it takes ~2 seconds</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">time</span><span class="o">.</span><span class="n">strftime</span><span class="p">(</span><span class="nb">format</span><span class="p">))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"sync"</span><span class="p">,</span> <span class="n">smain</span><span class="p">())</span>  <span class="c1"># it takes ~6 seconds</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">time</span><span class="o">.</span><span class="n">strftime</span><span class="p">(</span><span class="nb">format</span><span class="p">))</span>
</code></pre></div>

Output
```
2024-01-06 00:58:54
async [2, 3, 4]
2024-01-06 00:58:56
sync [2, 3, 4]
2024-01-06 00:59:02
```






## License

This project is licensed under the terms of the [MIT license](https://github.com/lpthong90/async-iterator/blob/main/LICENSE).


<script src="{{ "/assets/js/termynal.js" | relative_url }}" data-termynal-container="#termynal"></script>