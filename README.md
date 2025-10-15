# EasyASCII                  
```
 ▄▄▄▄▄▄▄▄     ▄▄       ▄▄▄▄   ▄▄▄    ▄▄▄    ▄▄       ▄▄▄▄       ▄▄▄▄    ▄▄▄▄▄▄    ▄▄▄▄▄▄ 
 ██▀▀▀▀▀▀    ████    ▄█▀▀▀▀█   ██▄  ▄██    ████    ▄█▀▀▀▀█    ██▀▀▀▀█   ▀▀██▀▀    ▀▀██▀▀ 
 ██          ████    ██▄        ██▄▄██     ████    ██▄       ██▀          ██        ██   
 ███████    ██  ██    ▀████▄     ▀██▀     ██  ██    ▀████▄   ██           ██        ██   
 ██         ██████        ▀██     ██      ██████        ▀██  ██▄          ██        ██   
 ██▄▄▄▄▄▄  ▄██  ██▄  █▄▄▄▄▄█▀     ██     ▄██  ██▄  █▄▄▄▄▄█▀   ██▄▄▄▄█   ▄▄██▄▄    ▄▄██▄▄ 
 ▀▀▀▀▀▀▀▀  ▀▀    ▀▀   ▀▀▀▀▀       ▀▀     ▀▀    ▀▀   ▀▀▀▀▀       ▀▀▀▀    ▀▀▀▀▀▀    ▀▀▀▀▀▀ 
```

## A comprehensive, single-file, zero-dependency Python library for creating beautiful and functional text-based user interfaces and ASCII art.

