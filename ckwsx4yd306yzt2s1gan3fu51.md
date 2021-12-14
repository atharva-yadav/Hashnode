## Create a URL Shortener Application using Python Tkinter


We often need to share some links with our friends or anyone, but sometimes those links are very long and are not readable. So we need to shorten that URL to get a clean, minimal look. But how it is, if you could create your own URL Shortener using Python?

Yes, in this article, we will see how to make a URL shortener using a python module called `pyshortners` and Python *Tkinter* for creating a GUI.

**Prerequisites**: [Python GUI — Tkinter](https://docs.python.org/3/library/tk.html)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1638686024946/_2GymIyFN.png)


### Modules Required

For this application, we will need two Python modules, [pyshorteners](https://pyshorteners.readthedocs.io/en/latest/), and [**Tkinter**](https://docs.python.org/3/library/tk.html).




#### **1\. Pyshorteners**

Pyshorteners is a Python library that helps you shorten URLs using the most famous URL Shorteners available.

To install pyshorteners, just grab it directly from PyPI:

`pip install pyshorteners`

#### 2\. Tkinter

Tkinter is a standard library in Python which is used for GUI applications. Tkinter is the native library. You don’t need to install it externally; just import it while you use it, just like any other python module.

### Implementation of URL Shortener using pyshorteners and Tkinter.

When you run your code, you will get such kind of output. Enter any URL in the first row and press the convert button & that’s it, your python code will generate a shortened URL for you.

#### Code

```
from tkinter import *
import pyshorteners
# Function for short URL and set value in textbox
def convert():
    s = pyshorteners.Shortener().tinyurl.short(url.get())
    shorturl.set(s)
root = Tk()
root.title(" URL Shortner")
root.geometry("400x350")
root.resizable(False, False)
root.config(background="#ffffe0")
# Declare variables
url = StringVar()
shorturl = StringVar()
# Design labels
Label(root, text="URL Shortner", bg="#ffffe0", fg="#E74C3C", font="verdana 22 ").place(x=80, y=10)
Label(root, text="-------------------------------------------------", bg="#ffffe0", fg="#E74C3C"
            , font="verdana 12 ").place(x=15, y=50)
# Accepting URL as a Input
Label(root, text="Enter URL Here ", bg="#2C3E50", fg="#EAECEE", font="verdana 10 bold"
            , padx=2, pady=2).place(x=7, y=100)
Entry(root, textvariable=url, font="verdana 12", width=30).place(x=7, y=120)
# Creating button to give a call for convert function
Button(root, text="Convert...", bg="#fdde6c", fg="#000", font="verdana 12 "
        , command=convert, relief=GROOVE).place(x=7, y=180)
# Displaying shortened URL
Label(root, text="Shortened URL - Copy & Paste in browser", bg="#2C3E50", fg="#EAECEE"
            , font="verdana 10 bold", padx=2, pady=2).place(x=7, y=250)
Entry(root, textvariable=shorturl, width=35, font="verdana 12").place(x=7, y=270)
# StatusBar - Only for design purpose
statusvar = StringVar()
statusvar.set("©https://atharvayadav.medium.com/")
Label(root, textvariable=statusvar, relief=GROOVE,  bg="#ffffe0"
            , fg="#2C3E50", width=60).place(x=-1, y=328)
root.mainloop()
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1638686029295/iFKcns4MF.png)



**Note:** This application will only run until you’re connected to the internet. As it needs to fetch APIs; It will not work offline.

### Conclusion:

This is a short overview of, how you can create your URL Shortener using pyshorteners and the Tkinter module.

If you found this helpful, please consider sharing it with other developers who may need this. Please tell us your views, suggestions in below comment box.
