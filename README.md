# Electrical Engineering Mathematics LaTeX

เอกสารประกอบการสอนรายวิชา 5571102 คณิตศาสตร์วิศวกรรมไฟฟ้า จัดทำด้วย LaTeX และรองรับภาษาไทยด้วย XeLaTeX

## โครงสร้างโปรเจกต์

```text
electrical-math-latex/
├── main.tex
├── chapters/
├── images/
├── styles/
├── fonts/
├── outputs/
└── references/
```

## การ build

ใช้ XeLaTeX เท่านั้น เพราะเอกสารตั้งค่าฟอนต์ไทยผ่าน `fontspec` และ `polyglossia`

```sh
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```

รันสองรอบเมื่อเปิดสารบัญหรือมีการอ้างอิงภายในเอกสาร เพื่อให้เลขหน้าในสารบัญอัปเดตครบ

## การเลือกฟอนต์

เปลี่ยนฟอนต์ได้ที่ `main.tex`

```tex
\usepackage[cmprasanmit]{styles/custom}
```

ค่าที่รองรับ:

- `cmprasanmit` ใช้ฟอนต์ในโฟลเดอร์ `fonts/`
- `sarabun` ใช้ `TH Sarabun New` จากโฟลเดอร์ `fonts/` หรือจากฟอนต์ที่ติดตั้งในระบบ
- `auto` ให้เอกสารเลือกอัตโนมัติ โดยเรียงลำดับ `CmPrasanmit -> TH Sarabun -> Garuda`

## ไฟล์หลัก

- `main.tex` เป็น entry point ของเอกสาร
- `styles/custom.sty` รวมการตั้งค่าหน้ากระดาษ ฟอนต์ไทย สี กล่อง และรูปแบบโค้ด
- `chapters/ch2_complex_phasor.tex` เป็นเนื้อหาบทที่ 2 เรื่องจำนวนเชิงซ้อนและเฟสเซอร์
- `fonts/` เก็บฟอนต์ CmPrasanmit ที่ใช้เป็นฟอนต์หลักของเอกสาร
