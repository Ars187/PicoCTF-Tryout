### Description
Files can always be changed in a secret way. Can you find the flag? cat.jpg

#### Hint
Look at the details of the file

We are given a jpg file cat.jpg
![cat](https://user-images.githubusercontent.com/71893695/120835886-8e5fde80-c582-11eb-8753-0ae579fd27f1.jpg)
 
In the hints it says to check the details of the file

After checking the metadata using exiftool
```
$ exiftool cat.jpg
ExifTool Version Number         : 11.88
File Name                       : cat.jpg
Directory                       : .
File Size                       : 858 kB
File Modification Date/Time     : 2021:06:03 18:58:56+05:30
File Access Date/Time           : 2021:06:03 18:59:03+05:30
File Inode Change Date/Time     : 2021:06:03 18:58:56+05:30
File Permissions                : rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
```
We can see the license has a base64 string as its value. Decoding it we get the flag 

Flag:`picoCTF{the_m3tadata_1s_modified}`
