# Keyboard Events

In LGF, keyboard events are almost identical to mouse events. We call the `poll()` function, and then check if the user either has a key pressed down or a key released. Keyboard events are useful in games that use player controls, have text fields, and a lot more.

Let's get into the code, shall we?

```lua
require("lgf.lgf") -- Require LGF

local window = LGF.Window.create("Hello LGF!", 1280, 720) -- Create the window
window:sync(60) -- Set the FPS limit

local renderer = LGF.Renderer.new() -- Create the renderer
renderer:changeColorRGB(0, 0, 0) -- Change the renderer's color

while window:active() do -- While the window is open
  renderer:clearScreen() -- Clear the renderer's screen
  renderer:render() -- Render everything

  keyboard:poll() -- Poll for keyboard events
  if keyboard:keyup(LGF.Keyboard.Keycode.KEY_A) then -- If the user has pressed the A key
    print("A key has been pressed!") -- Display that the user has pressed the A key
  end

  window:update() -- Poll events
end

window:close() -- Close the window
```

Almost identical to the mouse events. But this time, we use the `keyup()` function. When the user has a key being held down, the "keydown" event will trigger. Once the user has released that key, the "keyup" event will trigger.

When you call either `keyup()` or `keydown()`, you need to supply a key code. The keycodes are very self-explanatory. There is a keycode for almost every key on the keyboard. There are being more added in updates.
