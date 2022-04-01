# template

```js
const MAP_NAME = {
  "properties": {//default for all areas
    width: 80,
    height: 15,
    index: 19,
    disableAbilities: false, //optional
    canShift: true, //optional
    speedMult: {x:1, y:1}, //optional
    hero: "magmax", //optional
    victory: true, //optional
    deathTimer: 60, //optional
    areaL: 0, //optional
    areaR: 2, //optional
    areaN: 1, //optional
    maxRadius: 50, //optional
    lighting: { //optional
      lighting: 1, //brightness of the area
      smoke: 0.1, //smoke strength
      color: [0, 255, 0] //color of the smoke and lighting
    }
  },
  "1": {
    "properties":{//optional 
      //and everything inside is optional
      //you can use every property except index here
    },
    "enemies": [
      {
        type: "switch",
        amount: 10,
        radius: 5,
        speed: 5,
        aditional:{//this and everything inside is optional
          switchTime: 2000,//works only if the enemy type incudes switch
          auraSize: 200,//works only if the enemy that has an aura / tracks the distance to be enabled (mine, neko, e.t.c.)
          bouncyP: 40,//the power that pushes the player from the bouncy enemy, default 40
          bouncyE: 1,//the power that pushes the bouncy enemy, default 1
          rof: 2000,//rate of fire for snipers
          startReload: 2000,//pause before first sniper shot
          angleIncrement: 1,//how fast do the homing enemies turn
        },
        spawnerData:[{//optional
          spawnerTime:1000,
          spawnerTimer:0,//optional
          pauseInterval:0,//optional
          pauseIntervaler:0,//optional if pauseInterval
          pauseDuration:0,//if pauseInterval
          type: "normal",
          radius: 5,
          speed: 5,
          life:2000,
        }]
      }
    ],
    "zones":[//optional
      {
        type: "wall",
        texture: "normal",//optional
        x: 0,
        y: 0,
        width: 1,
        height: 1,
        enemyCollide:false,//optional
        switched: true,//optional
        switchTime: 1000,//optional
        switchTimer: 1000,//optional
        path: [[0,0,0]],//optional
        safe: false,//optional
        walkable: false,//tp type only | optional
        tpTo:[0, 0],//tp type only | optional between this and V
        tpBy:[0, 0],//tp type only | optional between this and ^
        speedEffect: 1,//speed type only | optional
      },
    ]
  }
}
```

# Properties
* **width** - width of the enemy zone in tiles  
  `default: 80`
* **height** - height of the enemy zone in tiles  
  `default: 15`
* **index** - ###  
  `default: decided by devs`
* **disableAbilities** - disable the usage of abilities (including pasives)  
  `default: false`
* **canShift** - allow the player to shift, note: *affects mouse movement*  
  `default: true`
* **speedMult** - the speed is being multiplied by the given numbers  
  `default: {x: 1, y: 1}`  
  `2x slower: {x: 0.5, y: 0.5}`  
  `2x faster: {x: 2, y: 2}`  
  `l/r only: {x: 1, y: 0}`  
* **hero** - the that is going to be used in the areas  
  `default: undefined`  
* **victory** - wether the area is displayed as victory or no  
  `default: false`  
  `valid: Bool`  
* **deathTimer** - death timer in seconds  
  `default: 60`  
  `valid: Number`  
* **areaL** - are you get teleported to if you go to the left portal  
  **areaR** - are you get teleported to if you go to the right portal  
  `default: areaNumber ± 1`  
  `valid: Number / String`  
* **areaN** - the area stats you have in the area. e.g, if 1, energy = 30, regen = 1  
  `default: areaNumber`  
  `valid: Number`  
* **maxRadius** - the max radius that can be reached by `paladin`. May be used for other heroes later too  
  `default: Infinity`  
  `valid: Number`  
* **lighting** - the lighting of an area  
  `default: undefined`  
  `valid: {lighting: 1, smoke: 0.1, color: [0, 255, 0]}`
  `where`
  * `lighting` - brightness of the area
  * `smoke` - smoke strength
  * `color` - color of the smoke and lighting in RGB format


# Enemy Data
* **type** - the type of the enemy  
  `valid: "type" | ["type1", "type2"]`
* **amount** - the count of enemies  
  `valid: Number`
* **radius** - the radius of the enemy  
  `valid: Number`
* **speed** - the speed of the enemy  
  `valid: Number`
* **angle** - the angle of the enemy  
  `default: none`  
  `valid: Number`
* **x | y** - spawn position in pixels  
  `default: none`  
  `valid: Number`
* **tx | ty** - spawn position in tiles  
  `default: none`  
  `valid: Number`
* **path** - the path of the `path` enemy in tiles and `path2` enemy in pixels  
  `default: none`  
  `valid: [[x: Number, y: Number, speed: Number]]`  
  `example: [[1, 1, 2], [4, 4, 2]]`
* **aditional** - additional data  
  `default: none`  
  `valid: {see Additional}`
* **spawnerData** - the spawner of the enemy  
  `default: none`  
  `valid: [{see Spawner data}]`
  
Additional
--
* **switchTime** - time required for the enemy to switch  
  `default: depends on emeny type`
* **auraSize** - the size of an aura  
  `default: depends on emeny type`
* **bouncyP** - the power that pushes the player from the bouncy enemy  
  `default: 40`
* **bouncyE** - the power that pushes the bouncy enemy  
  `default: 1`
* **rof** - rate of fire for snipers  
  `default: depends on emeny type`
* **startReload** - pause before first sniper shot  
  `default: random between 0 and rof`
* **angleIncrement** - how fast do the homing enemies turn  
  `default: 1`


