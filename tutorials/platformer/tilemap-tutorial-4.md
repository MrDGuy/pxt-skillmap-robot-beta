# Using Tilemaps

## Introduction @unplugged

This tutorial teaches you to customize your tilemaps given already created tiles.

## Step One

Use the ``||tiles:set current tilemap to map ||`` code to start your robot on the start tile and set up the tilemap. Here is a slideshow which shows how to make a custom tilemap: https://docs.google.com/presentation/d/1cawKIOhjpS6RkyLfUtz1jMWu12Km-bZNeiX4x2yisHQ/edit?usp=sharing

```python
tiles.load_map(tiles.create_map(tilemap(""" """)))
```

## Step Two @showhint @unplugged

Change the dimensions to 10 x 7. 
~hint Click here to see how 🕵🏽

---

![Make a 10x7 tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/tilemap-customize-tile-1.gif "10x7 Tilemap" )
hint~


## Step Three @showhint @unplugged

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

## Step Four

Make a coinTile which is just like a regular tile but named "coinTile" exactly.  Wherever you place this on your tilemap a coin will appear.

## Step Five @showhint @unplugged

Click the walls tool to create walls around the edge and any walls you want inside your robot's world.  If you choose to make walls in your world make sure they are different from the non-wall tiles.
~hint Here is how to make walls 🕵🏽

---

![Add walls](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/tilemap-customize-3.gif "Add walls" )
hint~


## Step Six

Use the ``||robot:begin screen ||`` code to start your robot on the start tile and set up the tilemap.  You will now see coins wherever there is a coinTile.

```python
robot.begin_screen()
```

## Step Seven

Use the ``||robot:move forward||`` code to move the robot. Change the direction the robot is facing with the ``||robot:turn right||`` and ``||robot:turn left||`` code.  

```python
robot.move_forward()
robot.turn_right()
robot.turn_left()
```

## Step Eight

Use the ``||robot:collect coin||`` code to collect the coins and then move the robot to the goal tile.

```python
robot.collect_coin()
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
