---
layout: project
# logo_url: "/assets/images/projects/rails-messenger-logo.png"
title:  Order Matching Engine
# company: Personal Project
repo_name: python-order-matching-engine
repo_url: https://github.com/lpthong90/python-order-matching-engine
categories: Demo Algorithm Python
excerpt_separator: <!--more-->
# from_date:   2023-05-02
# to_date:   2023-05-04
---

<p align="center">
  <em>A demo project is a simple order matching engine which using double linked list and AVL tree.</em>
</p>
<!--more-->

---

**Source  Code**: <a href="{{ page.repo_url }}" target="_blank">{{ page.repo_url }}</a>

---

## Ideas

Order books involve three primary actions: adding a new order, canceling an existing order, and executing an order. 

When adding a new order, the system searches for the corresponding price level and then either adds the order to an existing level or initializes a new one. 

When canceling an order, the system searches for and removes it from the relevant price level's order list.

When executing an order, the system searches for all orders on the opposite side that match it. If matching orders exist, the system reduces the volume size of the order and retries until no matching orders remain. If an order is only partially filled, a new price level is created for the remaining volume.

Price levels without any related orders are removed to maintain efficiency in the order book.

## Diagrams

<!-- <img src="./images/diagram.png" alt="filter_options"/> -->
<img src="https://github.com/lpthong90/python-order-matching-engine/blob/c12928890d71f5ea45c725217dc739fbbc1a1b80/images/diagram.png" alt="OrderMatchingEngineDiagram">

## Models

``` python
class Order:
    def __init__(self, id: ID_TYPE, price: float, volume: float, side: SideType):
        self.id: ID_TYPE = id
        self.price: float = price
        self.volume: float = volume
        self.origin_volume = volume
        self.side: SideType = side  # 'BUY' 'SELL'

        self.price_level: Optional[PriceLevel] = None

class PriceLevel:
    def __init__(self, price: float):
        self.price: float = price
        self.total_volume: float = 0
        self.orders: LinkedList[int, Order] = LinkedList[int, Order]()

class OrderBook:
    def __init__(self):
        self.bids_tree: AdvancedAVLTree[float, PriceLevel] = AdvancedAVLTree[float, PriceLevel]()
        self.asks_tree: AdvancedAVLTree[float, PriceLevel] = AdvancedAVLTree[float, PriceLevel]()
        self.best_bid_price_level: Optional[PriceLevel] = None
        self.best_ask_price_level: Optional[PriceLevel] = None

        self.price_levels: Dict[float, PriceLevel] = {}

class MatchingEngine:
    def __init__(self, order_book: Optional[OrderBook]):
        self.order_book = order_book or OrderBook()

        self.orders: Dict[int, Order] = {}
        self.filled_orders: Dict[int, Order] = {}
```

## Complexity

Assume with m is number of price levels, n is number orders in each price level, l is number of matched price levels; then we have:

- Add new order:
  - O(log(m)) if related price level isn't existed
  - O(1) if otherwise
- Cancel order:
  - O(log(m)) if related price level is removed
  - O(1) if otherwise
- Execute order:
  - O(n * l * log(m))

## References

<a href="https://web.archive.org/web/20110219163448/http://howtohft.wordpress.com/2011/02/15/how-to-build-a-fast-limit-order-book/" target="_blank">1. How to build a fast limit order book </a>
