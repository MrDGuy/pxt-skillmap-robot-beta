# Using Tilemaps

## Introduction @unplugged

This tutorial teaches you to customize your tilemaps given already created tiles.

## Step One

Use the ``||tiles:set current tilemap to map ||`` code to start your robot on the start tile and set up the tilemap. Here is a slideshow which shows how to make a custom tilemap: https://docs.google.com/presentation/d/1cawKIOhjpS6RkyLfUtz1jMWu12Km-bZNeiX4x2yisHQ/edit?usp=sharing

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
robot.collect_coin()
```
```assetjson
{
  "README.md": " ",
  "assets.json": "",
  "main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><block type=\"pxt-on-start\" x=\"0\" y=\"0\"></block><block type=\"forever\" x=\"110\" y=\"190\"><statement name=\"HANDLER\"><block type=\"controls_if\"><value name=\"IF0\"><shadow type=\"logic_boolean\"><field name=\"BOOL\">TRUE</field></shadow><block type=\"robot_goalReached\"><field name=\"goalTile\">sprites.background.autumn</field></block></value><statement name=\"DO0\"><block type=\"game_setgameovereffect\"><field name=\"effect\">effects.confetti</field><value name=\"win\"><shadow type=\"toggleWinLose\"><field name=\"win\">true</field></shadow></value><next><block type=\"game_setgameoverplayable\"><value name=\"sound\"><shadow type=\"music_melody_playable\"><field name=\"melody\">music.powerUp</field></shadow></value><value name=\"looping\"><shadow type=\"toggleOnOff\"><field name=\"on\">true</field></shadow></value><value name=\"win\"><shadow type=\"toggleWinLose\"><field name=\"win\">true</field></shadow></value><next><block type=\"game_setgameovermessage\"><value name=\"message\"><shadow type=\"text\"><field name=\"TEXT\">Goal Reached!</field></shadow></value><value name=\"win\"><shadow type=\"toggleWinLose\"><field name=\"win\">true</field></shadow></value></block></next></block></next></block></statement></block></statement></block></xml>",
  "main.py": "",
  "main.ts": "\n",
  "pxt.json": "{\n    \"name\": \"Non Git Hub Robot Tile and Tilemap Assets Coin Tile Only\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\",\n        \"tilemaps\": \"github:microsoft/pxt-tilemaps#v1.12.0\",\n        \"Sprite Grid\": \"github:microsoft/arcade-grid#v1.3.0\",\n        \"Robot Extension\": \"github:MrDGuy/robot-extension#8a70c12520c14e7caf22006addbea36f5267078f\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\",\n        \"main.py\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.13.31\",\n        \"tag\": \"v1.13.31\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/ef3aad740700f5159eebccf721fa35d32683fcaa\",\n        \"target\": \"1.13.31\",\n        \"pxt\": \"9.1.6\"\n    },\n    \"preferredEditor\": \"pyprj\"\n}\n",
  "tilemap.g.jres": "{\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"tile4\": {\n        \"data\": \"hwQQABAAAAD//////////393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/d/d3d3d3d39393d3d3d3f3f3d3d3d3d/f//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"coinTile\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
  "tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile4 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"transparency16\":return transparency16;\n            case \"coinTile\":\n            case \"tile4\":return tile4;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
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
