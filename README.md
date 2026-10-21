# Three-EP Workflow Skill (Enterprise AI Framework: Co-Worker, Context System, Build)

[![Antigravity Compatible](https://img.shields.io/badge/Antigravity-Skill-blue.svg)](https://github.com/mickmix258-gif/three-ep-workflow-skill)
[![Framework](https://img.shields.io/badge/Framework-3--EPs-green.svg)](https://github.com/mickmix258-gif/three-ep-workflow-skill)
[![License](https://img.shields.io/badge/License-MIT-purple.svg)](LICENSE)

ชุดสกิลสำหรับ Antigravity ที่ออกแบบมาเพื่อเปลี่ยนผ่านการใช้งาน AI จากการเป็นเพียง "แชทบอทถาม-ตอบทั่วไป" ไปสู่การเป็น **"ระบบเพื่อนร่วมงานและเครื่องยนต์พัฒนานวัตกรรมภายในองค์กร"** อย่างเป็นรูปธรรมตามหลักสูตรและมาตรฐาน Framework 3 EPs

---

## 1. รายละเอียดสกิล (Skill Overview)

### สกิลนี้คืออะไร?
`three-ep-workflow` คือชุดสกิลและแนวทางปฏิบัติระดับ Enterprise ที่แปลงการทำงานร่วมกับ AI ในองค์กรให้เป็นระบบแบ่ง 3 ช่วง (Episodes):
- **EP1 • CO-WORKER:** ทำงานกับไฟล์งานจริง เลิก Copy-Paste ผลลัพธ์พร้อมส่งต่องานทันที
- **EP2 • CONTEXT SYSTEM:** วางระบบบริบทองค์กรแบบหลายชั้นที่ใช้ซ้ำได้ ไม่ต้องเล่าใหม่ทุกครั้ง
- **EP3 • BUILD:** เปลี่ยนปัญหาหน้างานให้กลายเป็น PRD และซอฟต์แวร์หรือ Internal App ใช้งานจริงในทีม

### มีหน้าที่ทำอะไร?
- กำหนดให้ AI จัดการไฟล์ต้นฉบับและสร้างไฟล์ปลายทางโดยตรง (`.docx`, `.xlsx`, `.pptx`, `.csv`)
- กำกับมาตรฐานคุณภาพผ่าน **Agent Supervisor Architecture** ก่อนส่งมอบ
- จัดระเบียบคลังความรู้และบริบทการทำงานของทีมแบบ 3 ระดับ (3-Tier Layering)
- แปลงความต้องการทางธุรกิจ (Business Requirements) เป็นเอกสาร Product Requirement Document (PRD), Database Schema และแอปพลิเคชันต้นแบบ

### แก้ปัญหาจุดไหน?
1. **การ Copy-Paste ไปมา:** ลดเวลาและความผิดพลาดจากการต้องก๊อปปี้ข้อความไปจัดหน้ารีฟอร์แมตเองใน Word หรือ Excel
2. **Context Amnesia & Token Waste:** แก้ปัญหาต้องพิมพ์เล่าภูมิหลังบริษัทใหม่ทุกครั้งที่เปิดห้องแชท ด้วยระบบ Context Template ที่นำมา Reusable ได้
3. **ติดหล่มอยู่แค่ระดับเอกสาร:** ช่วยให้ทีมข้ามขีดจำกัดจากการสร้างแค่ข้อความ ไปสู่การสร้างเครื่องมือ ซอฟต์แวร์ และแอปพลิเคชันใช้งานจริงภายในองค์กร

---

## 2. หลักการวิเคราะห์และที่มา (Core Principles & Analysis)

### แนวคิดเบื้องหลัง (Core Philosophy)
ในองค์กรยุคใหม่ พนักงานไม่ได้ต้องการแชทบอทมาตอบคำถามทั่วไป แต่ต้องการ **"เพื่อนร่วมงานอัจฉริยะ (Digital Coworker)"** ที่เข้าใจบริบทองค์กร และมีความสามารถในการสร้างชิ้นงานที่พร้อมใช้งานทันที (Forward-ready)

```text
+-------------------+       +--------------------+       +--------------------+
|  EP1 • CO-WORKER  | ----> |   EP2 • CONTEXT    | ----> |    EP3 • BUILD     |
|                   |       |                    |       |                    |
| ทำงานกับไฟล์จริง      |       | วางชั้น Context    |       | เปลี่ยนโจทย์เป็น PRD|
| Word, Excel, PPT  |       | ระบบ Reusable      |       | ต่อ Database       |
| ส่งต่องานได้ทันที    |       | ไม่ต้องเล่าใหม่ทุกครั้ง|       | สร้าง App ใช้ในทีม   |
+-------------------+       +--------------------+       +--------------------+
```

### รายละเอียดหลักการทั้ง 3 เฟส:

#### 1. EP1: Co-Worker (ทำงานกับไฟล์จริง & ส่งต่องานได้ทันที)
- **Direct File Manipulation:** อ่านและเขียนไฟล์ลงระบบโดยตรง ควบคุมฟอนต์ ตาราง และรูปแบบตามข้อกำหนด
- **Agent Supervisor:** มีเอเจนต์ตรวจสอบความถูกต้อง (Verification Loop) ก่อนยืนยันการเสร็จสิ้นของงาน
- **Forward-Ready Standard:** ผลงานต้องมีคุณภาพระดับนำไปใช้ในที่ประชุมหรือส่งให้ลูกค้าได้ทันที

#### 2. EP2: Context System (ระบบบริบทองค์กร 3 ระดับ)
- **Level 1 (Company Standard):** ค่านิยม พันธกิจ กฎความปลอดภัย นโยบายข้อมูลส่วนบุคคล
- **Level 2 (Team / Project Domain):** สเปกผลิตภัณฑ์ ลูกค้าเป้าหมาย ตัวชี้วัด KPIs
- **Level 3 (Task Specific):** ข้อกำหนดเฉพาะของงานชิ้นนั้น ๆ
- **Progressive Disclosure:** โหลดเฉพาะส่วนบริบทที่จำเป็นเพื่อประหยัด Token และรักษาความแม่นยำ

#### 3. EP3: Build (สร้าง Internal Application & PRD จากโจทย์จริง)
- **Pain Point to PRD:** วิเคราะห์ปัญหาหน้างาน แปลงเป็น User Stories และ Acceptance Criteria
- **Database & Architecture:** ออกแบบโครงสร้างตารางข้อมูลและ REST API
- **Deployment:** ส่งมอบแอปพลิเคชันหรือสคริปต์อัตโนมัติที่คนในทีมเปิดใช้งานได้ทันที

---

## 3. ขั้นตอนและสถาปัตยกรรมการสร้าง (Implementation & Architecture)

### โครงสร้างไฟล์ในสกิล
```text
.
├── SKILL.md                                 # ข้อกำหนดสกิลหลัก (Instructions & Architecture)
└── references/
    ├── ep1-coworker.md                      # คู่มือการทำงานกับไฟล์จริง และ Agent Supervisor
    ├── ep2-context.md                       # การจัดโครงสร้าง Context 3 ระดับ
    ├── ep3-build.md                         # วงจรพัฒนา PRD, Database Schema และ Internal App
    └── 100-prompts-library.md               # คลัง 100 คำสั่งยอดนิยมแยกตาม 10 หมวดหมู่และ 3 EPs
```

### การจัดหมวดหมู่คลัง 100 คำสั่ง (100 Prompts Mapping)
สกิลนี้รวบรวมและจัดกลุ่ม 100 คำสั่งยอดนิยมให้สอดคล้องกับแต่ละ EP:
- **หมวด 1 (Writing & Proofreading):** จัดอยู่ใน EP1: Co-Worker
- **หมวด 2 (Creative Writing & Storytelling):** จัดอยู่ใน EP3: Build
- **หมวด 3 (Summarization & Synthesis):** จัดอยู่ใน EP1: Co-Worker
- **หมวด 4 (Research & Analysis):** จัดอยู่ใน EP2: Context System
- **หมวด 5 (Productivity & Organization):** จัดอยู่ใน EP1: Co-Worker
- **หมวด 6 (Coding & Technical Tasks):** จัดอยู่ใน EP3: Build
- **หมวด 7 (Learning & Skill Development):** จัดอยู่ใน EP2: Context System
- **หมวด 8 (Communication & Interpersonal):** จัดอยู่ใน EP1: Co-Worker
- **หมวด 9 (Business & Marketing):** จัดอยู่ใน EP2: Context System
- **หมวด 10 (Decision Making & Problem Solving):** จัดอยู่ใน EP3: Build

---

## 4. วิธีติดตั้งและใช้งานใน Antigravity (Installation & Usage)

### วิธีที่ 1: ติดตั้งใน Workspace โปรเจกต์
```bash
# Clone repository
git clone https://github.com/mickmix258-gif/three-ep-workflow-skill.git

# สร้างโฟลเดอร์สำหรับ skills
mkdir -p .agents/skills/

# นำสกิลไปวางใน .agents/skills/three-ep-workflow
cp -r three-ep-workflow-skill .agents/skills/three-ep-workflow
```

### วิธีที่ 2: ติดตั้งเป็น Global Skill
```bash
mkdir -p ~/.gemini/antigravity/builtin/skills/
cp -r three-ep-workflow-skill ~/.gemini/antigravity/builtin/skills/three-ep-workflow
```

### ตัวอย่างการสั่งการใน Antigravity Chat
- *"ช่วยสรุปเอกสารผลประกอบการนี้ แล้วเขียนรายงานสรุปผลพร้อมตารางวิเคราะห์ลงไฟล์ Word (.docx) ตามแนวทาง EP1 Co-worker"*
- *"ออกแบบโครงสร้าง Context Layering 3 ระดับสำหรับทีมการตลาดเพื่อใช้ซ้ำตามหลัก EP2"*
- *"เปลี่ยนปัญหาการเบิกจ่ายล่าช้าของฝ่ายบัญชีให้กลายเป็นเอกสาร PRD และสเปก Database สำหรับสร้าง Internal Web App ตามหลัก EP3 Build"*
