## DUMP

หากไฟล์ libil2cpp.so อยู่ใน `/storage/emulated/0/gerena.mask/` และคุณต้องการ dump ไฟล์นี้ เพื่อวิเคราะห์หรือทำวิศวกรรมย้อนกลับ (Reverse Engineering) คุณสามารถทำได้ตามขั้นตอนด้านล่าง:


---

1. **ตรวจสอบตำแหน่งไฟล์**

ยืนยันว่าไฟล์อยู่ในตำแหน่งที่ระบุ:

```
cd /storage/emulated/0/gerena.mask/
ls
```

ควรเห็นไฟล์ libil2cpp.so ในรายการ



---

## 2. คัดลอกไฟล์ไปยังพื้นที่ที่เข้าถึงง่าย

ใช้คำสั่ง cp เพื่อคัดลอกไฟล์ไปยังโฟลเดอร์ $HOME ของ Termux:

```
cp libil2cpp.so $HOME
```
ตรวจสอบว่าไฟล์ถูกคัดลอกเรียบร้อยแล้ว:
```
cd $HOME
ls
```
---

## 3. ติดตั้งเครื่องมือที่จำเป็น

ติดตั้ง binutils เพื่อใช้งานคำสั่งวิเคราะห์ไฟล์:
```
pkg update
pkg install binutils
```
---

## 4. วิเคราะห์โครงสร้างไฟล์

ใช้ objdump เพื่อดูข้อมูลโครงสร้างไฟล์:
```
objdump -x libil2cpp.so
```
หรือใช้คำสั่ง readelf เพื่อดูข้อมูลเพิ่มเติม:
```
readelf -a libil2cpp.so
```
**ได้ครับ! หากคุณไม่มี PC และต้องการ dump ไฟล์ libil2cpp.so ไปยังโฟลเดอร์เดิม (/storage/emulated/0/gerena.mask/) คุณสามารถทำงานทั้งหมดผ่าน Termux ได้โดยใช้เครื่องมือใน Termux เอง:*

## 1. เตรียมความพร้อม

ยืนยันว่าไฟล์ libil2cpp.so อยู่ในตำแหน่งเดิม:
```
ls /storage/emulated/0/gerena.mask/
```
ควรมีไฟล์ libil2cpp.so อยู่


## 2. คัดลอกไฟล์มาวิเคราะห์ใน Termux

คัดลอกไฟล์มาไว้ใน $HOME (พื้นที่ของ Termux):
```
cp /storage/emulated/0/gerena.mask/libil2cpp.so $HOME
```

## 3. ติดตั้งเครื่องมือวิเคราะห์ใน Termux

ติดตั้ง binutils (สำหรับใช้ objdump หรือ readelf):
```
pkg update
pkg install binutils
```
ติดตั้ง radare2 (อีกเครื่องมือสำหรับวิศวกรรมย้อนกลับ):
```
pkg install radare2
```

## 4. วิเคราะห์และ Dump ไฟล์

ใช้ objdump:
ไฟล์ที่ได้ (dump_libil2cpp.txt) จะเป็นข้อมูล Assembly ที่ dump ออกมา


ใช้ radare2:

เปิดไฟล์เพื่อวิเคราะห์:
```
r2 -A libil2cpp.so
```
ใช้คำสั่งใน Radare2 เพื่อดูโครงสร้างหรือ dump ข้อมูล เช่น:

5. บันทึกไฟล์ที่ Dump กลับไปยังโฟลเดอร์เดิม

เมื่อคุณได้ไฟล์ที่ dump แล้ว (เช่น dump_libil2cpp.txt หรืออื่น ๆ) ให้คัดลอกกลับไปยังโฟลเดอร์เดิม:
```
cp dump_libil2cpp.txt /storage/emulated/0/gerena.mask/
```


---

ตัวอย่าง: Dump ทั้งไฟล์เป็น Binary ใหม่

หากคุณต้องการสร้างไฟล์ .so ที่ dump หรือแก้ไขแล้ว:

## 1. ใช้คำสั่ง dd เพื่อสร้างสำเนาใหม่:
```
dd if=libil2cpp.so of=/storage/emulated/0/gerena.mask/libil2cpp_dump.so
```

## 2. ตรวจสอบว่าไฟล์ถูกสร้างในโฟลเดอร์เดิม:
```
ls /storage/emulated/0/gerena.mask/
```
