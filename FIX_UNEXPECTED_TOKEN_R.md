# แก้ Error: Unexpected token 'R' / Request Entity / Response Payload

สาเหตุที่เจอบ่อย:
- รูป reference ใหญ่เกิน
- ส่งรูปหลายรูปเกินไป
- ส่งภาพผลลัพธ์กลับมาทีเดียว 5 ภาพจน Vercel รับ/ส่ง payload ไม่ไหว

เวอร์ชันนี้แก้ให้แล้ว:
- ย่อรูป reference ฝั่ง browser ก่อนส่ง
- จำกัด reference สูงสุด 5 รูป
- สร้างภาพทีละ 1 รูป แล้วทยอยแสดงจนครบ 5 รูป
- เปลี่ยน output เป็น JPEG และบีบอัดไฟล์
- ถ้า server ตอบกลับมาเป็นข้อความ ไม่ใช่ JSON ระบบจะโชว์ error อ่านง่ายขึ้น

วิธีอัปเดต GitHub:
1. แตก ZIP นี้
2. เปิดเข้าไปในโฟลเดอร์ที่เห็น `app`, `public`, `package.json`
3. กด Ctrl + A เลือกทั้งหมด
4. ไป GitHub repo เดิม
5. กด Add file → Upload files
6. ลากไฟล์ทั้งหมดเข้าไป
7. กด Commit changes
8. กลับไป Vercel รอ Deploy ใหม่ หรือกด Redeploy

แนะนำทดสอบครั้งแรก:
- ใช้รูป reference 1 รูป
- จำนวนภาพ 1
- Quality = กลาง
ถ้าผ่านแล้วค่อยเพิ่มเป็น 5 ภาพ
