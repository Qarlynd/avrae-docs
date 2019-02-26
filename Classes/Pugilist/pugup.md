# pugup
*By Qarlynd#2096.*

assuming no multiclass
sets the cvar PugilistLevel
and the cc's for moxie and Hit Dice

### Usage
`!pugup`



### Code
```c
!alias pugup embed
{{set_cvar("PugilistLevel" , int(level))}}
{{m,h="Moxie","Hit Dice (d8)"}}
{{cm,ch=cc_exists(m),cc_exists(h)}}
{{delete_cc(m) if cm else ""}}
{{create_cc_nx(m, 0, int(level)//2+1, "short", "bubble")}}
{{delete_cc(h) if ch else ""}}
{{create_cc_nx(h, 0, int(level))}}
-title "<name> updated"
-desc "<name> is now a level {level} Pugulist"
-f {{m+"|"+cc_str(m)}}
-f {{"'Hit Dice (d8)'|"+cc_str(h)}}
```
