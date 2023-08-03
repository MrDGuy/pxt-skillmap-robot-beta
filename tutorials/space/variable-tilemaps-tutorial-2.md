# Variable Tilemaps

## Introduction @unplugged

This tutorial will teach you how to link tilemaps together to have the robot move through multiple levels.
![Setting your two tilemaps to variables](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/variables-tilemaps-1.png "Variable Tilemaps" )

## Step One

Use the ``||tiles:tilemap ||`` code to create a new tilemap. Click the map and then My Assets then select level1.

```python
tiles.create_map(tilemap("""level1"""))
```

## Step Two

After that in the front of the line of code write "tile_map1 =".

```python
tile_map1 = tiles.create_map(tilemap("""level1"""))
```

## Step Three

Use the ``||tiles:tilemap ||`` code to create a new tilemap. Click the map and then My Assets then select level2.

```python
tiles.create_map(tilemap("""level2"""))
```

## Step Four

After that in the front of the line of code write "tile_map2 =".
![Customize your tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/variables-tilemaps-1.png "Customize Tilemap" )

```python
tile_map2 = tiles.create_map(tilemap("""level2"""))
```

## Step Five

Load the tilemap tile_map1
![Customize your tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/variables-tilemaps-2.gif "Customize Tilemap" )

```python
tiles.load_map(tile_map1)
```

## Step Six

Use the ``||robot:begin screen ||`` code to start your robot on the start tile and set up the tilemap.

```python
robot.begin_screen()
```

## Step Seven

Connect the two tilemaps with ``||tiles:connect tilemap1 and tilemap2 by connection ||`` code.  Change the two parameters to tile_map1 and tile_map2.

```python
tiles.connect_map_by_id(tile_map1, tile_map2, ConnectionKind.door1)
```

## Step Eight

Pull in the code from the ``||scene:run code on sprite of kind overlaps tile at location||`` in the ``||scene:scene||`` category under the tilemaps section.

```python
def on_overlap_tile(sprite, location):
    pass
scene.on_overlap_tile(SpriteKind.player, img(""" """), on_overlap_tile)
```

## Step Nine

Replace the img(""" """) code at the end of the overlap tile code with assets.tile("""door1""")

```python
def on_overlap_tile(sprite, location):
    pass
scene.on_overlap_tile(SpriteKind.player, assets.tile("""door1"""), on_overlap_tile)
```

## Step Ten

Replace the pass in the on_overlap_tile function with ``||tiles:set current tilemap to map||`` code to load tile_map2. Also, include a new ``||robot:begin screen||`` to load the next level properly.

```python
def on_overlap_tile(sprite, location):
    tiles.load_map(tile_map2)
    robot.begin_screen()
scene.on_overlap_tile(SpriteKind.player, assets.tile("""door1"""), on_overlap_tile)
```

## Step Eleven

Use the ``||robot:move forward||`` code to move the robot. Change the direction the robot is facing with the ``||robot:turn right||`` and ``||robot:turn left||`` code.  Also, use the ``||robot:collect coin||`` to collect all the coins along the way. Move the robot to the goal tile.

```python
robot.move_forward()
robot.turn_right()
robot.turn_left()
robot.collect_coin()
```



