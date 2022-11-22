# Window Creation

In LGF, creating a window is very simple. There is no need to manage contexts, error handling, etc. All you need to do is input the right configuration options for your needs.

## **Creating the project**

Assuming you have insatlled the LGF CLI, you can create a new project using `lgf new`. It will ask for the project name and copy some files into a new directory. The directory's name will be your project's name.

### **Project structure** -

LGF Projects are divided into three folders:

- **scripts** - this folder is where your game's source code will be stored. Every LGF project must have a `main.lua` file in this directory.

- **build** - this folder is where your game's source code is being built. It also stores important shared library files for LGF.

- **lgf** - this is where LGF Lua source files are kept. This is just a wrapper around the LGF C++ functions.

## **Creating the window**

Create a new Lua source file (main.lua) inside the `scripts` folder.

Insert the following contents:

```lua
require("lgf.lgf") -- Require LGF

local window = LGF.Window.create("Hello LGF!", 1280, 720) -- Create the window
window:sync(60) -- Set the FPS limit

local renderer = LGF.Renderer.new() -- Create the renderer
renderer:changeColorRGB(0, 0, 0) -- Change the renderer's color

while window:active() do -- While the window is open
  renderer:clearScreen() -- Clear the renderer's screen
  renderer:render() -- Render everything

  window:update() -- Poll events
end

window:close() -- Close the window
```

We will go through this file line by line.

So, to create the actual window, we create a new instance of the `Window` object with the provided title, width, and height. The next line sets the FPS limit of the window to 60 frames/s to avoid high CPU/GPU usage. Although, this is completely optional.

The next part is creating a renderer. The renderer controls everything that will be rendered, or drawn to the screen. Examples of this are images, fonts, rectangles, etc. The next line just changes the background color of the window to black, although this line is also optional as the default LGF window color is black.

Now, into the game loop. The next line is simply a while loop that only runs if the window is open. Every frame, we want to clear the renderer's screen. This is useful for moving parts in the renderer (e.g. players). `renderer:render()` draws everything to the screen. This render method should only be called once per frame. This is because rendering to the screen is slow, which is why we draw everything first and then show it to the player.

The next line updates and polls for window events. It controls if the window shoulds stay open or not.

The final line just closes the window once we're done

## **Finally - running the code**

To run an LGF project, simply type in `lgf run`. This will run your game. Enjoy seeing the blank window ;).
