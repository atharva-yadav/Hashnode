## Convert Python Script to .exe File

### Introduction
As a programmer, you might be creating many Python programs per day that are useful in real-world problems. And obviously, you want to share them with your other friends so that they can benefit from it. But the problem is, everyone has no python installed on their machine, so they can’t run python programs on their PC.

So, to overcome this problem, and to run Python scripts without the installation of Python, we will be converting `.py` files to `.exe` files. As we convert to `.exe` format, anyone can run this installer and use your python applications.

If you are interested in how to convert this, keep reading this article, and within a few minutes, you will learn everything you need to know for conversion of `.py` file to a `.exe` file. 

### Convert Python files to .exe files

For doing so, There are two methods:

1.  **Using** [**Pyinstaller**](https://www.pyinstaller.org/) **module:** PyInstaller bundles a Python application and all its dependencies into a single package. Using terminal commands we can use this module.
2.  **Using** [**auto-py-to-exe**](https://pypi.org/project/auto-py-to-exe/) **module:** A .py to .exe converter using a simple graphical interface and PyInstaller in Python. Means it uses pyinstaller at the backend.

Here in this article, we are going to use `[*auto-py-to-exe*](https://pypi.org/project/auto-py-to-exe/)` because, it is beginner-friendly, easy to use, and has a clean GUI.

#### Step 1. **Installation**

Install the library pyinstaller. Type below command in the command prompt.

```
pip install auto-py-to-exe
```

In my case, it is already installed hence it is showing `“Requirement already satisfied:”`

![How to Convert Python Script to .exe File | Create desktop applications](https://cdn.hashnode.com/res/hashnode/image/upload/v1638686034461/eKdNfyVUk.png)

#### Step 2. Using the Application

1.  Once installed, open a terminal in a folder where your python file is present.
2.  After that, type a command `auto-py-to-exe` in a terminal and press enter.

![How to Convert Python Script to .exe File | Create desktop applications type a command auto-py-to-exe in a terminal and press enter.](https://cdn.hashnode.com/res/hashnode/image/upload/v1638686036911/yRtmXzxi6.png)

Type the command ***auto-py-to-exe*** in a terminal and press enter.

**3.** After pressing enter, a GUI for `auto-py-to-exe` will open as shown below. Where you see an option to select a python script from your PC with many other options.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1638686039011/Y4X5zeXno.png)

**4.** Select the Python script you want to convert by pressing the “**Browse**” button. You can also choose the icon for your `.exe` file. *(It should be a .ico file).*

![Select a python script you want to convert](https://cdn.hashnode.com/res/hashnode/image/upload/v1638686041135/ySQ5nqeOd.png)

Select the Python script you want to convert.

After selecting you will see that, `**Current command**` section showing some commands. That is nothing but commands from the pyinstaller. That command will run by `auto-py-to-exe` at the backend. (auto-py-to-exe uses pyinstaller only).

**5.** After selecting all the files press the “**Convert .py to .exe**” button, then the conversion will start.

It will take some time to finish the process depending on the size of the file and how big is your project.

After the processing has been finished, the window will look as below:

![Output (Conversion has completed)](https://cdn.hashnode.com/res/hashnode/image/upload/v1638686043371/Xa44Ydiyb.png)

Output (Conversion has been completed)

#### Step 3. Open the Output folder

You will notice that there is a new folder named “**output**” will be created, as you open it, you will find the `.exe` file having the same name as your python script.

![.exe file having the same name as your python script](https://cdn.hashnode.com/res/hashnode/image/upload/v1638686045631/mRDJiK7WU.png)

.exe file having the same name as your python script

As you double click on it, it will open and you can see the output of the python script through the `.exe` file

![run the .exe file](https://cdn.hashnode.com/res/hashnode/image/upload/v1638686047668/lPcv3KsT0.png)

run the .exe file

### Conclusion

That’s all, now you can convert this output folder into `.zip` format and anyone can run your application even if they don’t have python installed on their machine.

Hope you found this helpful; If yes, please consider sharing it with other developers who may need this. You can also tell us your opinions, suggestions in below comment box.
