# Variable Tilemaps

## Introduction @unplugged

This tutorial teaches you how to save tilemaps under variable names to be used later.
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
![Customize your tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/variables-tilemaps-5.gif "Customize Tilemap" )

```python
tiles.load_map(tile_map1)
```


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

## Step Seven

Once you have reached the goal of the first tilemap, load the tilemap tile_map2.
![Customize your tilemap](https://raw.githubusercontent.com/MrDGuy/pxt-skillmap-robot/main/docs/static/variables-tilemaps-3.gif "Customize Tilemap" )

```python
tiles.load_map(tile_map2)
```


## Step Eight

Use the ``||robot:begin screen ||`` code AGAIN after you load the tile_map2 to start your robot on the start tile and set up the tilemap on the new tilemap.

```python
robot.begin_screen()
```

## Step Nine

Use the ``||robot:move forward||`` code to move the robot. Change the direction the robot is facing with the ``||robot:turn right||`` and ``||robot:turn left||`` code.  Move the robot to the goal tile of the second tilemap.

```python
robot.move_forward()
robot.turn_right()
robot.turn_left()
```

```assetjson
{
  "README.md": " ",
  "assets.json": "",
  "main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><block type=\"pxt-on-start\" x=\"0\" y=\"0\"></block></xml>",
  "main.py": "# ...",
  "main.ts": "\n",
  "pxt.json": "{\n    \"name\": \"Non Git Hub Robot Tile and Tilemap Assets - Copy\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\",\n        \"tilemaps\": \"github:microsoft/pxt-tilemaps#v1.12.0\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\",\n        \"main.py\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.13.30\",\n        \"tag\": \"v1.13.30\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/4e9a9f1f821251b14f74e4d41eac7c10db87224e\",\n        \"target\": \"1.13.30\",\n        \"pxt\": \"9.1.6\"\n    },\n    \"preferredEditor\": \"pyprj\"\n}\n",
  "tilemap.g.jres": "{\n    \"tile1\": {\n        \"data\": \"hwQQABAAAAD//////////09ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPT//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"startTile\"\n    },\n    \"tile2\": {\n        \"data\": \"hwQQABAAAAD//////////4+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPj//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"goalTile\"\n    },\n    \"tile3\": {\n        \"data\": \"hwQQABAAAAD//////////x8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfH//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"floorTile\"\n    },\n    \"tile4\": {\n        \"data\": \"hwQQABAAAAD//////////393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/f//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"coinTile\"\n    },\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"tile5\": {\n        \"data\": \"hwQQABAAAAD//////////7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/v//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"wallTile\"\n    },\n    \"level1\": {\n        \"id\": \"level1\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTAwYTAwMDcwMDA0MDUwNTBjMDUwNTBjMDUwNTA2MGExMDAzMTAxMTExMTAwMzAyMDcwYTAzMDMwMzExMTExMDExMTEwNzBmMDMxMTAzMTExMTEwMDMwMzBlMGEwMzExMDMxMTEwMTExMTAzMDcwYTAxMTEwMzAzMDMxMDAzMDMwNzA5MGIwYjBkMGIwYjBkMGIwYjA4MjIyMjIyMjIyMjAyMDAyMjAwMjAwMjAwMjIyMDIyMDIwMjIyMDAyMDAyMDIwMjIyMjAwMjAyMDAwMDIwMjIyMjIyMjIyMg==\",\n        \"tileset\": [\n            \"myTiles.transparency16\",\n            \"myTiles.tile1\",\n            \"myTiles.tile2\",\n            \"myTiles.tile3\",\n            \"sprites.dungeon.greenOuterNorthWest\",\n            \"sprites.dungeon.greenOuterNorth0\",\n            \"sprites.dungeon.greenOuterNorthEast\",\n            \"sprites.dungeon.greenOuterEast0\",\n            \"sprites.dungeon.greenOuterSouthWest\",\n            \"sprites.dungeon.greenOuterSouthEast\",\n            \"sprites.dungeon.greenOuterWest0\",\n            \"sprites.dungeon.greenOuterSouth1\",\n            \"sprites.dungeon.greenOuterNorth2\",\n            \"sprites.dungeon.greenOuterSouth2\",\n            \"sprites.dungeon.greenOuterEast2\",\n            \"sprites.dungeon.greenOuterWest2\",\n            \"myTiles.tile4\",\n            \"myTiles.tile5\"\n        ],\n        \"displayName\": \"level1\"\n    },\n    \"level2\": {\n        \"id\": \"level2\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTAwYTAwMDcwMDA0MDUwNTBjMDUwNTBjMDUwNTA2MGExMDExMTEwMzAzMDMxMTAyMDcwYTAzMDMwMzAzMTExMDExMDMwNzBmMTExMTExMDMxMTAzMTExMDBlMGEwMzAzMDMwMzExMTAxMTEwMDcwYTAxMTExMTExMTEwMzEwMTAwNzA5MGIwYjBkMGIwYjBkMGIwYjA4MjIyMjIyMjIyMjAyMjIwMDIwMjAwMjAwMjAyMDIwMjIyMjIwMjAyMDAyMDAyMDIwMjAwMjIyMjIwMDIwMjIyMjIyMjIyMg==\",\n        \"tileset\": [\n            \"myTiles.transparency16\",\n            \"myTiles.tile1\",\n            \"myTiles.tile2\",\n            \"myTiles.tile3\",\n            \"sprites.dungeon.greenOuterNorthWest\",\n            \"sprites.dungeon.greenOuterNorth0\",\n            \"sprites.dungeon.greenOuterNorthEast\",\n            \"sprites.dungeon.greenOuterEast0\",\n            \"sprites.dungeon.greenOuterSouthWest\",\n            \"sprites.dungeon.greenOuterSouthEast\",\n            \"sprites.dungeon.greenOuterWest0\",\n            \"sprites.dungeon.greenOuterSouth1\",\n            \"sprites.dungeon.greenOuterNorth2\",\n            \"sprites.dungeon.greenOuterSouth2\",\n            \"sprites.dungeon.greenOuterEast2\",\n            \"sprites.dungeon.greenOuterWest2\",\n            \"myTiles.tile4\",\n            \"myTiles.tile5\"\n        ],\n        \"displayName\": \"level2\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
  "tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile1 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile2 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile3 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile4 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile5 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tilemap\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"level1\":\n            case \"level1\":return tiles.createTilemap(hex`0a0007000405050c05050c0505060a1003101111100302070a0303031111101111070f03110311111003030e0a0311031110111103070a011103030310030307090b0b0d0b0b0d0b0b08`, img`\n2 2 2 2 2 2 2 2 2 2 \n2 . . . 2 2 . . . 2 \n2 . . . 2 2 . 2 2 2 \n2 . 2 . 2 2 . . . 2 \n2 . 2 . 2 . 2 2 . 2 \n2 . 2 . . . . . . 2 \n2 2 2 2 2 2 2 2 2 2 \n`, [myTiles.transparency16,myTiles.tile1,myTiles.tile2,myTiles.tile3,sprites.dungeon.greenOuterNorthWest,sprites.dungeon.greenOuterNorth0,sprites.dungeon.greenOuterNorthEast,sprites.dungeon.greenOuterEast0,sprites.dungeon.greenOuterSouthWest,sprites.dungeon.greenOuterSouthEast,sprites.dungeon.greenOuterWest0,sprites.dungeon.greenOuterSouth1,sprites.dungeon.greenOuterNorth2,sprites.dungeon.greenOuterSouth2,sprites.dungeon.greenOuterEast2,sprites.dungeon.greenOuterWest2,myTiles.tile4,myTiles.tile5], TileScale.Sixteen);\n            case \"level2\":\n            case \"level2\":return tiles.createTilemap(hex`0a0007000405050c05050c0505060a1011110303031102070a0303030311101103070f11111103110311100e0a0303030311101110070a011111111103101007090b0b0d0b0b0d0b0b08`, img`\n2 2 2 2 2 2 2 2 2 2 \n2 . 2 2 . . . 2 . 2 \n2 . . . . 2 . 2 . 2 \n2 2 2 2 . 2 . 2 . 2 \n2 . . . . 2 . 2 . 2 \n2 . 2 2 2 2 . . . 2 \n2 2 2 2 2 2 2 2 2 2 \n`, [myTiles.transparency16,myTiles.tile1,myTiles.tile2,myTiles.tile3,sprites.dungeon.greenOuterNorthWest,sprites.dungeon.greenOuterNorth0,sprites.dungeon.greenOuterNorthEast,sprites.dungeon.greenOuterEast0,sprites.dungeon.greenOuterSouthWest,sprites.dungeon.greenOuterSouthEast,sprites.dungeon.greenOuterWest0,sprites.dungeon.greenOuterSouth1,sprites.dungeon.greenOuterNorth2,sprites.dungeon.greenOuterSouth2,sprites.dungeon.greenOuterEast2,sprites.dungeon.greenOuterWest2,myTiles.tile4,myTiles.tile5], TileScale.Sixteen);\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"startTile\":\n            case \"tile1\":return tile1;\n            case \"goalTile\":\n            case \"tile2\":return tile2;\n            case \"floorTile\":\n            case \"tile3\":return tile3;\n            case \"coinTile\":\n            case \"tile4\":return tile4;\n            case \"transparency16\":return transparency16;\n            case \"wallTile\":\n            case \"tile5\":return tile5;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
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
