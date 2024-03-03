---
layout: project
logo_url: "/assets/images/projects/py-simple-trees/thumbnail.png"
title:  py-simple-trees
# company: Personal Project
repo_name: py-simple-trees
repo_url: https://github.com/lpthong90/py-simple-trees
categories: Lib Algorithm Python
category_classs: lib algorithm python
excerpt_separator: <!--more-->
# from_date:   2023-05-02
# to_date:   2023-05-04
---

<p align="center">
    <a href="/projects/099989-py-simple-trees.html">
        <img class="project-thumnail" src="/assets/images/projects/py-simple-trees/thumbnail.png" alt="Django ChatGPT">
    </a> 
    <br>
    <em>This package is a implementation collection of tree data structures.</em>
</p>

<p align="center">
    <a href="https://github.com/lpthong90/py-simple-trees/actions?query=workflow%3ATest" target="_blank">
        <img src="https://github.com/lpthong90/py-simple-trees/workflows/Test/badge.svg" alt="Test">
    </a>
    <a href="https://github.com/lpthong90/py-simple-trees/actions?query=workflow%3APublish" target="_blank">
        <img src="https://github.com/lpthong90/py-simple-trees/workflows/Publish/badge.svg" alt="Publish">
    </a>
    <a href="https://coverage-badge.samuelcolvin.workers.dev/redirect/lpthong90/py-simple-trees" target="_blank">
        <img src="https://coverage-badge.samuelcolvin.workers.dev/lpthong90/py-simple-trees.svg" alt="Coverage">
    </a>
    <a href="https://pypi.org/project/py-simple-trees" target="_blank">
        <img src="https://img.shields.io/pypi/v/py-simple-trees?color=%2334D058&label=pypi%20package" alt="Package version">
    </a>
    <a href="https://pypi.org/project/py-simple-trees" target="_blank">
        <img alt="Downloads" src="https://img.shields.io/pypi/dm/py-simple-trees?color=%2334D058" />
    </a>
</p>
<p align="center">
    <img alt="PyPI - Python Version" src="https://img.shields.io/pypi/pyversions/py-simple-trees">
</p>

<!--more-->

---

**Documentation**: <a href="https://lpthong90.dev/py-simple-trees" target="_blank">https://lpthong90.dev/py-simple-trees</a>

**Source  Code**: <a href="https://github.com/lpthong90/py-simple-trees" target="_blank">https://github.com/lpthong90/py-simple-trees</a>

---

This package is a implementation collection of tree data structures.

## Installation
<div id="termynal" class="termy" data-termynal>
    <span data-ty="input">pip install py-simple-trees</span>
    <span data-ty="progress"></span>
    <span data-ty>Successfully installed py-simple-trees</span>
</div>

## Tree Types
- Binary Tree
- Binary Search Tree (BST)
- AVL Tree

## Basic Usage

``` python
from py_simple_trees import AVLTree, AVLNode

if __name__ == "__main__":
    tree = AVLTree()

    tree.insert(AVLNode(1, 1))
    tree.insert(AVLNode(2, 2))
    tree.insert(AVLNode(3, 3))
    tree.insert(AVLNode(4, 4))
    tree.insert(AVLNode(5, 5))
    tree.insert(AVLNode(6, 6))
    tree.insert(AVLNode(7, 7))

    tree.print()
```

Output
```
4 --L--> 2
4 --R--> 6
2 --L--> 1
2 --R--> 3
6 --L--> 5
6 --R--> 7
```






## License

This project is licensed under the terms of the [MIT license](https://github.com/lpthong90/py-simple-trees/blob/main/LICENSE).