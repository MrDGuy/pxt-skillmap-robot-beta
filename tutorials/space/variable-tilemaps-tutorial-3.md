# Customized Tilemaps

## Introduction @unplugged

You will now demonstrate all that you have learned about the robot and tilemaps.

## Step One

Create two custom tilemaps that each contain a startTile and one with a connection tile and the other with a goalTile.  Make sure you create a custom coinTile to place coins on your tilemaps.  Name the first tilemap level1 and the second level2.

## Step One

Use the ``||tiles:tilemap ||`` code to create a new tilemap. Click the map and then Create a custom tilemaps that contains a startTile and a connection tile named door1.  Make sure you create a custom coinTile to place coins on your tilemaps.  Name the first tilemap level1.

```python
tiles.create_map(tilemap("""level1"""))
```

## Step Two

After that in the front of the line of code write tile_map1 =.

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
```

## Step Three

Use the ``||tiles:tilemap ||`` code to create a new tilemap. Click the map and then Create a custom tilemaps that contains a startTile and a goalTile.  Make sure you create a custom coinTile to place coins on your tilemaps.  Name the second tilemap level2.

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
tiles.create_map(tilemap("""level2"""))
```

## Step Four

After that in the front of the line of code write tile_map2 =.
![Customize your tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/variables-tilemaps-1.png "Customize Tilemap" )

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
tile_map2 = tiles.create_map(tilemap("""level2"""))
```

## Step Five

Load the tilemap tile_map1. Code: tiles.load_map(tile_map1)
![Customize your tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/variables-tilemaps-2.gif "Customize Tilemap" )

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
tile_map2 = tiles.create_map(tilemap("""level2"""))
tiles.load_map(tile_map1)
```

## Step Six

Use the ``||robot:begin screen ||`` code to start your robot on the start tile and set up the tilemap.

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
tile_map2 = tiles.create_map(tilemap("""level2"""))
tiles.load_map(tile_map1)
robot.begin_screen()
```

## Step Seven

Connect the two tilemaps with ``||tiles:connect tilemap1 and tilemap2 by connection ||`` code.  

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
tile_map2 = tiles.create_map(tilemap("""level2"""))
tiles.load_map(tile_map1)
robot.begin_screen()
tiles.connect_map_by_id(tilemap1, tilemap2, ConnectionKind.door1)
```

## Step Eight
Change tiles.connect_map_by_id(tilemap1, tilemap2, ConnectionKind.door1) to tiles.connect_map_by_id(tile_map1, tile_map2, ConnectionKind.door1)

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
tile_map2 = tiles.create_map(tilemap("""level2"""))
tiles.load_map(tile_map1)
robot.begin_screen()
tiles.connect_map_by_id(tile_map1, tile_map2, ConnectionKind.door1)
```

## Step Eight

Pull in the code from the ``||scene:run code on sprite of kind overlaps tile at location||`` in the ``||scene:scene||`` category under the tilemaps section.

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
tile_map2 = tiles.create_map(tilemap("""level2"""))
tiles.load_map(tile_map1)
robot.begin_screen()
tiles.connect_map_by_id(tile_map1, tile_map2, ConnectionKind.door1)

def on_overlap_tile(sprite, location):
    pass
scene.on_overlap_tile(SpriteKind.player, img(""" """), on_overlap_tile)
```

## Step Nine

Replace the img(""" """) code at the end of the overlap tile code with assets.tile("""door1""")

```pythontile_map1 = tiles.create_map(tilemap("""level1"""))
tile_map2 = tiles.create_map(tilemap("""level2"""))
tiles.load_map(tile_map1)
robot.begin_screen()
tiles.connect_map_by_id(tile_map1, tile_map2, ConnectionKind.door1)

def on_overlap_tile(sprite, location):
    pass
scene.on_overlap_tile(SpriteKind.player, assets.tile("""door1"""), on_overlap_tile)
```

## Step Ten

Replace the pass in the on_overlap_tile function with ``||tiles:set current tilemap to map||`` code to load tile_map2. Also, include a new ``||robot:begin screen||`` to load the next level properly.

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
tile_map2 = tiles.create_map(tilemap("""level2"""))
tiles.load_map(tile_map1)
robot.begin_screen()
tiles.connect_map_by_id(tile_map1, tile_map2, ConnectionKind.door1)

def on_overlap_tile(sprite, location):
    tiles.load_map(tile_map2)
    robot.begin_screen()
scene.on_overlap_tile(SpriteKind.player, assets.tile("""door1"""), on_overlap_tile)
```

## Step Twelve

Use the ``||robot:move forward||`` code to move the robot. Change the direction the robot is facing with the ``||robot:turn right||`` and ``||robot:turn left||`` code.  Also, use the ``||robot:collect coin||`` to collect all the coins along the way. Move the robot to the goal tile.

```python
robot.move_forward()
robot.turn_right()
robot.turn_left()
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
