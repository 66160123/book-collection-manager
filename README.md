# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript and enable type-aware lint rules. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

## book-collection-manager

# การติดตั้งและการเริ่มต้นใช้งาน

## สร้างโปรเจค React ใหม่ด้วย Vite
- npm create vite@latest book-collection-manager -- --template react
- cd book-collection-manager
- npm install

## ติดตั้ง dependencies ที่จำเป็น
- npm install react-router-dom axios

## รัน Project
- npm run dev


# การใช้งาน

## การเพิ่มหนังสือใหม่
1.ไปที่หน้า Book List
2.คลิกปุ่ม "เพิ่มหนังสือ"
3.กรอกข้อมูลหนังสือ เช่น
 - ชื่อหนังสือ (Title)
 - ผู้แต่ง (Author)
 -ปีที่พิมพ์ (Year)
 - หมวดหมู่ (Category)
 - สถานะ (Status) → อ่านแล้ว / กำลังอ่าน / จะอ่าน
 - URL รูปปกหนังสือ (ถ้ามี)
4.คลิกปุ่ม "บันทึก" เพื่อเพิ่มหนังสือลงในระบบ
5.ระบบจะนำทางกลับไปยังหน้า Book List และแสดงหนังสือที่เพิ่ม

## การแก้ไขหนังสือ
1.ไปที่หน้า Book List
2.เลือกหนังสือที่ต้องการแก้ไข
3.กดปุ่ม "แก้ไข"
4.ระบบจะพาคุณไปที่หน้า Edit Book พร้อมแสดงข้อมูลเดิมของหนังสือ
5.แก้ไขข้อมูลตามต้องการ
6.คลิก "บันทึก" → ระบบจะอัปเดตข้อมูลและกลับไปที่หน้า Book List

## การลบหนังสือ
1.ไปที่หน้า Book List
2.เลือกหนังสือที่ต้องการลบ
3.กดปุ่ม "ลบ"
4.ระบบจะถาม ยืนยันการลบ หรือไม่
5.หากกด "ยืนยัน" หนังสือจะถูกลบออกจากระบบ

## การค้นหาและกรองหนังสือ
1.ค้นหาหนังสือ
 - ใช้ ช่องค้นหา (Search Bar) ในหน้า Book List
 - พิมพ์ ชื่อหนังสือ แล้วระบบจะแสดงเฉพาะหนังสือที่ตรงกับคำค้นหา
2.การกรองหนังสือ
 - สามารถกรองหนังสือตาม หมวดหมู่ (Category) หรือ สถานะการอ่าน
 - ตัวกรองจะช่วยให้สามารถดูเฉพาะหนังสือที่ต้องการได้ง่ายขึ้น

## การดูรายละเอียดของหนังสือ
1.ไปที่หน้า Book List
2.คลิกที่ หนังสือที่ต้องการดู
3.ระบบจะแสดง รายละเอียดของหนังสือ
 - ชื่อหนังสือ
 - ผู้แต่ง
 - ปีที่พิมพ์
 - หมวดหมู่
 - สถานะ
 - คำอธิบาย- รูปปก (ถ้ามี)
4.สามารถ กด "แก้ไข" หรือ "ลบ" หนังสือได้จากหน้านี้

## การจัดการข้อมูลหนังสือด้วย LocalStorage
แอปนี้ ไม่ต้องใช้ฐานข้อมูล แต่ใช้ LocalStorage ในการเก็บข้อมูลหนังสือที่เพิ่มเข้ามา
 - เมื่อเพิ่ม/แก้ไข/ลบหนังสือ ระบบจะบันทึกข้อมูลลง LocalStorage
 - เมื่อลองปิดหน้าเว็บแล้วเปิดใหม่ ข้อมูลยังคงอยู่
 - ใช้ Custom Hook (useBooks.js) เพื่อจัดการการอ่าน/เขียนข้อมูล
