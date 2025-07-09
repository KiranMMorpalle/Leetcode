# Leetcode
---

# 🧠 LeetCode Master Tracker

Welcome to my LeetCode journey! This repo tracks all problems I've solved across topics, languages, and curated sheets.  
I'm grinding through challenges to level up for top tech interviews 💼 (FAANG, Product-based).

---

## 📊 Stats Overview

- 🔢 **Total Solved:** 135+  
- 📆 **Goal:** 500 by [Target Date]  
- 🚀 **Sheets Covered:** Blind 75, TUF Sheet, NeetCode 150

---

## 🗂️ Filter by Language

> 🟦 = C++ | 🟨 = JavaScript | 🟩 = Python

| # | Title | Difficulty | Sheet | Lang | Solution |
|--:|:------|:-----------:|:-----:|:----:|:--------:|
| 1 | Two Sum | 🟢 Easy | Blind 75 | 🟦🟨🟩 | [Code](./solutions/Array/1-two-sum.cpp) |
| 121 | Best Time to Buy/Sell Stock | 🟢 Easy | TUF Sheet | 🟨🟩 | [Code](./solutions/Array/121-buy-sell-stock.py) |
| 3 | Longest Substring w/o Repeat | 🟡 Medium | Blind 75 | 🟦🟩 | [Code](./solutions/SlidingWindow/3-longest-substring.cpp) |
| 70 | Climbing Stairs | 🟢 Easy | NeetCode 150 | 🟨🟩 | [Code](./solutions/DP/70-climbing-stairs.js) |
| 206 | Reverse Linked List | 🟢 Easy | Blind 75 | 🟦🟩 | [Code](./solutions/LinkedList/206-reverse-linked-list.cpp) |

---

## 🧵 Folder Structure
```
solutions/
├── Array/
│ ├── 1-two-sum.cpp
│ └── 121-buy-sell-stock.py
├── SlidingWindow/
│ └── 3-longest-substring.cpp
├── DP/
│ └── 70-climbing-stairs.js
├── LinkedList/
│ └── 206-reverse-linked-list.cpp

```


---

## 🗃️ Tags Explained

| Tag | Meaning |
|-----|---------|
| 🟢 Easy / 🟡 Medium / 🔴 Hard | Difficulty level |
| Blind 75 | Most frequently asked 75 problems |
| TUF Sheet | Striver’s 450 DSA Sheet |
| NeetCode 150 | Curated set for interviews |
| ✅ Solved | Tracked in the table above |

---

## 🛠️ Tech Stack

- 👨‍💻 Language: C++, Python, JavaScript  
- 🔍 IDE: VS Code  
- 📘 Platform: [LeetCode](https://leetcode.com/)  
- 📁 Tracker: This repo (auto-update ready)

---

## 🔄 Auto-Update Script (Optional)

> Save this as `update.py` and run it to auto-generate the Markdown table.

```python
import os

def generate_table():
    topics = ['Array', 'DP', 'LinkedList', 'SlidingWindow']
    exts = {'.cpp': '🟦', '.js': '🟨', '.py': '🟩'}
    rows = []

    for topic in topics:
        path = f'./solutions/{topic}'
        if not os.path.isdir(path):
            continue
        for file in os.listdir(path):
            name, ext = os.path.splitext(file)
            if ext in exts:
                lc_number = name.split('-')[0]
                title = ' '.join(name.split('-')[1:])
                lang = exts[ext]
                link = f'[Code]({path}/{file})'
                rows.append((int(lc_number), title.title(), "🟢", "TUF Sheet", lang, link))

    rows.sort()
    for row in rows:
        print(f'| {row[0]} | {row[1]} | {row[2]} | {row[3]} | {row[4]} | {row[5]} |')

generate_table()
