# Easy ASCII
## A comprehensive, single-file, zero-dependency Python library for creating beautiful and functional text-based user interfaces and ASCII art.

[PyPI Easy ASCII Link](https://pypi.org/project/easyascii-py/1.1.3/) -
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

### Easy ASCII is designed to be incredibly simple to use while providing a powerful set of tools for command-line applications. Whether you need to display data in a clean table, create an eye-catching banner, or show progress for a long-running task, this library has you covered.

## ✨ Key Features

* 📦 Advanced Boxes: Create boxes with multiple border styles, titles, and text alignment.

* 🔔 Alerts: Display styled info, success, warning, and error messages.

* 📊 Data Tables: Generate perfectly formatted tables from lists of dictionaries with text wrapping.

* 📈 Charts: Create simple horizontal bar charts and compact sparklines (▂▄▇).

* ✅ Checklists: Show the status of tasks with [x] and [ ] boxes.

* 🎚️ Gauges: Display static progress or stats with meter bars.

* 🅰️ FIGlet Banners: Render large ASCII text banners with a built-in font.

* ⏳ Progress Bars & Spinners: Provide dynamic user feedback with updatable text and new styles.

* 🌳 Tree Structures: Visualize hierarchical data like file systems.

* 🏛️ Multi-Column Layouts: Arrange text into clean, evenly spaced columns.

* 📝 Lists & Rules: Create ordered/unordered lists and customizable horizontal rules.

* 🐍 Pure Python: Single file with zero external dependencies.

* 💡 Developer Friendly: Fully type-hinted with extensive docstrings and a flexible API.


## 📦 Installation

Install `easyascii` directly from PyPI:

`pip install easyascii-py==1.1.3`

Or update it if you're using an old version of the library:

`pip install --upgrade easyascii-py`

---

## Quick Start

### 1. Creating Boxes

The ``box`` function creates ASCII text boxes with customizable borders, alignment, padding, and optional titles.

``from easyascii import box, print_box``

``print_box("Hello World!", style="light", title="My Box", align="center", padding=1)``

- ``style``: light, heavy, double, rounded, star, hash, plus, dots  
- ``align``: left, center, right  
- ``padding``: int or (horizontal, vertical)  
- ``title``: optional box title

---

### 2. Pre-styled Alerts

``alert`` creates pre-styled alert messages:

``from easyascii import alert, print_alert``

``print_alert("This is an info message.", alert_type="info")``

``print_alert("Operation successful!", alert_type="success")``

``print_alert("Be careful!", alert_type="warning")``

``print_alert("Something went wrong!", alert_type="error")``

---

### 3. ASCII Tables

``table`` generates tables from lists of dictionaries.

``from easyascii import table, print_table``

``data = [{"ID": 1, "Name": "Python", "Type": "Programming Language"}, {"ID": 2, "Name": "JavaScript", "Type": "Scripting Language"}]``

``print_table(data, style="double", align={"ID": "center", "Name": "left"})``

- ``headers``: optional list of column names  
- ``align``: string or dict per column  
- ``max_col_width``: maximum width per column

---

### 4. ASCII Banners

``banner`` generates large text banners in ASCII style:

``from easyascii import banner, print_banner``

``print_banner("EASY ASCII")``

- Default font is ``SIMPLE_FONT``  
- All characters are converted to uppercase

---

### 5. Gauge / Progress Bar

``from easyascii import gauge, print_gauge``

``print_gauge(75, total=100, label="Progress")``

- ``value``: current value  
- ``total``: maximum value  
- ``length``: bar length  
- ``fill`` / ``background``: characters for fill and background

---

### 6. Sparkline Charts

``from easyascii import sparkline, print_sparkline``

``print_sparkline([1, 5, 2, 8, 3])``

- Automatically normalizes values  
- Uses characters ``▂▃▄▅▆▇█``

---

### 7. Bar Charts

``from easyascii import bar_chart, print_bar_chart``

``data = {"Python": 75, "JavaScript": 50, "C++": 25}``

``print_bar_chart(data, max_bar_length=30, title="Languages")``

- ``max_bar_length``: max bar length  
- ``fill``: character for bar fill  
- ``title``: optional title

---

### 8. Horizontal Rules

``from easyascii import hr, print_hr``

``print_hr(char="=", title="SECTION")``

- ``width``: line width (default terminal width)  
- ``char``: line character  
- ``title``: optional centered title

---

### 9. Lists & Checklists

- Ordered or unordered lists:

``from easyascii import listing, print_listing``

``print_listing(["Item 1", "Item 2", "Item 3"], ordered=True)``

- Checklists with status:

``from easyascii import checklist, print_checklist``

``tasks = [("Buy milk", True), ("Send email", False)]``

``print_checklist(tasks)``

---

### 10. Columns

``from easyascii import columns, print_columns``

``texts = ["Column 1 content", "Column 2 content", "Column 3 content"]``

``print_columns(texts, num_cols=3)``

- ``num_cols``: number of columns  
- ``width``: total width  
- ``spacing``: space between columns

---

### 11. Tree Structures

``from easyascii import tree, print_tree``

``data = {"Root": {"Branch1": {"Leaf1": None, "Leaf2": None}, "Branch2": {"Leaf3": None}}}``

``print_tree(data)``

- Accepts nested dictionaries  
- Generates ASCII tree-like visualization

---

### 12. Dynamic Progress Bar

``from easyascii import progress_bar``
``import time``

``for i in range(101):``  
``    progress_bar(i, 100, prefix="Loading")``  
``    time.sleep(0.05)``

- Updates in real-time  
- ``prefix`` and ``suffix`` optional

---

### 13. Loading Spinner

``from easyascii import Spinner``
``import time``

``with Spinner("Processing...", style="dots") as s:``  
``    time.sleep(2)``  
``    s.update_text("Almost done...")``  
``    time.sleep(2)``

- Styles: line, dots, arrow, box, moon, bounce  
- Allows dynamic text updates

---

## Convenience Print Wrappers

For all main functions, there is a direct print wrapper:

- ``print_box``
  
- ``print_alert``
  
- ``print_table``
  
- ``print_banner``
  
- ``print_gauge``
  
- ``print_sparkline``
  
- ``print_bar_chart``
  
- ``print_hr``
  
- ``print_listing``
  
- ``print_checklist``
  
- ``print_columns``
  
- ``print_tree``
  

---

## Showcase

Run a full demo:

``from easyascii import showcase``

``showcase()``

Displays boxes, tables, charts, lists, banners, spinners, and more in sequence.

---

## Support

- Python 3.6+  
- Zero external dependencies  
- Perfect for interactive terminals, scripts, CLI dashboards, and ASCII art

