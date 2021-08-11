# Startcodes FLSUN Q5

[flsun-q5-und-cura-grundeinstellungen](https://drucktipps3d.de/forum/topic/flsun-q5-und-cura-grundeinstellungen/#postid-115067)

der originale Code vom Q5 in der PC Version vom beigelegten Cura ist der hier


## Startcode

```
G21
G90
M82
M107 T0
M190 S{material_bed_temperature}
M109 S{material_print_temperature} T0
G28
G92 E0
G0 E3 F200
G92 E0
```

### QQ

```
G28 ;Home
G1 Z15.0 F6000 ;Move the platform down 15mm
;Prime the extruder
G92 E0
G1 F200 E3
G92 E0
```


## Endcode

```
M107 T0
M104 S0
M104 S0 T1
M140 S0
G92 E0
G91
G1 E-1 F300
G1 Z+0.5 E-5 X-20 Y-20 F9000
G28 X0 Y0
G90 ;absolute positioning
```

### QQ

```
M104 S0
M140 S0
;Retract the filament
G92 E1
G1 E-1 F300
G28 X0 Y0
M84
```

## Damit zuerst die Düse gereinigt wird, solltest du aber einen anderen Startcode benutzen

[micro SD card reader extension holder for flsun Q5](https://www.thingiverse.com/thing:4296243)


### Start G-code script (for cura/simplify3D):

```
G28 ;Home
M420 S1; load bed levelling mesh
G1 Z15.0 F6000 ;Move the platform down 15mm
;Prime the extruder
G92 E0 ; reset extrusion distance
G1 X-98 Y0 Z0.4 F3000 ; move to arc start
G3 X0 Y-98 I98 Z0.4 E40 F400 ; lay arc stripe 90deg
G92 E0 ; reset extrusion distance
G1 E-3
G1 X0 Y-50 Z4 E-2 F3000 ; get off the bed
G92 E0
```

