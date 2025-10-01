# Easy ASCII
## A comprehensive, single-file, zero-dependency Python library for creating beautiful and functional text-based user interfaces and ASCII art.

[PyPI Easy ASCII Link](https://pypi.org/project/easyascii-py/1.4.0/) -
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

### Easy ASCII is designed to be incredibly simple to use while providing a powerful set of tools for command-line applications. Whether you need to display data in a clean table, create an eye-catching banner, or show progress for a long-running task, this library has you covered.

##✨ Key Features

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


## 📦 Installation

Install `easyascii` directly from PyPI:

`pip install easyascii-py==1.4.0`

Or update it if you're using an old version of the library:

`pip install --upgrade easyascii-py`

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

    "Welcome! This app is ready to go.",
    
    alert_type="success",
    
    title="STATUS"
    
``)``

#### 4. Display a checklist of startup tasks
``tasks = [``

    ("Configuration loaded", True),
    
    ("Database connected", True),
    
    ("Ready for input", False)
    
``]``
``easyascii.print_checklist(tasks)``

#### 5. Show some initial data in a table
``servers = [``

    {"Server": "Primary DB", "Status": "Online", "Region": "us-east-1"},
    
    {"Server": "Cache", "Status": "Online", "Region": "us-east-1"},
    
    {"Server": "Backup DB", "Status": "Offline", "Region": "eu-west-2"},
    
``]``
``easyascii.print_table(servers, style="rounded", align={"Status": "center"})``


OUTPUT:


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


📚 API Reference
This library provides two ways to use most functions:
Core Functions (box(), table()): Return a formatted string, letting you store or manipulate it.
print_* Wrappers (print_box(), print_table()): Print the result directly to the console. They accept the same arguments.
Layout & Structure
box() / alert()
Create a box or a pre-styled alert.
code
Python
easyascii.print_box("A message.", title="Info", style="rounded", align="center")
easyascii.print_alert("Operation failed!", alert_type="error")
code
Code
╭────── Info ──────╮
│     A message.     │
╰────────────────────╯
╔════════════════ ERROR ════════════════╗
║ [x] Operation failed!                  ║
╚════════════════════════════════════════╝
table()
Display a list of dictionaries as a formatted table.
code
Python
data = [{"ID": 1, "Name": "A"}, {"ID": 2, "Name": "B"}]
easyascii.print_table(data, style="double")
code
Code
╔════╦══════╗
║ ID ║ Name ║
╠════╬══════╣
║ 1  ║ A    ║
║ 2  ║ B    ║
╚════╩══════╝
hr()
Create a horizontal rule, optionally with a title.
code
Python
easyascii.print_hr(title="SECTION BREAK", char="=")
code
Code
======================= SECTION BREAK ========================
columns()
Arrange text into multiple columns.
code
Python
items = ["Apple", "Banana", "Cherry", "Date", "Fig"]
easyascii.print_columns(items, num_cols=3, width=40)
code
Code
Apple       Cherry      Fig
Banana      Date
Data Visualization
gauge()
Display a static progress/meter bar.
code
Python
easyascii.print_gauge(75, 100, label="Disk Usage", length=30)

Disk Usage: |██████████████████████-----|  75.0%
sparkline()
Generate a compact, multi-line chart from a list of numbers.

data = [10, 30, 20, 50, 90, 40, 60]
easyascii.print_sparkline(data, height=3)

#
# # # # # # #
# # # # # # #
bar_chart()
Create a horizontal bar chart from a dictionary.

data = {"Python": 85, "Go": 50, "Rust": 65}
easyascii.print_bar_chart(data, title="Language Popularity", max_bar_length=30)

Language Popularity
-------------------
Python | ██████████████████████████████ 85
    Go | █████████████████ 50
  Rust | ███████████████████████ 65
Lists & Hierarchies
listing() / checklist()
Create standard lists or checklists for tasks.

easyascii.print_listing(["Item 1", "Item 2"], ordered=True)

easyascii.print_checklist([("Task A", True), ("Task B", False)])

``1. Item 1``

``2. Item 2``

   
``[x] Task A``

``[ ] Task B``


### tree()

Visualize a nested dictionary as a file-system tree.

``fs = {"project": {"src": {"main.py": None}, "README.md": None}}``

``easyascii.print_tree(fs)``


``└── project``

``    ├── src``
    
``    │   └── main.py``
    
``    └── README.md``
    
Text, Banners & Art

banner() / day_banner()

Render large ASCII text. day_banner is a shortcut for the current day.

``easyascii.print_banner("DONE")``
#### On a Tuesday:
``easyascii.print_day_banner()``

``####  ###  #   # #####``

``#   # #  # ##  # #``

``#   # #  # # # # ###``

``#   # #  # #  ## #``

``####  ###  #   # #####``

``##### #   # #####  #### ####   ###  #   #``

``  #   #   # #     #     #   # #   #  # #``

``  #   #   # ###    ###  #   # #####   #``

``  #   #   # #         # #   # #   #   #``

``  #    ###  ##### ####  ####  #   #   #``

bubble(), cat(), maze(), etc.
Generate fun ASCII art and structures.

easyascii.print_bubble("Hello there!")
easyascii.print_maze(width=21, height=7)

╭──────────────╮
│ Hello there! │
╰──╮  ╭──╯
   \/
█████████████████████
  █ █   █ █ █     █ 
█ █ █ ███ █ █ █ █ █ 
█   █   █   █   █   █ 
█ ███ █ █ █ ███ ███ █ 
█     █   █         
█████████████████████
timestamp()
Prepend a formatted timestamp to a message.

easyascii.print_timestamp("Process complete.")

[2023-11-10 14:45:15] Process complete.
Dynamic & Animated UI
Note: These functions are blocking and will run until they complete or are interrupted with Ctrl+C.
progress_bar()
Shows a real-time progress bar. Call this inside a loop.


import time, easyascii
for i in range(101):
    easyascii.progress_bar(i, 100)
    time.sleep(0.02)

Progress: |██████████████████████████████████████████████████| 100.0% Complete
Spinner
A context manager for showing an animated spinner during long operations.
code
Python
import time, easyascii
with easyascii.Spinner("Processing...", style="moon") as s:
    time.sleep(2)
    s.update_text("Finalizing...")
    time.sleep(2)


(During execution)
Finalizing... (  .. )
typewriter()
Prints text to the console one character at a time.

easyascii.typewriter("Hello, world...", delay=0.05)
timer() / clock()
Display a countdown timer or a live-updating clock.

easyascii.timer(5) # Counts down from 5 seconds
easyascii.clock()  # Runs a live clock until stopped
scroll(), rain(), fireworks()
Fun, full-screen animations.

easyascii.scroll("...Long scrolling message...")
easyascii.rain(duration=5)
easyascii.fireworks(duration=5)
Showcase
To see a live demonstration of all library features, simply run:

import easyascii
easyascii.showcase()
🤝 Contributing
Contributions, issues, and feature requests are welcome!
📜 License
This project is licensed under the MIT License.



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

# tomorrow i'm going to format it
