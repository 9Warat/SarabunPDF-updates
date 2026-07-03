# SarabunPDF — Update feed

ที่เก็บ **สาธารณะ** สำหรับไฟล์อัปเดตของโปรแกรม SarabunPDF เท่านั้น (ไม่มีซอร์สโค้ด)
โปรแกรมจะอ่าน `update.xml` ผ่าน raw URL:

```
https://raw.githubusercontent.com/9Warat/SarabunPDF-updates/main/update.xml
```

## วิธีปล่อยเวอร์ชันใหม่
1. Build ตัวติดตั้ง `SarabunPDF_Setup.exe`
2. สร้าง GitHub Release ในรีโปนี้ แล้วแนบไฟล์ `SarabunPDF_Setup.exe` เป็น asset
3. แก้ `update.xml`: เพิ่ม `<version>` (เช่น `1.1.0.0`) ให้สูงกว่าเวอร์ชันที่ผู้ใช้ติดตั้ง
4. เสร็จ — ผู้ใช้กด "ตรวจสอบการอัปเดต" จะเห็นเวอร์ชันใหม่และติดตั้งได้

> `<version>` ต้องตรงกับ `<Version>` ใน `SarabunPDF.csproj` ของแต่ละรุ่น
