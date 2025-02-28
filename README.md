CTkTreeview
A modern and customizable TreeView module for CustomTkinter, providing an elegant alternative to the standard Tkinter Treeview widget.

Features
Design integrated with CustomTkinter's visual style
Full support for CustomTkinter's theme system
Multiple columns with customizable widths
Customization of colors, fonts, and styles
Single and double-click events
Hover effect on rows
Integrated vertical scrollbar
Intuitive API similar to the standard Treeview
Installation
pip install ctktreeview
Or install directly from the repository:

pip install git+https://github.com/username/ctktreeview.git
Dependencies
Python 3.7+
CustomTkinter 5.0.0+
Basic Usage
import customtkinter as ctk
from ctktreeview import CTkTreeview

app = ctk.CTk()
app.title("CTkTreeview Demo")
app.geometry("800x500")

# Create TreeView with columns
treeview = CTkTreeview(
    app,
    columns=["name", "age", "position"],
    column_width={"name": 200, "age": 100, "position": 150},
    headings={"name": "Name", "age": "Age", "position": "Position"},
)
treeview.pack(padx=20, pady=20, fill="both", expand=True)

# Add data
treeview.insert("", "end", ["John Smith", 35, "Developer"])
treeview.insert("", "end", ["Mary Johnson", 42, "Manager"])
treeview.insert("", "end", ["Charles Brown", 28, "Designer"])
treeview.insert("", "end", ["Anna Williams", 31, "Analyst"])

app.mainloop()
Customization Options
treeview = CTkTreeview(
    master,
    columns=["col1", "col2"],                # List of columns
    column_width={"col1": 150, "col2": 100}, # Width of each column
    headings={"col1": "Title 1", "col2": "Title 2"}, # Column headings
    height=300,                              # Widget height
    width=500,                               # Widget width
    show_headings=True,                      # Show headings
    heading_font=("Roboto", 12, "bold"),     # Heading font
    item_font=("Roboto", 11, "normal"),      # Item font
    corner_radius=5,                         # Corner radius
    heading_fg_color=None,                   # Heading background color
    heading_text_color=None,                 # Heading text color
    heading_border_color=None,               # Heading border color
    row_fg_color=[None, None],               # Alternating row colors
    row_hover_color=None,                    # Row hover color
    row_text_color=None,                     # Row text color
    row_border_color=None,                   # Row border color
    row_height=30,                           # Height of each row
    double_click_callback=None,              # Double-click callback function
    single_click_callback=None,              # Single-click callback function
)
Main Methods
insert(parent, index, values, tags=None): Inserts a new row
clear(): Removes all rows
get_children(parent=""): Returns the child IDs
item(item_id, option=None, **kw): Gets or sets item properties
set(item_id, column, value): Sets the value of a specific cell
get(item_id, column): Gets the value of a specific cell
delete(item_id): Removes a specific item
Example with Callbacks
def on_item_click(item):
    print(f"Item clicked: {item['values']}")
    
def on_item_double_click(item):
    print(f"Item double-clicked: {item['values']}")

treeview = CTkTreeview(
    app,
    columns=["name", "age"],
    single_click_callback=on_item_click,
    double_click_callback=on_item_double_click
)
Theme Compatibility
CTkTreeview automatically adapts to the current CustomTkinter theme, including light and dark modes.

# Change theme
ctk.set_appearance_mode("dark")  # or "light"
ctk.set_default_color_theme("blue")  # or "green", "dark-blue"
Integration with Other Libraries
CTkTreeview works well with other CustomTkinter libraries and components:

frame = ctk.CTkFrame(app)
frame.pack(fill="both", expand=True, padx=20, pady=20)

# Title with CTkLabel
label = ctk.CTkLabel(frame, text="User List", font=("Roboto", 16, "bold"))
label.pack(pady=10)

# TreeView inside the frame
treeview = CTkTreeview(frame, columns=["name", "age"])
treeview.pack(fill="both", expand=True)
Contributions
Contributions are welcome! Feel free to open issues or submit pull requests.

License
This project is licensed under the MIT License - see the LICENSE file for details.