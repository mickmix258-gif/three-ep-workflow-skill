# EP3 • BUILD: การเปลี่ยนโจทย์หน้างานเป็น PRD และ Internal App

เป้าหมายของ EP3 คือการต่อยอดจากการสร้างเอกสาร ไปสู่การสร้าง **"ระบบและเครื่องมือใช้งานจริงภายในทีม"** โดยแปลงความต้องการทางธุรกิจให้เป็นซอฟต์แวร์ที่พร้อม Deploy

---

## 1. วงจรการพัฒนาใน EP3 (Build Lifecycle)

```text
[ปัญหาหน้างาน / Pain Point]
          │
          ▼
[1. วิเคราะห์ & ร่าง PRD] ─── สเปกฟังก์ชัน, User Stories, Acceptance Criteria
          │
          ▼
[2. สถาปัตยกรรม & ฐานข้อมูล] ─── Data Schema, API Contracts, Security Boundaries
          │
          ▼
[3. สร้าง Internal Application] ─── Web UI, Automation Script, Dashboard
          │
          ▼
[4. Deploy & ใช้งานจริงในทีม] ─── สมาชิกในทีมใช้งานได้ทันทีโดยไม่ต้องเขียนโค้ด
```

---

## 2. แม่แบบเอกสาร PRD มาตรฐาน (PRD Template)

เมื่อได้รับโจทย์จากผู้ใช้ ให้ใช้โครงสร้าง PRD นี้ในการสรุปข้อกำหนด:

```markdown
# Product Requirement Document (PRD): [ชื่อระบบ/ฟีเจอร์]

## 1. Executive Summary & Objective
- **ปัญหาหลัก (Problem Statement):** [อธิบายปัญหาที่พบในปัจจุบัน]
- **เป้าหมาย (Objective):** [สิ่งที่ระบบนี้จะแก้ ภายในกรอบเวลาและตัวชี้วัด]
- **ความสำเร็จที่วัดได้ (Success Metrics):** [เช่น ลดเวลาทำงานลง 50%, รองรับผู้ใช้ 500 คน]

## 2. Target Users & User Stories
- **ผู้ใช้งานหลัก (Persona):** [เช่น เจ้าหน้าที่ฝ่ายปฏิบัติการ, ผู้จัดการโครงการ]
- **User Story 1:** ในฐานะ [ผู้ใช้] ฉันต้องการ [การกระทำ] เพื่อ [ประโยชน์ที่ได้รับ]
- **User Story 2:** ในฐานะ [ผู้ตรวจสอบ] ฉันต้องการ [การกระทำ] เพื่อ [ประโยชน์ที่ได้รับ]

## 3. Functional Requirements
| ID | ฟังก์ชันการทำงาน | รายละเอียดความต้องการ | Acceptance Criteria |
| :---: | :--- | :--- | :--- |
| FR-01 | นำเข้าข้อมูล | รองรับการอัปโหลดไฟล์ Excel และ CSV | ข้อมูลเข้าฐานข้อมูลภายใน 3 วินาที |
| FR-02 | ประมวลผลอัตโนมัติ | สรุปยอดและตรวจสอบค่าผิดปกติ | แจ้งเตือนข้อผิดพลาดทันทีหากยอดไม่ตรง |
| FR-03 | ส่งออกรายงาน | สร้างรายงาน PDF และ Excel พร้อมส่ง | ฟอร์แมตถูกต้องตามมาตรฐานบริษัท |

## 4. Technical Architecture & Database Schema
- **Data Model:**
  - `Users` (id, name, role, department)
  - `Tasks` (id, title, status, assigned_to, created_at)
  - `Reports` (id, task_id, file_path, verified_by)
- **Integration Points:** เชื่อมต่อกับฐานข้อมูลภายในผ่าน REST API / SQL Connector

## 5. Deployment & Rollout Plan
- **Phase 1 (Day 1–30):** Prototype และทดสอบในทีมย่อย
- **Phase 2 (Day 31–60):** เปิดให้ทั้งแผนกใช้งาน พร้อมเก็บ Feedback
- **Phase 3 (Day 61–90):** ปรับจูนประสิทธิภาพและขยายผลทั่วทั้งองค์กร
```

---

## 3. การสร้างแอปพลิเคชันสำหรับทีมโดยไม่ต้องเขียนโค้ดพื้นฐาน (No-Code/Low-Code for Team)

1. **AI เป็น Engine:** ให้ AI รับหน้าที่เขียนโค้ด Backend, Logic, และ UI Components ทั้งหมด
2. **คนในทีมเป็น Product Owner:** สมาชิกในทีมทำหน้าที่ระบุความต้องการ ตรวจสอบ Acceptance Criteria และทดสอบการทำงาน
3. **Deploy ง่าย:** ติดตั้งบนเซิร์ฟเวอร์ภายในหรือรันผ่าน Local Environment พร้อมคำแนะนำการรันแบบขั้นตอนเดียว (One-click Run Script)
