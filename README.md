# SarabunPDF — Update feed

ที่เก็บ **สาธารณะ** สำหรับไฟล์อัปเดตของโปรแกรม SarabunPDF เท่านั้น (ไม่มีซอร์สโค้ด)

โปรแกรม (ตั้งแต่ v3.5.1) อ่าน `update.xml` ผ่าน **GitHub Pages (CDN)** ซึ่งเสถียรและไม่ติดลิมิต 429:

```
https://9warat.github.io/SarabunPDF-updates/update.xml
```

> URL แบบ raw (`raw.githubusercontent.com/.../update.xml`) ยังใช้งานได้เป็น fallback แต่เคยเจอ HTTP 429 เมื่อหลายเครื่องใช้ IP เดียวกัน จึงย้ายค่าเริ่มต้นมาที่ Pages · ค่านี้อยู่ในไฟล์ `update.txt` ข้าง .exe (แก้ได้ หรือ override ด้วย env `SARABUNPDF_UPDATE_URL`)

**เวอร์ชันล่าสุดบนฟีด: `4.0.1.0`**

## วิธีปล่อยเวอร์ชันใหม่
1. Build ตัวติดตั้ง แล้วเปลี่ยนชื่อ asset ให้เป็น `SarabunPDF_Setup.exe` เป๊ะ (เพื่อให้ `releases/latest/download/...` ทำงาน)
2. สร้าง GitHub Release ในรีโปนี้ แล้วแนบ `SarabunPDF_Setup.exe` เป็น asset
3. แก้ `update.xml`: ตั้ง `<version>` (เช่น `3.5.5.0`) ให้สูงกว่าเวอร์ชันที่ผู้ใช้ติดตั้ง + เพิ่มบันทึกใน `CHANGELOG.md`
4. Push — Pages จะ rebuild ~1 นาที · ผู้ใช้กด "ตรวจสอบการอัปเดต" จะเห็นเวอร์ชันใหม่และติดตั้งได้

> `<version>` ต้องตรงกับ `<Version>` ใน `SarabunPDF.csproj` ของแต่ละรุ่น · commit เฉพาะ `update.xml` / `CHANGELOG.md` / `README.md` เท่านั้น (ห้ามใส่ไบนารี/ซอร์ส)
