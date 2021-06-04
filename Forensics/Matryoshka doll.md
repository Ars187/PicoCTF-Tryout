The file contains the flag hidden inside it. By using binwalk we can see there exists compressed zip data inside
```
$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22
```
Using the unzip command we get another doll image. Repeat this and we can get the flag
```
$ unzip dolls.jpg
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg 
$ unzip base_images/2_c.jpg
Archive:  base_images/2_c.jpg
warning [base_images/2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg
$ unzip base_images/3_c.jpg
Archive:  base_images/3_c.jpg
warning [base_images/3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg
$ unzip base_images/4_c.jpg
Archive:  base_images/4_c.jpg
warning [base_images/4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt
$ cat flag.txt
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}
```
Flag:`picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}`
