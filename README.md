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
    hero: "magmax" //optional
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
        }
      }
    ]
  }
}
```
# properties
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

additional
--
* **switchTime** - time required for the enemy to switch  
  `default: depends on emeny type`
* **auraSize** - the size of an aura  
  `default: depends on emeny type`
# all enemies

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
