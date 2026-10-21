---
name: three-ep-workflow
description: >-
  กรอบการทำงาน Enterprise AI ตาม Framework 3 EPs (EP1: Co-worker, EP2: Context System, EP3: Build)
  ใช้เมื่อผู้ใช้ต้องการเปลี่ยนกระบวนการทำงานในทีมให้ทำงานร่วมกับ AI ด้วยไฟล์จริง (Word, PowerPoint, Excel),
  การจัดระบบบริบทองค์กรแบบหลายชั้น (Context Layering) ที่นำกลับมาใช้ซ้ำได้, การแปลงปัญหาหน้างานเป็นเอกสาร PRD,
  หรือการเชื่อมต่อฐานข้อมูลเพื่อสร้าง Internal Application ที่พร้อม Deploy ให้ทีมใช้งานจริง
---

# กรอบการทำงาน 3 EPs (Framework 3 EPs: Co-worker, Context System, Build)

สกิลนี้ออกแบบมาเพื่อเปลี่ยนผ่านการใช้งาน AI จากการเป็นเพียง "แชทบอทถาม-ตอบทั่วไป" ไปสู่การเป็น **"ระบบเพื่อนร่วมงานและเครื่องยนต์พัฒนานวัตกรรมภายในองค์กร"** อย่างเป็นรูปธรรมตามหลักสูตรและมาตรฐาน 3 EPs

---

## 1. ภาพรวมของสถาปัตยกรรม 3 EPs

```text
+-------------------+       +--------------------+       +--------------------+
|  EP1 • CO-WORKER  | ----> |   EP2 • CONTEXT    | ----> |    EP3 • BUILD     |
|                   |       |                    |       |                    |
| ทำงานกับไฟล์จริง      |       | วางชั้น Context    |       | เปลี่ยนโจทย์เป็น PRD|
| Word, Excel, PPT  |       | ระบบ Reusable      |       | ต่อ Database       |
| ส่งต่องานได้ทันที    |       | ไม่ต้องเล่าใหม่ทุกครั้ง|       | สร้าง App ใช้ในทีม   |
+-------------------+       +--------------------+       +--------------------+
```

| EP | ชื่อเฟส | วัตถุประสงค์หลัก | ผลลัพธ์ที่ส่งมอบ (Deliverables) |
| :--- | :--- | :--- | :--- |
| **EP1** | **CO-WORKER** | ทำงานร่วมกับไฟล์งานจริงในชีวิตประจำวัน เลิก Copy-Paste | เอกสารจริง (.docx, .pptx, .xlsx) ที่จัดรูปแบบพร้อมส่งต่อ |
| **EP2** | **CONTEXT SYSTEM** | วางระบบจัดเก็บและเรียกใช้บริบทองค์กรแบบเป็นชั้น | Reusable Context Template, Central Knowledge Layer |
| **EP3** | **BUILD** | แปลงปัญหาหน้างานเป็นซอฟต์แวร์และแอปพลิเคชันจริง | เอกสาร PRD, Database Schema, Internal Application |

---

## 2. ขั้นตอนการปฏิบัติการตามแต่ละ EP

### EP1: CO-WORKER (ทำงานกับไฟล์จริง & ส่งต่องานได้ทันที)
1. **เลิก Copy-Paste ลงแชท:** สั่งการให้ AI อ่านเอกสารต้นฉบับและเขียนผลลัพธ์ลงไฟล์ปลายทางโดยตรง
2. **ระบบ Agent Supervisor:** กำหนด Agent Supervisor ทำหน้าที่ตรวจสอบคุณภาพ ความถูกต้องของฟอร์แมต และความสอดคล้องกับมาตรฐานบริษัทก่อนส่งมอบงาน
3. **ความพร้อมส่งต่อ (Forward-ready):** ผลงานที่ AI ส่งมอบต้องมีโครงสร้าง ฟอนต์ สี และตารางที่พร้อมนำไปใช้งานหรือส่งต่อให้หัวหน้างาน/ลูกค้าทันที

> อ่านแนวทางปฏิบัติของ EP1 เพิ่มเติมได้ที่ [EP1 Co-worker Guide](./references/ep1-coworker.md)

---

### EP2: CONTEXT SYSTEM (ระบบบริบทที่ใช้ซ้ำได้ ไม่ต้องเริ่มใหม่)
1. **การจัดชั้น Context 3 ระดับ (3-Tier Layering):**
   - **Level 1 (Company Standard):** ค่านิยม พันธกิจ กฎระเบียบความปลอดภัย นโยบายข้อมูล
   - **Level 2 (Team / Project Domain):** สเปกผลิตภัณฑ์ ลูกค้ากลุ่มเป้าหมาย ตัวชี้วัดหลัก (KPIs / Baseline Metrics)
   - **Level 3 (Task Specific):** ข้อกำหนดเฉพาะของงานชิ้นนั้น ๆ
2. **Design Skill for Team:** ออกแบบ Skill และ Playbook ประจำทีม เพื่อให้สมาชิกทุกคนที่เรียกใช้ได้มาตรฐานเดียวกัน
3. **ลดความสูญเปล่าของ Token:** จัดเก็บเอกสารบริบทเป็นไฟล์อ้างอิง และโหลดเฉพาะส่วนที่จำเป็นด้วยระบบ Progressive Disclosure

> อ่านเทคนิคการวางเลเยอร์ Context เพิ่มเติมได้ที่ [EP2 Context Layering Guide](./references/ep2-context.md)

---

### EP3: BUILD (สร้าง Internal Application & PRD จากโจทย์จริง)
1. **แปลงปัญหาหน้างานเป็น PRD:** วิเคราะห์ปัญหาการทำงาน (Pain Point) และร่างเป็น Product Requirement Document ครบวงจร (User Stories, Acceptance Criteria, System Architecture)
2. **เชื่อมต่อฐานข้อมูล (Database Integration):** ออกแบบ Database Schema และสร้าง API / Query เชื่อมโยงข้อมูลอย่างปลอดภัย
3. **สร้างและ Deploy แอปในทีม:** พัฒนา Web Application หรือ Automation Script ภายในทีม เพื่อให้ทุกคนใช้งานได้โดยไม่ต้องมีพื้นฐานการเขียนโค้ด

> อ่านกระบวนการสร้างและเทมเพลต PRD ได้ที่ [EP3 Build Guide](./references/ep3-build.md)

---

## 3. การผูก 100 คำสั่งยอดนิยมกับ Framework 3 EPs

คำสั่งยอดนิยมทั้ง 100 คำสั่ง (10 หมวดหมู่) สามารถนำมาปรับใช้ภายใต้กระบวนการ 3 EPs:
- **หมวด 1, 7, 10 (Writing, Translation, Productivity):** ประยุกต์ใช้กับ **EP1** เพื่อผลิตเอกสารจริง
- **หมวด 4, 5, 6 (Analysis, Business, Education):** ประยุกต์ใช้กับ **EP2** เพื่อจัดทำ Knowledge Base และ Context System
- **หมวด 2, 3, 8, 9 (Creative, Coding, Brainstorming, Roleplay):** ประยุกต์ใช้กับ **EP3** เพื่อสร้างฟีเจอร์และ Internal Tools

> ดูสารบัญคำสั่งและเทมเพลต 100 ข้อได้ที่ [100 Prompts Library](./references/100-prompts-library.md)
