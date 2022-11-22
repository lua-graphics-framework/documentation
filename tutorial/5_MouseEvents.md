# Mouse Events

If you want to make a game (or really anything), you need some sort of mouse input. LGF provides ways of checking if the mouse has been pressed or being held down for each of the three mouse buttons. LGF's mouse button IDs are from 1-3.

**1** is the left mouse button. It is usually the primary mouse button.

**2** is the middle mouse button. It is the scroll wheel on the mouse pressed down.

**3** is the right mouse button. Whenever you "right click," this is the button.

Enough explaining. Let's get to the code, shall we?

```lua
require("lgf.lgf") -- Require LGF

local window = LGF.Window.create("Hello LGF!", 1280, 720) -- Create the window
window:sync(60) -- Set the FPS limit

local renderer = LGF.Renderer.new() -- Create the renderer
renderer:changeColorRGB(0, 0, 0) -- Change the renderer's color

while window:active() do -- While the window is open
  -- Here we check every frame for mouse events
  -- This must be here to use mouse events.
  LGF.Mouse:poll()

  -- This code checks to see if the left mouse button (ID 1) is pressed, and
  -- if it is, let us know
  if LGF.Mouse:mouseButtonUp(1) == true then
    print("Left mouse button pressed.")
  end

  -- Same thing here...
  if LGF.Mouse:mouseButtonUp(2) == true then
    print("Middle mouse button pressed.")
  end

  -- ...and here..
  if LGF.Mouse:mouseButtonUp(3) == true then
    print("Right mouse button pressed.")
  end

  renderer:clearScreen() -- Clear the renderer's screen
  renderer:render() -- Render everything

  window:update() -- Poll events
end

window:close() -- Close the window
```

The LGF call "poll" mouse events is basically LGF's one way switch to activate mouse events. Once they are being polled, you can check for these events.

Next up, we will talk about keyboard events.
