# คู่มือใช้งานแบบไม่ติดตั้งในเครื่อง

ไฟล์ชุดนี้ทำเป็นเว็บแอพไว้แล้ว ใช้ได้ 2 แบบ:

1. ใช้เป็นหน้าเว็บผ่านลิงก์ Vercel
2. หลังเปิดผ่านมือถือ/คอม สามารถกด Add to Home Screen / Install app เพื่อใช้งานเหมือนแอพได้

## สิ่งที่คุณต้องมี

- บัญชี GitHub
- บัญชี Vercel
- OpenAI API Key

ไม่ต้องติดตั้ง Node.js ในเครื่อง

## ขั้นตอน

### 1) อัปโหลดขึ้น GitHub ผ่านเว็บ

1. เข้า GitHub
2. กด New repository
3. ตั้งชื่อ เช่น `face-lock-image-generator`
4. กด Create repository
5. กด Add file → Upload files
6. ลากไฟล์และโฟลเดอร์ทั้งหมดในโปรเจกต์นี้ขึ้นไป
7. กด Commit changes

ห้ามอัปโหลดไฟล์ `.env.local` ถ้ามีอยู่ในเครื่อง

### 2) เอา GitHub ไปต่อกับ Vercel

1. เข้า Vercel
2. กด Add New → Project
3. เลือก repo ที่สร้างไว้
4. กด Deploy

### 3) ตั้งค่าคีย์ใน Vercel

เข้า Project Settings → Environment Variables แล้วเพิ่ม:

```env
OPENAI_API_KEY=sk-xxxxxxxx
IMAGE_MODEL=gpt-image-1
SHARE_PASSWORD=123456
```

จากนั้นกด Redeploy

### 4) ส่งลิงก์ให้คนอื่นใช้

Vercel จะให้ลิงก์ประมาณ:

```text
https://ชื่อโปรเจกต์.vercel.app
```

ส่งลิงก์ + รหัส `SHARE_PASSWORD` ให้คนอื่นได้เลย

## วิธีทำให้เหมือนแอพ

หลัง deploy แล้ว เปิดลิงก์ใน Chrome หรือ Edge

บนคอม:
- กดไอคอน Install app ที่แถบ URL ถ้ามี
- หรือเมนู browser → Install app

บนมือถือ:
- เปิดลิงก์ใน browser
- กด Share
- เลือก Add to Home Screen

## แนะนำเพื่อความปลอดภัย

- อย่าส่ง OpenAI API Key ให้ใคร
- เปลี่ยน SHARE_PASSWORD เป็นระยะ
- ถ้าให้คนใช้เยอะ ควรเพิ่มระบบจำกัดเครดิตต่อคน
