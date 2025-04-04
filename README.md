# Orderbook Implementation

This project is a C++ implementation of an Orderbook system used in financial markets to manage buy and sell orders. It supports order matching, order modification, and order cancellation with various order types.

---

## 📁 Files
- `orderbook.cpp` - The main implementation of the orderbook system.

---

## ⚙️ Features
- **Order Matching:** Matches buy and sell orders based on price priority.
- **Order Types:** 
  - `GoodTillCancel`: Stays active until explicitly canceled.
  - `FillAndKill`: Either fully executed immediately or canceled if not matched.
- **Order Modification:** Modify existing orders while maintaining their priority.
- **Order Cancellation:** Remove orders by ID.
- **Orderbook Level Information:** Retrieve aggregated order data for bids and asks.

---

## 📌 Classes
- **`Orderbook`**: Manages the overall order matching, addition, modification, and cancellation.
- **`Order`**: Represents an individual buy or sell order.
- **`Trade`**: Represents a successful match between a buy and a sell order.
- **`OrderModify`**: Handles modifications of existing orders.
- **`OrderbookLevelInfos`**: Stores aggregated information about current bid and ask levels.

---

## 🚀 Usage Example

```cpp
#include <iostream>
#include "orderbook.h"

int main(){
    Orderbook orderbook;

    const OrderId orderId = 1;
    orderbook.AddOrder(std::make_shared<Order>(OrderType::GoodTillCancel, orderId, Side::Buy, 100, 10));
    std::cout << orderbook.Size() << std::endl;
    
    orderbook.CancelOrder(orderId);
    std::cout << orderbook.Size() << std::endl;
    return 0;
}
```
## Output

1
0

## 📦 Dependencies
Standard C++ Libraries (<iostream>, <map>, <list>, etc.)

## Compilation
```bash
g++ -std=c++20 -o orderbook orderbook.cpp
```

