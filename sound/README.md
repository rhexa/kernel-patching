## Useful Commands

- List sound card codec
```
grep Codec /proc/asound/card*/codec*
```
- List sound sources
```
arecord -l
amixer -c0 #Or the index of the arecord command instead of 0
pacmd list-cards
pacmd list-sources
pacmd list-source-outputs
```
- List module
```
lsmod | grep snd
```
- List modole model name
```
lspci -vnn
```
- Dmesg
```
sudo dmesg | grep snd
```

## sound patch

### Realtek ALC282 on Packard Bell Easynote

Work around to get headset microphone work on Packard Bell EasyNote TE69KB\
AMD E1-2500, Realtek ALC282.
```
echo "options snd-hda-intel model=headset-mic,dell-headset-multi" | \
sudo tee /etc/modprobe.d/audiomod.conf
```
