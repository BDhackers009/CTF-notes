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

1. get SAM,SYSTEM hive from the DISK

2. samdump2 SYSTEM SAM

3. then decrypt the hash and get raw passwords

## Fix .gif file header using python

```
bandor = open('pro.gif', 'rb').read()
bandor = b"\x47\x49\x46\x38" + bandor
with open('pro_fixed.gif', 'wb') as fak:
    fak.write(bandor)
```
