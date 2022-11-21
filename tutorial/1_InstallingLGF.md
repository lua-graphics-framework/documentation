# Installing LGF

Well, you decided to commit to learning LGF. Your first step to master LGF is to install it, of course.

## **Installation Guide - Windows**

Now, just a heads up: Microsoft Defender will most likely complain about LGF if you haven't disabled it. The easiest way to install LGF is to use the LGF CLI. The CLI comes with an auto updater, project creation tools, and the ability to run your project very easily. To install it, go to https://github.com/lua-graphics-framework/cli/releases and download the latest release for Windows.

The second thing you need to do is create a `.lgf` folder in C:\Users\\[user]. Move the .exe file into that newly created folder. Next, rename the .exe file to `lgf.exe`. The finaly thing you need to do is to add that folder to your `PATH` environment variable.

Finally, open up anew powershell (or Windows Terminal) window and execute the following command:

`lgf update`

This command will install LGF and its dependencies into the .lgf folder. If Microsoft Defender complains, you could exclude it.

## **Conclusion**

There you go, you now have LGF installed on your system. The next step is to create a project with a blank LGF window.
