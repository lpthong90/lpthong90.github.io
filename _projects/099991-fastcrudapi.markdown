---
layout: project
logo_url: "/assets/images/projects/fastcrudapi-logo.png"
title:  fastcrudapi - Super easy to generate CRUD api routes for FastAPI
# company: Personal Project
repo_name: fastcrudapi
repo_url: https://github.com/lpthong90/fastcrudapi
categories: Lib FastAPI Python 
excerpt_separator: <!--more-->
# from_date:   2023-05-02
# to_date:   2023-05-04
---

<p align="center">
    <a class="project-thumnail-small" href="https://fastcrudapi.lpthong90.dev"><img src="https://fastcrudapi.lpthong90.dev/img/logo.png" alt="FastCRUDAPI"></a>
</p>
<p align="center">
    <em>Super easy to generate CRUD api routes for FastAPI.</em>
</p>
<p align="center">
    <a href="https://github.com/lpthong90/fastcrudapi/actions?query=workflow%3ATest" target="_blank">
        <img src="https://github.com/lpthong90/fastcrudapi/workflows/Test/badge.svg" alt="Test">
    </a>
    <a href="https://github.com/lpthong90/fastcrudapi/actions?query=workflow%3APublish" target="_blank">
        <img src="https://github.com/lpthong90/fastcrudapi/workflows/Publish/badge.svg" alt="Publish">
    </a>
    <a href="https://coverage-badge.samuelcolvin.workers.dev/redirect/lpthong90/fastcrudapi" target="_blank">
        <img src="https://coverage-badge.samuelcolvin.workers.dev/lpthong90/fastcrudapi.svg" alt="Coverage">
    </a>
    <a href="https://pypi.org/project/fastcrudapi" target="_blank">
        <img src="https://img.shields.io/pypi/v/fastcrudapi?color=%2334D058&label=pypi%20package" alt="Package version">
    </a>
    <a href="https://pypi.org/project/fastcrudapi" target="_blank">
        <img alt="Downloads" src="https://img.shields.io/pypi/dm/fastcrudapi?color=%2334D058" />
    </a>
</p>

<p align="center">
    <img alt="PyPI - Python Version" src="https://img.shields.io/pypi/pyversions/fastcrudapi">
</p>

<!--more-->

---

**Documentation**: <a href="https://fastcrudapi.lpthong90.dev" target="_blank">https://fastcrudapi.lpthong90.dev</a>

**Source  Code**: <a href="https://github.com/lpthong90/fastcrudapi" target="_blank">https://github.com/lpthong90/fastcrudapi</a>

---

The package helps to generate CRUD APIs for models based on FastAPI.

## Installation
<div id="termynal" class="termy" data-termynal>
    <span data-ty="input">pip install fastcrudapi</span>
    <span data-ty="progress"></span>
    <span data-ty>Successfully installed fastcrudapi</span>
</div>

## Basic Usage

<div class="highlight"><pre><span></span><code><span class="kn">from</span> <span class="nn">fastapi</span> <span class="kn">import</span> <span class="n">FastAPI</span>
<span class="kn">from</span> <span class="nn">fastcrudapi</span> <span class="kn">import</span> <span class="n">CrudApiRouter</span>
<span class="kn">from</span> <span class="nn">pydantic</span> <span class="kn">import</span> <span class="n">BaseModel</span>

<span class="n">app</span> <span class="o">=</span> <span class="n">FastAPI</span><span class="p">()</span>


<span class="k">class</span> <span class="nc">Book</span><span class="p">(</span><span class="n">BaseModel</span><span class="p">):</span>
    <span class="nb">id</span><span class="p">:</span> <span class="nb">int</span>
    <span class="n">name</span><span class="p">:</span> <span class="nb">str</span>


<span class="n">book_router</span> <span class="o">=</span> <span class="n">CrudApiRouter</span><span class="p">(</span>
    <span class="n">prefix</span><span class="o">=</span><span class="s2">"/books"</span><span class="p">,</span>
    <span class="n">schema</span><span class="o">=</span><span class="n">Book</span><span class="p">,</span>
<span class="p">)</span>
<span class="n">app</span><span class="o">.</span><span class="n">include_router</span><span class="p">(</span><span class="n">book_router</span><span class="p">)</span>
</code></pre></div>

## OpenAPI

<p align="center">
    <img src="https://fastcrudapi.lpthong90.dev/img/openapi.png" alt="OpenAPI">
</p>

<br>

## License

This project is licensed under the terms of the [MIT license](https://github.com/lpthong90/fastcrudapi/blob/main/LICENSE).
