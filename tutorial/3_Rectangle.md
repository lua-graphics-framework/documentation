# Creating a Rectangle

In LGF, creating a rectangle is very simple.

## **Rendering a Rectangle**

To draw a rectangle, we must first create it. Here is some code that we will use for this tutorial:

```lua
require("lgf.lgf") -- Require LGF

local window = LGF.Window.create("Hello LGF!", 1280, 720) -- Create the window
window:sync(60) -- Set the FPS limit

local renderer = LGF.Renderer.new() -- Create the renderer
renderer:changeColorRGB(0, 0, 0) -- Change the renderer's color

-- Here, we create a rectangle. We specify the x position, y position,
-- width, and height.
local rectangle = LGF.Rectangle.create(10, 10, 100, 100)

while window:active() do -- While the window is open
  renderer:clearScreen() -- Clear the renderer's screen

  -- Here, we need to set the color of the rectangle. In this example, we are
  -- setting it to white.
  rectangle:changeColor(255, 255, 255)
  rectangle:draw() -- The magic call!

  renderer:render() -- Render everything
  window:update() -- Poll events
end

window:close() -- Close the window
```

Most of this code you already recognize. The code we are interested are the rectangle calls. When we create a rectangle, we specify its position and size. You do not _have_ to create the rectangle after the renderer is created; as it doesn't use the renderer for its creation.

Into the game loop again. We first set the rectangle's color to white. For now, we need to do this for every frame. Then... the magic drawing call. This is when the rectangle is actually rendered.

There you go! That is how you draw a rectangle in LGF.
