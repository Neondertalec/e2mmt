# template

```js
const MAP_NAME = {
  "properties": {//default for all areas
    width: 80,
    height: 15,
    index: 19,
    disableAbilities: false, //optional
    canShift: true, //optional
    speedMult: {x:1, y:1} //optional
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
          switchTime: 2000//works only if the enemy type incudes switch
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

# all enemies

```css
normal  
movekill  
stopkill  
corrosive  
outside  
immunecorrosive  
immunecorrosivenoshifthuge  
immunecorrosiveless  
immunecorrosivenoshift  
switch  
halfswitch  
quarterswitch  
seizureswitch  
disabled  
wall  
sizing  
wavy  
zigzag  
turning  
sniper  
octo  
icicle  
ice sniper  
ice octo  
tired  
pull  
push  
nebula  
blackhole  
megapull  
zoning  
speed sniper  
regen sniper  
immunedisabler  
immune  
immunepush  
immunepull  
immunefreezing  
dasher  
dasherswitch  
lag  
warp  
sidewarp  
cancer  
homing  
homingswitch  
tp  
snake  
evilsnake  
scared  
glitch  
growing  
trap  
aaaa  
path2  
diagonal  
wallsprayer  
liquid  
stutter  
permafrost  
water  
frog  
evilfrog  
yeet  
sideways  
transangle  
wipeu  
wipeu2  
sweepu  
nut  
blind  
tornado  
slower  
slippery  
sneaky  
draining  
megaDraining  
megafreezing  
soldier  
creeper  
mine  
jumper  
eviljumper  
disabler  
freezing  
subzero  
burning  
noshift  
invert  
spiral  
sidestep  
ultraspiral  
oscillating  
retracing  
rain  
path  
sliding  
backdash
```
