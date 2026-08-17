# FSA — Financial Statement Analysis (BS923102)

เว็บสรุปเนื้อหาวิชา Financial Statement Analysis สำหรับเตรียมสอบ Midterm
อาจารย์ผู้สอน: Asst Prof. Dr. Chamaiporn Kumpamool, PhD Finance

**เว็บไซต์:** https://poomiput.github.io/courseMidterm-FSA/

## ขอบเขตสอบ Midterm

จากโน้ตในเอกสาร CH5: **70 ข้อ · 4 ตัวเลือก · ใช้เครื่องคิดเลขได้ · อาจมีข้อสอบเป็นภาษาอังกฤษ**

| บท | ชื่อบท | ไฟล์ต้นฉบับ |
| --- | --- | --- |
| 2 | Financial Reporting Mechanics | `CH 2 FSA 1.68_Student.pdf` / `.md` |
| 3 | Financial Reporting Standards | `CH 3 FSA 1.69_Student.pdf` / `.md` |
| 4 | Understanding Financial Statements | `CH 4 FSA 1.69_Students.pdf` / `.md` |
| 5 | Financial Analysis Techniques | `CH 5 FSA 1.69_Student.pdf` / `.md` |

เอกสารต้นฉบับอยู่ที่ `C:\Users\AxisKing\Downloads\FSA\`

## Design system

โครงหน้าเว็บและ design system ยกมาจากโปรเจกต์ [internetwork-course](https://github.com/poomiput/internetwork-course)
ทุกอย่างอยู่ที่ `src/layouts/Layout.astro` ไฟล์เดียว — design token 13 ชุด + component class 21 ตัว
(`.card .knob .exam .cascade .tablewrap .fixnote .grid-2 .grid-3 .sec-head` ฯลฯ) พร้อมระบบ tooltip

ถ้าจะเอาไปทำวิชาอื่นอีก ให้ก๊อปโฟลเดอร์นี้แล้วแก้แค่ 6 จุด:

1. `src/layouts/Layout.astro` — default description + `<title>` suffix
2. `src/components/Sidebar.astro` — `units` array + ชื่อแบรนด์
3. `src/components/ComingSoon.astro` — ชื่อวิชา + จำนวนบท
4. `astro.config.mjs` — `base`
5. `src/pages/index.astro` — ปลายทาง redirect
6. `package.json` — `name`

แล้วลบ `src/pages/ch*.astro` กับเนื้อหาใน `src/data/terms.js` ออก

## Development

```bash
npm install
npx astro dev --background
```

จัดการ dev server ด้วย `npx astro dev status` / `logs` / `stop`

```bash
npm run build
```

Deploy อัตโนมัติทุกครั้งที่ push ขึ้น `main` ผ่าน GitHub Actions (`.github/workflows/deploy.yml`)
