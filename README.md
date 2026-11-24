# STEMI Consult

เว็บแอปหน้าเดียวสำหรับ consult STEMI ระหว่างแพทย์ รพช. กับ cardiologist เน้นกด template เร็ว ๆ บนมือถือ แล้วคัดลอกข้อความไปส่งใน LINE

## ใช้งาน

เปิด `index.html` ในเบราว์เซอร์ได้เลย ไม่ต้องติดตั้งอะไร หรือเปิด GitHub Pages (Settings → Pages → Branch `main` / root) เพื่อให้ได้ลิงก์ส่งต่อ

## ฟีเจอร์

**ฝั่ง รพช. (ส่ง consult)**
- ข้อมูลผู้ป่วย, U/D, status เดิม, CC + onset/door time (คำนวณ PTA อัตโนมัติ), pain score
- V/S, BP 4 รยางค์ (เตือนเมื่อ SBP แขนต่างกัน > 20 mmHg)
- ตรวจร่างกาย, GCS, Killip class (มีค่าแนะนำ)
- EKG 12 leads + V7-9, V3R, V4R แบบแตะเลือก STE/STD → สร้างบรรทัด EKG, บอก territory และ Impression อัตโนมัติ
- คำเตือน: ยังไม่ทำ V7-9 / V3R-4R, RV infarct กับ NTG, STE aVR + diffuse STD, contraindication ของ fibrinolytic
- แนบรูป EKG / CXR และรวมเป็นภาพเดียวสำหรับส่งต่อ
- แถบแจ้งข้อมูลที่ยังขาด + ปุ่มคัดลอกข้อความ

**ฝั่ง Cardio (ตอบกลับ)**
- Dx, reperfusion plan, ยา, follow-up แบบกดเลือก แล้วคัดลอกข้อความตอบกลับ

## หมายเหตุ

- ข้อมูลเคสเก็บใน localStorage ของเครื่องผู้ใช้เท่านั้น ไม่มีการส่งไปเซิร์ฟเวอร์
- ไม่มีช่องชื่อ/HN ผู้ป่วยโดยตั้งใจ (PDPA)
- ขนาดยาและ checklist เป็นค่าเริ่มต้น ควรตรวจและปรับตาม protocol ของเครือข่าย
