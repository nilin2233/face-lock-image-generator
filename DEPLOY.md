# คู่มือเอาขึ้นเว็บเพื่อส่งลิงก์ให้คนอื่นใช้

## ทางที่ง่ายสุด: Vercel

เหมาะกับ Next.js app ตัวนี้ที่สุด เพราะอัปโหลดโปรเจกต์แล้วได้ลิงก์เว็บสำหรับแชร์ต่อ

## ขั้นตอนแบบไม่ซับซ้อน

### 1) สร้าง GitHub Repository

1. เข้า GitHub
2. กด New repository
3. ตั้งชื่อ เช่น `face-lock-image-generator`
4. Upload ไฟล์ทั้งหมดในโฟลเดอร์โปรเจกต์นี้ขึ้น GitHub
5. ห้ามอัปโหลดไฟล์ `.env.local` เด็ดขาด

### 2) Deploy ด้วย Vercel

1. เข้า Vercel
2. กด Add New Project
3. เลือก GitHub repository ที่อัปโหลดไว้
4. Framework ควรเป็น Next.js อัตโนมัติ
5. กด Deploy

### 3) ตั้งค่า Environment Variables ใน Vercel

ไปที่ Project Settings → Environment Variables แล้วเพิ่ม:

```env
OPENAI_API_KEY=sk-xxxxxxxx
IMAGE_MODEL=gpt-image-1
SHARE_PASSWORD=ตั้งรหัสที่อยากให้คนอื่นใช้
```

แนะนำให้ตั้ง `SHARE_PASSWORD` เช่น:

```env
SHARE_PASSWORD=nlin2026
```

จากนั้นกด Redeploy อีกครั้ง

### 4) ส่งลิงก์ให้คนอื่น

หลัง Deploy เสร็จ Vercel จะให้ลิงก์ประมาณ:

```text
your-project-name.vercel.app
```

ส่งลิงก์นี้ + รหัสเข้าใช้งานให้คนอื่นได้เลย

## ข้อควรระวัง

- อย่าส่ง OpenAI API Key ให้ใคร
- อย่าเอา API key ไปใส่ในหน้าเว็บฝั่ง client
- ถ้าจะเปิดให้ลูกค้าใช้จริง ควรเพิ่มระบบสมาชิก / จำกัดเครดิต / จำกัดจำนวนภาพต่อวัน
- ถ้าเริ่มมีคนใช้เยอะ ควรทำระบบคิดเงินหรือเติมเครดิตก่อน
