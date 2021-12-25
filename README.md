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
          auraSize: 200//works only if the enemy has an aura
        },
        spawnerData:[{//optional
          spawnerTime:1000,
          spawnerTimer:0,//optional
          type: "normal",
          radius: 5,
          speed: 5,
          life:2000,
        }]
      }
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
* **life** - the life of the new enemy  
  `valid: Number`

Note
--
* **tx | ty | path(*path enemy*)** - the position is in the bottom-right of the tile, not the center of it. use `.5` to put it in the center.
* Non specified areas (missing areas) will always be victory. If there is no area after a missing area, you will get disconnected.  
  example: area `39, 40, 42, 43`. you will go 39 -> 40 -> victoy -> 42 -> 43  
  example2: area `39, 40, 43, 44`. you will go 39 -> 40 -> victoy -> death screen
* Spawner data may have a negative **spawnerTimer**. The enemies will be created as if the spawner was producing them for *N(-specified)* ms.

# All enemies

```css
aaaa
backdash
blackhole
blind
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
jumper
lag
liquid
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
oscillating
outside
path
path2
permafrost
pull
push
quarterswitch
rain
regen sniper
retracing
scared
seizureswitch
sidestep
sidewarp
sideways
sizing
sliding
slippery
slower
snake
sneaky
sniper
soldier
speed sniper
spiral
stopkill
stopmoveswitch
stutter
subzero
sweepu
switch
tired
tornado
tp
transangle
trap
turning
ultraspiral
wall
wallsprayer
warp
water
wavy
wipeu
wipeu2
yeet
zigzag
zoning
```
