## DUMP SETUP1 .so

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

[ສຳເລັດ](#ສຳເລັດ)

**หากต้องการดูเฉพาะส่วน เนื้อหา . 5o (เช่น ชื่อฟังก์ชันหรือ สตริงที่ใช้ในไฟล์):
• ดูเฉพาะสตริง:**

```
strings libInjected.so > /storage/emulated/0/MODFF/libInjected_strings.txt
```

**ເບິ່ງສ່ວນຫົວຂອງໄຟລ໌**
```
readelf -h libInjected.so > /storage/emulated/0/MODFF/libInjected_headers.txt
```