```assetjson
{
  "README.md": " ",
  "assets.json": "",
  "main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><block type=\"pxt-on-start\" x=\"0\" y=\"0\"></block></xml>",
  "main.py": "# ...",
  "main.ts": "\n",
  "pxt.json": "{\n    \"name\": \"Non Git Hub Robot Tile and Tilemap Assets - Copy\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\",\n        \"tilemaps\": \"github:microsoft/pxt-tilemaps#v1.12.0\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\",\n        \"main.py\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.13.30\",\n        \"tag\": \"v1.13.30\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/4e9a9f1f821251b14f74e4d41eac7c10db87224e\",\n        \"target\": \"1.13.30\",\n        \"pxt\": \"9.1.6\"\n    },\n    \"preferredEditor\": \"pyprj\"\n}\n",
  "tilemap.g.jres": "{\n    \"tile1\": {\n        \"data\": \"hwQQABAAAAD//////////09ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPT//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"startTile\"\n    },\n    \"tile2\": {\n        \"data\": \"hwQQABAAAAD//////////4+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPj//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"goalTile\"\n    },\n    \"tile3\": {\n        \"data\": \"hwQQABAAAAD//////////x8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfH//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"floorTile\"\n    },\n    \"tile4\": {\n        \"data\": \"hwQQABAAAAD//////////393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/f//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"coinTile\"\n    },\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"tile5\": {\n        \"data\": \"hwQQABAAAAD//////////7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/v//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"wallTile\"\n    },\n    \"tile6\": {\n        \"data\": \"hwQQABAAAAB3R0RERERERHcUEUFERERERxREQURERERHRBFEREREREdERERERERER0QRQURERERHREFBREREREdEEUFEQUFER0RERBQRQURHRBFBRERBREdEQUFERERER0QRQURERERHREREREREREdEEUFEREREd0RBRERERER3R0RERERERA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"door1\"\n    },\n    \"level2\": {\n        \"id\": \"level2\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTAwYTAwMDcwMDA0MDUwNTBjMDUwNTBjMDUwNTA2MGExMDExMTEwMzAzMDMxMTAyMDcwYTAzMDMwMzAzMTExMDExMDMwNzBmMTExMTExMDMxMTAzMTExMDBlMGEwMzAzMDMwMzExMTAxMTEwMDcwYTAxMTExMTExMTEwMzEwMTAwNzA5MGIwYjBkMGIwYjBkMGIwYjA4MjIyMjIyMjIyMjAyMjIwMDIwMjAwMjAwMjAyMDIwMjIyMjIwMjAyMDAyMDAyMDIwMjAwMjIyMjIwMDIwMjIyMjIyMjIyMg==\",\n        \"tileset\": [\n            \"myTiles.transparency16\",\n            \"myTiles.tile1\",\n            \"myTiles.tile2\",\n            \"myTiles.tile3\",\n            \"sprites.dungeon.greenOuterNorthWest\",\n            \"sprites.dungeon.greenOuterNorth0\",\n            \"sprites.dungeon.greenOuterNorthEast\",\n            \"sprites.dungeon.greenOuterEast0\",\n            \"sprites.dungeon.greenOuterSouthWest\",\n            \"sprites.dungeon.greenOuterSouthEast\",\n            \"sprites.dungeon.greenOuterWest0\",\n            \"sprites.dungeon.greenOuterSouth1\",\n            \"sprites.dungeon.greenOuterNorth2\",\n            \"sprites.dungeon.greenOuterSouth2\",\n            \"sprites.dungeon.greenOuterEast2\",\n            \"sprites.dungeon.greenOuterWest2\",\n            \"myTiles.tile4\",\n            \"myTiles.tile5\"\n        ],\n        \"displayName\": \"level2\"\n    },\n    \"level1\": {\n        \"id\": \"level1\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTAwYTAwMDcwMDAzMDQwNDBiMDQwNDBiMDQwNDA1MDkwZjAyMGYxMDEwMGYwMjExMDYwOTAyMDIwMjEwMTAwZjEwMTAwNjBlMDIxMDAyMTAxMDBmMDIwMjBkMDkwMjEwMDIxMDBmMTAxMDAyMDYwOTAxMTAwMjAyMDIwZjAyMDIwNjA4MGEwYTBjMGEwYTBjMGEwYTA3MjIyMjIyMjIyMjAyMDAyMjAwMjAwMjAwMjIyMDIyMDIwMjIyMDAyMDAyMDIwMjIyMjAwMjAyMDAwMDIwMjIyMjIyMjIyMg==\",\n        \"tileset\": [\n            \"myTiles.transparency16\",\n            \"myTiles.tile1\",\n            \"myTiles.tile3\",\n            \"sprites.dungeon.greenOuterNorthWest\",\n            \"sprites.dungeon.greenOuterNorth0\",\n            \"sprites.dungeon.greenOuterNorthEast\",\n            \"sprites.dungeon.greenOuterEast0\",\n            \"sprites.dungeon.greenOuterSouthWest\",\n            \"sprites.dungeon.greenOuterSouthEast\",\n            \"sprites.dungeon.greenOuterWest0\",\n            \"sprites.dungeon.greenOuterSouth1\",\n            \"sprites.dungeon.greenOuterNorth2\",\n            \"sprites.dungeon.greenOuterSouth2\",\n            \"sprites.dungeon.greenOuterEast2\",\n            \"sprites.dungeon.greenOuterWest2\",\n            \"myTiles.tile4\",\n            \"myTiles.tile5\",\n            \"myTiles.tile6\"\n        ],\n        \"displayName\": \"level1\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
  "tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile1 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile2 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile3 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile4 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile5 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile6 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tilemap\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"level2\":\n            case \"level2\":return tiles.createTilemap(hex`0a0007000405050c05050c0505060a1011110303031102070a0303030311101103070f11111103110311100e0a0303030311101110070a011111111103101007090b0b0d0b0b0d0b0b08`, img`\n2 2 2 2 2 2 2 2 2 2 \n2 . 2 2 . . . 2 . 2 \n2 . . . . 2 . 2 . 2 \n2 2 2 2 . 2 . 2 . 2 \n2 . . . . 2 . 2 . 2 \n2 . 2 2 2 2 . . . 2 \n2 2 2 2 2 2 2 2 2 2 \n`, [myTiles.transparency16,myTiles.tile1,myTiles.tile2,myTiles.tile3,sprites.dungeon.greenOuterNorthWest,sprites.dungeon.greenOuterNorth0,sprites.dungeon.greenOuterNorthEast,sprites.dungeon.greenOuterEast0,sprites.dungeon.greenOuterSouthWest,sprites.dungeon.greenOuterSouthEast,sprites.dungeon.greenOuterWest0,sprites.dungeon.greenOuterSouth1,sprites.dungeon.greenOuterNorth2,sprites.dungeon.greenOuterSouth2,sprites.dungeon.greenOuterEast2,sprites.dungeon.greenOuterWest2,myTiles.tile4,myTiles.tile5], TileScale.Sixteen);\n            case \"level1\":\n            case \"level1\":return tiles.createTilemap(hex`0a0007000304040b04040b040405090f020f10100f0211060902020210100f1010060e02100210100f02020d09021002100f101002060901100202020f020206080a0a0c0a0a0c0a0a07`, img`\n2 2 2 2 2 2 2 2 2 2 \n2 . . . 2 2 . . . 2 \n2 . . . 2 2 . 2 2 2 \n2 . 2 . 2 2 . . . 2 \n2 . 2 . 2 . 2 2 . 2 \n2 . 2 . . . . . . 2 \n2 2 2 2 2 2 2 2 2 2 \n`, [myTiles.transparency16,myTiles.tile1,myTiles.tile3,sprites.dungeon.greenOuterNorthWest,sprites.dungeon.greenOuterNorth0,sprites.dungeon.greenOuterNorthEast,sprites.dungeon.greenOuterEast0,sprites.dungeon.greenOuterSouthWest,sprites.dungeon.greenOuterSouthEast,sprites.dungeon.greenOuterWest0,sprites.dungeon.greenOuterSouth1,sprites.dungeon.greenOuterNorth2,sprites.dungeon.greenOuterSouth2,sprites.dungeon.greenOuterEast2,sprites.dungeon.greenOuterWest2,myTiles.tile4,myTiles.tile5,myTiles.tile6], TileScale.Sixteen);\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"startTile\":\n            case \"tile1\":return tile1;\n            case \"goalTile\":\n            case \"tile2\":return tile2;\n            case \"floorTile\":\n            case \"tile3\":return tile3;\n            case \"coinTile\":\n            case \"tile4\":return tile4;\n            case \"transparency16\":return transparency16;\n            case \"wallTile\":\n            case \"tile5\":return tile5;\n            case \"door1\":\n            case \"tile6\":return tile6;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
}
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
