## Get text from Ascii values/numbers.

awk '{ for(i=1;i<=NF;i++) printf("%c",$i); print "";  }' 

## Get image from .wav file using qsstv on linux machine.

1. pactl load-module module-null-sink sink_name=virtual-cable

2. pavucontrol # A GUI will pop-up, go to the "Output Devices" tab to verify that you have the "Null Output" device

3. qsstv # The program GUI will pop-up, go to "Options" -> "Configuration" -> "Sound" and select the "PulseAudio" Audio Interface

4. Back in the pavucontrol GUI, select the "Recording" tab and specify that QSSTV should capture audio from the Null Output

5. paplay -d virtual-cable message.wav

6. Auto Slant option must be checked

7. pactl list short modules | grep null

8. pactl unload-module 22 # replace 22 to the output of the previous command

## PNG Headers Hex values.

.PNG = 

IHDR =

IDAT =
IEND =

## decrypt a salted file with des3 enc scheme

openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123


## Get all hashed password from windows registry hives

### get SAM,SYSTEM hive from the DISK

1. samdump2 SYSTEM SAM

### Then decrypt the hash and get raw passwords

## Fix .gif file header using python

```
bandor = open('pro.gif', 'rb').read()
bandor = b"\x47\x49\x46\x38" + bandor
with open('pro_fixed.gif', 'wb') as fak:
    fak.write(bandor)
```

## Get Ascii Text output from whitespace
```
file_name = input("Enter Your File Name: ")

f = open(file_name, "r").read()
pro = ""
for bn in f:
	if ord(bn) == 32:
		pro += "0"
	else:
		pro += "1"

input_string=int(pro, 2);
 

Total_bytes= (input_string.bit_length() +7) // 8
 

input_array = input_string.to_bytes(Total_bytes, "big")
 
ASCII_value=input_array.decode()
print()
print()
print(ASCII_value)

```

## Extract audio from video using ffmpeg

1. ffmpeg -i sample.mp4 -q:a 0 -map a sample.mp3

## See all the comments of a GIF.
1. exiftool -a pro.gif | grep Comment.

or , using python

```
# Written by QaisQupti#5326
import imageio
def parse_comment_extension(gif_path):
    with imageio.get_reader(gif_path) as gif:
        for frame in gif:
            if "comment" in frame.meta:
                comment = frame.meta["comment"].decode("utf-8")
                print(comment)

parse_comment_extension("pro.gif")
```

## find hidden data from a PNG

```
zsteg -a legend.png
```
