# PicArd - Ultra-Low Cost PIC Programmer

## PicArd Hex Files Format (.pchx)

PicArd will handle Intel Hex files normally. But, for greater flexibility,
I decided to add custom codes:

|Code|Description| PicArd version
| :--- | :---|  :---|
| 06 | BandGap information | 0.41+|
| 07 | OSCCAL information |  0.41+|
| 08 | Calibration word(s) | 0.45+|

The Intel Hex syntax remains the same, for example:

```
:020000060010E8
 ||_______________number of bytes (0x02)
   ||||___________address ignored (0x0000)
       ||_________data type (0x06 = bandgap information)
	     ||||_____bandgap value (0x1000)
             ||___checksum (0xE8 - PicArd ignores it)
```

In pchx files, any line not starting with ":" is treated as a comment.

BandGap, OSCCAL and Calibration words must be read from PICs before operations
to avoid frequency or voltages miscalibration. PicArd will save the values into a 
special file (*osccals_bandgaps.txt*) and will try to restore them if necessary.

If an error occurs, you can use saved values into pchx file to restore factory defaults.


See *pic12f675_format_example.pchx* and *pic_16f886_format_example.pchx* for more 
details.
