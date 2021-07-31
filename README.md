# Konko Module System
### What is Konko?
Konko is a module system based on the Kitsu template that allows for beat-based tweens without a gameplay screen, or even a song.

Konko is object oriented. You can create nodes that act as extended actors that can have beat-based tweens appended to them. You can also create a global ready or update function to add beat-based tweens to existing nodes.

## Quick Start
```lua
-- Add a BPM and offset (in seconds).
BPM = 120
OFFSET = 0.12

-- Create a node.
local myNode = Node.new('Quad')

-- Set a ready function to setup our new node.
myNode:SetReady(function(self)
  self:Center()
  self:SetWidth(64, 64)
end)

-- Add a tween.
myNode:AddTween {0, 2, Tweens.inoutquad, 0, 360, 'rotationz'} -- This will rotate our actor on the Z-axis a full spin for 2 beats.
```

If you want to add a beat-based tween to an existing actor, you can do so like this:
```lua
Node.tween {myActor, 4, 4, Tweens.outelastic, -40, 40, 'y'} -- This will move our actor on the Y-axis from -40 pixels to 40 pixels for 4 beats.
```

More functionality is planned as this module system grows with OutFox.
