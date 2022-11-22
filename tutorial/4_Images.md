# Drawing Images

Now, it's time for drawing some images. In the `resources/` folder provided, you will see a file named "test-image.png". You can use that image or you can make your own.

## **Loading & Drawing**

Take a look at the following code:

```lua
require("lgf.lgf") -- Require LGF

local window = LGF.Window.create("Hello LGF!", 1280, 720) -- Create the window
window:sync(60) -- Set the FPS limit

local renderer = LGF.Renderer.new() -- Create the renderer
renderer:changeColorRGB(0, 0, 0) -- Change the renderer's color

-- Here we load the image. It's almost identical to loading a rectangle
-- but we provide an image path as well
local img = LGF.Image.load(100, 100, 400, 400, "res/gfx/test-image.png")

while window:active() do -- While the window is open
  renderer:clearScreen() -- Clear the renderer's screen
  img:draw() -- Draws the image!
  renderer:render() -- Render everything

  window:update() -- Poll events
end

window:close() -- Close the window
```

Okay, so we removed the rectangle calls. With images, the first thing we do is to call `LGF.Image.Load()`. We provide the position, size, and the filepath of where we want our image to be loaded at. Then, to draw, we simply call `img:draw()`.

One thing to note is that we need to create images _after_ we create a renderer. This is because, unlike rectangles, the image loader uses the renderer to load an image.