[PyPI EasyASCII Link](https://pypi.org/project/easyascii-py/1.4.0/) 
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[EasyASCII Official Website](https://easyascii-py.netlify.app)

### EasyASCII is designed to be incredibly simple to use while providing a powerful set of tools for command-line applications. Whether you need to display data in a clean table, create an eye-catching banner, or show progress for a long-running task, this library has you covered.

---

## ✨ Key Features

* Layout & Structure: Create advanced boxes, styled alerts, tables, multi-column layouts, and horizontal rules.  

* Data Visualization: Generate bar charts, sparklines ( ▂▄▇), and status gauges.  

* Lists & Hierarchies: Display ordered/unordered lists, task checklists, and tree structures.  

* Text & Banners: Render large FIGlet-style banners and apply effects like mirror, wave, staircase, and repeat.  

* ASCII Art & Generators: Display pre-made cat art, bubbles, and generate random mazes.  

* Date & Time: Show the current month's calendar, create timestamps, and display the day of the week as a day_banner.  

* Real-time feedback with progress_bar and an updatable Spinner.  

* Engaging animations like typewriter, scroll, timer, clock, rain, and fireworks.  

* Pure Python: A single file with zero external dependencies.  

* Developer Friendly: Fully type-hinted with extensive docstrings and a flexible API.  

---

## 📦 Installation

Install `easyascii` directly from PyPI:  

``pip install easyascii-py==1.4.0``  

Or update it if you're using an old version of the library:  

``pip install --upgrade easyascii-py``  

---

## 🚀 Getting Started: A 30-Second Tutorial

### Let's create a welcome screen for a command-line tool. It's that simple!

``import easyascii``

#### 1. Start with a big, bold banner

``easyascii.print_banner("MY APP")``

#### 2. Add a timestamped log message

``easyascii.print_timestamp("Application initialized.")``

#### 3. Show a welcome message in a styled alert box

``easyascii.print_alert(``  

``    "Welcome! This app is ready to go.",``  

``    alert_type="success",``  

``    title="STATUS"``  

``)``


#### 4. Display a checklist of startup tasks

``tasks = [``  

``    ("Configuration loaded", True),``  

``    ("Database connected", True),``  

``    ("Ready for input", False)``  

``]``


``easyascii.print_checklist(tasks)``

#### 5. Show some initial data in a table

``servers = [``  

``    {"Server": "Primary DB", "Status": "Online", "Region": "us-east-1"},``  

``    {"Server": "Cache", "Status": "Online", "Region": "us-east-1"},``  

``    {"Server": "Backup DB", "Status": "Offline", "Region": "eu-west-2"},``  

``]``


``easyascii.print_table(servers, style="rounded", align={"Status": "center"})``


---

### OUTPUT:

``#   # #   #        ###  ####  ####``  

``## ##  # #        #   # #   # #   #``  

``# # #   #         ##### ####  ####``  

``#   #   #         #   # #     #``  

``#   #   #         #   # #     #``  


``[2023-11-10 14:30:00] Application initialized.``  


``╭────────────── STATUS ───────────────╮``  

``│ [V] Welcome! This app is ready to   │``  

``│ go.                                 │``  

``╰─────────────────────────────────────╯``  


``[x] Configuration loaded``  

``[x] Database connected``  

``[ ] Ready for input``  


``╭────────────┬─────────┬───────────╮``  

``│ Server     │ Status  │ Region    │``  

``├────────────┼─────────┼───────────┤``  

``│ Primary DB │ Online  │ us-east-1 │``  

``│ Cache      │ Online  │ us-east-1 │``  

``│ Backup DB  │ Offline │ eu-west-2 │``  

``╰────────────┴─────────┴───────────╯``  


---

## 📚 API Reference

This library provides two ways to use most functions:  

- **Core Functions (box(), table())**: Return a formatted string.  
- **print_*** Wrappers (print_box(), print_table()): Print directly to the console.  

---

### Layout & Structure

#### box() / alert()

Create a box or a pre-styled alert.

There are 8 styles for the box: light, heavy, double, rounded, star, hash, plus and dots.

There are 4 types of alert: sucess, info, error and warning.

``easyascii.print_box("A message.", title="Info", style="rounded", align="center")``  

``easyascii.print_alert("Operation failed!", alert_type="error")``  


Output:

``╭────── Info ──────╮``  

``│    A message.    |``  

``╰──────────────────╯``  


``╔════════════════ ERROR ════════════════╗``  

``║         [x] Operation failed!         ║``  

``╚═══════════════════════════════════════╝``  


#### table()

Display a list of dictionaries as a formatted table.

There are 8 styles for the table: light, heavy, double, rounded, star, hash, plus and dots.

``data = [{"ID": 1, "Name": "A"}, {"ID": 2, "Name": "B"}]``  

``easyascii.print_table(data, style="double")``  


Output:

``╔════╦══════╗``  

``║ ID ║ Name ║``  

``╠════╬══════╣``  

``║ 1  ║ A    ║``  

``║ 2  ║ B    ║``  

``╚════╩══════╝``  


#### hr()

Create a horizontal rule, optionally with a title.

``easyascii.print_hr(title="SECTION BREAK", char="=")``  

Output:

``======================= SECTION BREAK ========================``  

#### columns()

Arrange text into multiple columns.

``items = ["Apple", "Banana", "Cherry", "Date", "Fig"]`` 

``easyascii.print_columns(items, num_cols=3, width=40)``  


Output:

``Apple       Cherry      Fig``  

``Banana      Date``  

---

### Data Visualization

#### gauge()

``easyascii.print_gauge(75, 100, label="Disk Usage", length=30)``  

Output:

``Disk Usage: |██████████████████████-----|  75.0%``  

#### sparkline()

``data = [10, 30, 20, 50, 90, 40, 60]``  

``easyascii.print_sparkline(data, height=3)``  


Output:

``    #``

``   ## #``

``#######``


#### bar_chart()

``data = {"Python": 85, "Go": 50, "Rust": 65}``  

``easyascii.print_bar_chart(data, title="Language Popularity", max_bar_length=30)``  


Output:

``Language Popularity``  

``-------------------``  

``Python | ██████████████████████████████ 85``  

``Go     | █████████████████ 50``  

``Rust   | ███████████████████████ 65``  


---

### Lists & Hierarchies

#### listing() / checklist()

``easyascii.print_listing(["Item 1", "Item 2"], ordered=True)``  

``easyascii.print_checklist([("Task A", True), ("Task B", False)])``  


Output:

``1. Item 1`` 

``2. Item 2``  

``[x] Task A``  

``[ ] Task B``  


#### tree()

``fs = {"project": {"src": {"main.py": None}, "README.md": None}}``  

``easyascii.print_tree(fs)``  


Output:

``└── project``  

``    ├── src``  

``    │   └── main.py``  

``    └── README.md``  


---

### Text, Banners & Art

#### banner() / day_banner()

``easyascii.print_banner("DONE")``  

``easyascii.print_day_banner()``  

Output ASCII banner:

``####  ###  #   # #####`` 

``#   # #  # ##  # #``  

``#   # #  # # # # ###``  

``#   # #  # #  ## #``  

``####  ###  #   # #####``  


[NOTE: INSTALL EASYASCII NOW AND SEE THE DAY_BANNER OUTPUT FOR YOURSELF!]


#### bubble(), cat(), maze()

``easyascii.print_bubble("Hello there!")``  

``easyascii.print_maze(width=21, height=7)``  

``easyascii.print_cat()``

Output:

``╭──────────────╮``

``│ Hello there! │``

``╰──────────────╯``

``    ╰  /``

``     \/``

[NOTE: INSTALL EASYASCII AND SEE THE MAZE OUTPUT FOR YOURSELF!]

`` /\_/\``

``( o.o )``

`` >   <``


#### calendar()

``easyascii.print_calendar()``

Output:
```
+---- October 2025 ----+
|                      |
| October 2025         |
| Mo Tu We Th Fr Sa Su |
| 1  2  3  4  5        |
| 6  7  8  9 10 11 12  |
| 13 14 15 16 17 18 19 |
| 20 21 22 23 24 25 26 |
| 27 28 29 30 31       |
|                      |
+----------------------+
```
#### timestamp()

``easyascii.print_timestamp("Process complete.")``  

Output:

``[2023-11-10 14:45:15] Process complete.``  

---

### Dynamic & Animated UI

#### progress_bar()

``import time, easyascii``  

``for i in range(101):``  

``    easyascii.progress_bar(i, 100)``  

``    time.sleep(0.02)``  

[NOTE: INSTALL EASYASCII NOW AND SEE THE OUTPUT FOR YOURSELF!]

#### Spinner

There are 5 styles for the spinner: line, dots, arrow, moon, bounce.

``import time, easyascii``  

``with easyascii.Spinner("Processing...", style="moon") as s:``  

``    time.sleep(2)``  

``    s.update_text("Finalizing...")``  

``    time.sleep(2)``  


Output during execution:

``Finalizing... (  .. )``  [There is animation]

#### typewriter()

``easyascii.typewriter("Hello, world...", delay=0.05)``  

[NOTE: INSTALL EASYASCII NOW AND SEE THE OUTPUT FOR YOURSELF!]

#### timer() / clock()

``easyascii.timer(5)``  

``easyascii.clock()``  

[NOTE: INSTALL EASYASCII NOW AND SEE THE OUTPUT FOR YOURSELF!]

#### scroll(), rain(), fireworks()

``easyascii.scroll("...Long scrolling message...")``  

``easyascii.rain(duration=5)``  

``easyascii.fireworks(duration=5)``  

[NOTE: INSTALL EASYASCII NOW AND SEE THE OUTPUT FOR YOURSELF!]

---

### Showcase

``from easyascii import showcase``  

``showcase()``  

Displays boxes, tables, charts, lists, banners, spinners, and more in sequence.  

---

### Support

- Python 3.6+  
- Zero external dependencies  
- Perfect for interactive terminals, scripts, CLI dashboards, and ASCII art
- Internal dependencies:

shutil;

sys;

time;

threading;

itertools;

from typing: List, Dict, Any, Optional, Union, Tuple, Iterable;

random;

os;

from datetime: datetime;

math;

calendar (as cal_module inside the easyascii source code)

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the issues page or create a PR.

## 📜 License
This project is licensed under the MIT License.
