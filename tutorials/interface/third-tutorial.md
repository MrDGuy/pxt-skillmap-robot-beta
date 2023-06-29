# Collect Coins along your journey

## Introduction @unplugged

In this tutorial you will make the robot move to the goal tile and collect coins along the way.

## Step One

Use the ``||robot:begin screen ||`` code to start your robot and place the coins

```python
robot.begin_screen()
```

## Step Two

Use the ``||robot:move forward||`` block to move the robot.

```python
robot.move_forward()
```

## Step Three

Turn the robot right with ``||robot:turn right||`` or turn the robot left with ``||robot:turn left||``.

```python
robot.turn_right()
robot.turn_left()

```

## Step Four

Collect any coins with the collect coin ``||robot:collect coin||`` block.  Reminder: You may ONLY collect a coin if the robot is in the same tile as the coin.

```python
robot.collect_coin()
```

```customts
    tiles.loadMap(tiles.createMap(tilemap`level1`))
    robot.beginScreen()
    game.onUpdate(function () {
        if (robot.goalReached()) {
            music.play(music.melodyPlayable(music.powerUp), music.PlaybackMode.UntilDone)
            game.splash("You reached the goal!")
            game.reset()
        }
    })
```



```assetjson
{
  "README.md": " ",
  "assets.json": "",
  "images.g.jres": "{\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myImages\"\n    }\n}",
  "images.g.ts": "// Auto-generated code. Do not edit.\nnamespace myImages {\n\n    helpers._registerFactory(\"image\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"animation\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"song\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n",
  "main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><block type=\"pxt-on-start\" x=\"0\" y=\"0\"><statement name=\"HANDLER\"><block type=\"tilemap_loadMap\"><value name=\"map\"><shadow type=\"create_overworld_map\"><field name=\"tilemap\">tilemap`level1`</field><data>{\"commentRefs\":[],\"fieldData\":{\"tilemap\":\"level1\"}}</data></shadow></value><next><block type=\"robot_beginScreen\"></block></next></block></statement></block><block type=\"gameupdate\" x=\"390\" y=\"90\"><statement name=\"HANDLER\"><block type=\"controls_if\"><value name=\"IF0\"><shadow type=\"logic_boolean\"><field name=\"BOOL\">TRUE</field></shadow><block type=\"robot_goalReached\"></block></value><statement name=\"DO0\"><block type=\"music_playable_play\"><field name=\"playbackMode\">music.PlaybackMode.UntilDone</field><value name=\"toPlay\"><shadow type=\"music_melody_playable\"><field name=\"melody\">music.baDing</field></shadow><block type=\"music_melody_playable\"><field name=\"melody\">music.powerUp</field></block></value><next><block type=\"gameSplash\"><mutation xmlns=\"http://www.w3.org/1999/xhtml\" _expanded=\"0\" _input_init=\"true\"></mutation><value name=\"title\"><shadow type=\"text\"><field name=\"TEXT\">You reached the goal!</field></shadow></value><value name=\"subtitle\"><shadow type=\"text\"><field name=\"TEXT\"></field></shadow></value><next><block type=\"arcade_game_reset\"></block></next></block></next></block></statement></block></statement></block></xml>",
  "main.py": "",
  "main.ts": "\n",
  "pxt.json": "{\n    \"name\": \"Basic Template for Code and Asset Creation\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\",\n        \"tilemaps\": \"github:microsoft/pxt-tilemaps#v1.12.0\",\n        \"Sprite Grid\": \"github:microsoft/arcade-grid#v1.3.0\",\n        \"Robot Extension\": \"github:MrDGuy/robot-extension#45f0768a5e0c25e4123c6e65e56115a7d468331b\",\n        \"color\": \"*\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\",\n        \"main.py\",\n        \"images.g.jres\",\n        \"images.g.ts\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.13.26\",\n        \"tag\": \"v1.13.26\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/55a70d58dd8d2cfb8363bc6fa31de4c829c33a4d\",\n        \"target\": \"1.13.26\",\n        \"pxt\": \"9.1.3\"\n    },\n    \"preferredEditor\": \"pyprj\",\n    \"palette\": [\n        \"#000000\",\n        \"#FFFFFF\",\n        \"#FF2121\",\n        \"#FF93C4\",\n        \"#FF8135\",\n        \"#FFF609\",\n        \"#249CA3\",\n        \"#78DC52\",\n        \"#003FAD\",\n        \"#87F2FF\",\n        \"#8E2EC4\",\n        \"#A4839F\",\n        \"#5C406c\",\n        \"#E5CDC4\",\n        \"#91463d\",\n        \"#000000\"\n    ]\n}\n",
  "tilemap.g.jres": "{\n    \"tile1\": {\n        \"data\": \"hwQQABAAAAD//////////09ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPRPRERERERE9E9ERERERET0T0RERERERPT//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"startTile\"\n    },\n    \"tile2\": {\n        \"data\": \"hwQQABAAAAD//////////x8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfEfERERERER8R8RERERERHxHxEREREREfH//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"floorTile\"\n    },\n    \"tile3\": {\n        \"data\": \"hwQQABAAAAD//////////4+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPiPiIiIiIiI+I+IiIiIiIj4j4iIiIiIiPj//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"goalTile\"\n    },\n    \"tile4\": {\n        \"data\": \"hwQQABAAAAD//////////393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/f//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"coinTile\"\n    },\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"tile5\": {\n        \"data\": \"hwQQABAAAAD//////////7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/u/u7u7u7u7+7+7u7u7u7v7v7u7u7u7u/v//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"wallTile\"\n    },\n    \"level1\": {\n        \"id\": \"level1\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTAwYTAwMDcwMDAzMDgwOTBmMDgwODBmMDgwODA3MDQxNDAxMDEwMTE0MTMwMTAyMGEwNDAxMTMwMTEzMTMxMzAxMDEwYTExMDExMzAxMDExNDAxMDExMzEwMDYwMTEzMDExMzEzMTMwMTE0MGEwNDEyMDEwMTAxMDEwMTAxMDEwYTA1MGMwYzBlMGQwYzBlMGMwYzBiMjIyMjIyMjIyMjAyMDAwMDAyMjAwMjAyMjIwMjIwMDIwMjAwMDAyMjAyMDIyMjAyMjAwMjAwMDAwMDIwMjIyMjIyMjIyMg==\",\n        \"tileset\": [\n            \"myTiles.transparency16\",\n            \"myTiles.tile2\",\n            \"myTiles.tile3\",\n            \"sprites.dungeon.purpleOuterNorthWest\",\n            \"sprites.dungeon.purpleOuterWest0\",\n            \"sprites.dungeon.purpleOuterSouthEast\",\n            \"sprites.dungeon.purpleOuterWest1\",\n            \"sprites.dungeon.purpleOuterNorthEast\",\n            \"sprites.dungeon.purpleOuterNorth0\",\n            \"sprites.dungeon.purpleOuterNorth1\",\n            \"sprites.dungeon.purpleOuterEast1\",\n            \"sprites.dungeon.purpleOuterSouthWest\",\n            \"sprites.dungeon.purpleOuterSouth1\",\n            \"sprites.dungeon.purpleOuterSouth0\",\n            \"sprites.dungeon.purpleOuterSouth2\",\n            \"sprites.dungeon.purpleOuterNorth2\",\n            \"sprites.dungeon.purpleOuterEast2\",\n            \"sprites.dungeon.purpleOuterWest2\",\n            \"myTiles.tile1\",\n            \"myTiles.tile5\",\n            \"myTiles.tile4\"\n        ],\n        \"displayName\": \"level1\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
  "tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile1 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile2 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile3 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile4 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile5 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tilemap\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"level1\":\n            case \"level1\":return tiles.createTilemap(hex`0a0007000308090f08080f0808070414010101141301020a0401130113131301010a110113010114010113100601130113131301140a0412010101010101010a050c0c0e0d0c0e0c0c0b`, img`\n2 2 2 2 2 2 2 2 2 2 \n2 . . . . . 2 . . 2 \n2 . 2 . 2 2 2 . . 2 \n2 . 2 . . . . . 2 2 \n2 . 2 . 2 2 2 . . 2 \n2 . . . . . . . . 2 \n2 2 2 2 2 2 2 2 2 2 \n`, [myTiles.transparency16,myTiles.tile2,myTiles.tile3,sprites.dungeon.purpleOuterNorthWest,sprites.dungeon.purpleOuterWest0,sprites.dungeon.purpleOuterSouthEast,sprites.dungeon.purpleOuterWest1,sprites.dungeon.purpleOuterNorthEast,sprites.dungeon.purpleOuterNorth0,sprites.dungeon.purpleOuterNorth1,sprites.dungeon.purpleOuterEast1,sprites.dungeon.purpleOuterSouthWest,sprites.dungeon.purpleOuterSouth1,sprites.dungeon.purpleOuterSouth0,sprites.dungeon.purpleOuterSouth2,sprites.dungeon.purpleOuterNorth2,sprites.dungeon.purpleOuterEast2,sprites.dungeon.purpleOuterWest2,myTiles.tile1,myTiles.tile5,myTiles.tile4], TileScale.Sixteen);\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"startTile\":\n            case \"tile1\":return tile1;\n            case \"floorTile\":\n            case \"tile2\":return tile2;\n            case \"goalTile\":\n            case \"tile3\":return tile3;\n            case \"coinTile\":\n            case \"tile4\":return tile4;\n            case \"transparency16\":return transparency16;\n            case \"wallTile\":\n            case \"tile5\":return tile5;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
}
```