Spawner data
--
* **type | speed | radius | angle | x | y | tx | tx** are the same as in Enemy data
* **rangle** - the angle depenging on the parent enemy  
  `default: none`  
  `valid: Number`
* **spawnerTime** - the interval of the new enemy creation  
  `valid: Number`
* **spawnerTimer** - the offset of the Timer
  `default: spawnerTime`  
  `valid: Number`  
* **pauseInterval** - the interval of the next pause starting from the last pause
  `default: spawnerTime`  
  `valid: Number`  
* **pauseIntervaler** - the offset of the pause Interval
  `default: spawnerTime`  
  `valid: Number`  
* **pauseDuration** - the duration of the pause
  `default: spawnerTime`  
  `valid: Number`
* **life** - the life of the new enemy  
  `valid: Number`

Zones data
--
* **type** - the type of the zone  
  `default: "wall"`  
  `valid:`  
  * `"wall" - you cant get on top of it`  
  * `"tp" - when you touch it, you get teleported by the tpTo / tpBy`
  * `"lava" - kills you when you touch it. Can't get on top of it too.`
  * `"speed" - applies the speed effect`  
  `You can specifiy a non existing one if you dont wish to have any of the above effect.`
* **texture** - the way you see this tile.  
  `default: "normal"`  
  `valid:`
  * `"normal"`  *fff46c*, alpha 0.5  
  * `"wall"`  *000000*, alpha 1  
  * `"lava"`  *ff0000*, alpha 1  
  * `"speedm"`  *ff0000*, alpha 0.5  
  * `"speeda"`  *cyan*, alpha 0.5
  * `other`  *specified color*
* **x**, **y** - position  
  `default: 0`  
  `valid: Number`  
* **width**, **height** - size  
  `default: 1`  
  `valid: Number`  
* **enemyCollide** - whether enemies should collide with the wall and bounce off  
  `default: true if type = "wall"`  
  `valid: Bool`  
* **switched** - whether the zone is active. if its not, nothing will work on it  
  `default: true`  
  `valid: Bool`  
* **switchTime** - the time it takes to switch  
  `default: none`  
  `valid: Number`  
* **switchTimer** - the timers offset  
  `default: switchTime`  
  `valid: Number`  
* **path** - the path of its movement. it can take 3-4 arguments  
  `default: none`  
  `valid: [ [x, y, time, type] ]`  
  `meaning:`  
  * `x - left tile`
  * `y - top tile`
  * `time - number in miliseconds that it should take o move from current point to next`
  * `type - curreltly "m" (default) or "i".`  
    * `if "m" - tile moves from a to b depending on the % of time`  
    * `if "i" - when time reaches the end, it gets teleported to the end spot`
* **safe** - grants invincibility while on the tile  
  `default: false`  
  `valid: Bool`  
* **walkable** - evades 1 tile type. If you get teleported to this tile, you wont get teleported from the tiles untill yo go off from the teleport tile **or** touch a teleport tile that has it false.  
  `default: false`  
  `valid: Bool`  
* **tpTo** - teleportation to a spcific tile on touch  
  `default: none`  
  `valid: [x, y, area, world]`  
  `meaning:`  
  * `x, y - tile you will end up being teleported to`
  * `area - area you will get teleported to (optional)`
  * `world - world you will get teleported to (optional)`
* **tpBy** - moves you by specified amount   
  `default: none`  
  `valid: [x, y, area, world]`  
  `meaning:`  
  * `x, y - the position in tiles that you will be moved by`
  * `area - area you will get teleported to (optional)`
  * `world - world you will get teleported to (optional)`
* **speedEffect** - same as **speedMult** property   
  `default: none`  
  `valid: Number | {x:Number, y:Number}`  


Note
--
* **tx | ty | path(*path enemy*)** - the position is in the bottom-right of the tile, not the center of it. use `.5` to put it in the center.
* Non specified areas (missing areas) will always be victory. If there is no area after a missing area, you will get disconnected.  
  example: area `39, 40, 42, 43`. you will go 39 -> 40 -> victory -> 42 -> 43  
  example2: area `39, 40, 43, 44`. you will go 39 -> 40 -> victory -> death screen
* Spawner data may have a negative **spawnerTimer**. The enemies will be created as if the spawner was producing them for *N(-specified)* ms.

# All enemies

```css
aaaa
amogus
backdash
B.A.L.L
become
blackhole
blind
bouncy
burning
cancer
corrosive
creeper
dasher
dasherswitch
diagonal
disabled
disabler
draining
evilfrog
eviljumper
evilsnake
freezing
frog
glitch
glitchednormal
growing
halfswitch
homing
homingswitch
ice octo
ice sniper
icicle
immune
immunecorrosive
immunecorrosiveless
immunecorrosivenoshift
immunecorrosivenoshifthuge
immunedisabler
immunefreezing
immunepull
immunepush
invert
invisible
jumper
lag
latch
liquid
lmao
megaDraining
megafreezing
megapull
mine
movekill
nebula
neko
normal
noshift
nut
octo
ok
oscillating
outside
path
path2
permafrost
pull
push
quarterswitch
rain
reallyglitchednormal
regen sniper
retracing
scared
seizure
seizureswitch
sidestep
sidewarp
sideways
sizing
sliding
slippery
slowdrainswitch
slower
snake
sneaky
sniper
soldier
speed sniper
spiral
steam
stopkill
stopmoveswitch
stutter
subzero
sweepu
switch
tetar
tired
tornado
tp
transangle
trap
trolled
turning
ultraspiral
wall
wallsprayer
warp
water
wavy
wind
wipeu
wipeu2
yeet
zigzag
zoning
```
