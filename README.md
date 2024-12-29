## DUMP SETUP1

```
pkg update && pkg upgrade -y
pkg install binutils -y
pkg install coreutils -y
pkg install termux-storage-api -y
termux-setup-storage
```
**ຄວນສ້າງໂຟເດີເຊັ່ນ (/storage/emulated/0/MODFF)ເພື່ອແປງໄຟ**
```
mkdir -p /storage/emulated/0/MODFF
```

```
cd /storage/emulated/0/MODFF/
objdump -d libInjected.so > /storage/emulated/0/MODFF/libInjected_dump.txt
```

