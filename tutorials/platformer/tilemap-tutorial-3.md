# Using Tilemaps

## Introduction @unplugged

This tutorial teaches you to customize your tilemaps given already created tiles.

## Step One

Use the ``||tiles:set current tilemap to map ||`` code to start your robot on the start tile and set up the tilemap.

```python
tiles.load_map(tiles.create_map(tilemap(""" """)))
```

## Step Two @showhint

Change the dimensions to 10 x 7. 
~hint Click here to see how 🕵🏽

---

![Make a 10x7 tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/tilemap-customize-tile-1.gif "10x7 Tilemap" )
hint~


## Step Three @showhint

Now click on the "My Tiles" and then click the plus sign.  You may make a custom tile or use one from the gallery. 
~hint Here is how to make a custom startTile 🕵🏽

---

![Make a 10x7 tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/tilemap-customize-tile-2.gif  "10x7 Tilemap" )
hint~
~hint Here is how to make a startTile from the Gallery 🕵🏽

---

![Make a 10x7 tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/tilemap-customize-tile-3.gif  "10x7 Tilemap" )
hint~


You should make as many types of tiles as you would like.  You must make a startTile and a goalTile. Make sure you name them exactly: startTile & goalTile.

## Step Four @showhint

Click the walls tool to create walls around the edge and any walls you want inside your robot's world.  If you choose to make walls in your world make sure they are different from the non-wall tiles.
~hint Here is how to make walls 🕵🏽

---

![Add walls](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/tilemap-customize-3.gif "Add walls" )
hint~


## Step Five

Use the ``||robot:begin screen ||`` code to start your robot on the start tile and set up the tilemap.

```python
robot.begin_screen()
```

## Step Six

Use the ``||robot:move forward||`` code to move the robot. Change the direction the robot is facing with the ``||robot:turn right||`` and ``||robot:turn left||`` code.  Move the robot to the goal tile.

```python
robot.move_forward()
robot.turn_right()
robot.turn_left()
```


```customts
    game.onUpdate(function () {
        if (robot.goalReached()) {
            music.play(music.melodyPlayable(music.powerUp), music.PlaybackMode.UntilDone)
            game.splash("You reached the goal!")
            game.reset()
        }
    })
```
