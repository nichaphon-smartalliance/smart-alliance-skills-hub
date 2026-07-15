# Team Setup Prompt — Skills + Global CLAUDE.md

วางบล็อกล่างนี้ให้ Claude Code (วางทั้งก้อนได้เลย):

---

````text
ตั้งค่าเครื่องฉันให้ทำงานแบบนักพัฒนามืออาชีพ ทำ 3 ขั้นตามลำดับ:

## 1. ติดตั้ง skills
Clone 3 repo นี้แล้วก๊อปทุกโฟลเดอร์ skill (แต่ละอันมี SKILL.md) เข้า ~/.claude/skills/
- https://github.com/multica-ai/andrej-karpathy-skills   (karpathy-guidelines — ฐาน §0)
- https://github.com/obra/superpowers                    (กระบวนการวิศวกรรม — §1)
- https://github.com/thananon/9arm-skills                (debug/review/delegate — §2)
เสร็จแล้ว list โฟลเดอร์ยืนยันว่ามี SKILL.md ครบ

## 2. เขียน ~/.claude/CLAUDE.md ด้วยโครง 4 ส่วนนี้ (กระชับ — โหลดทุก session)
§0 Base rules (Karpathy, always-on, สูงสุด — จาก skill `karpathy-guidelines`, inline ไว้ให้
   ทำงานทุก session): think before coding / simplicity first / surgical changes /
   goal-driven + ห้ามบอกเสร็จโดยไม่มีหลักฐาน (รันโชว์ output)
§1 Superpowers (obra) — ตาราง "สถานการณ์ → skill": brainstorming, writing-plans,
   executing-plans, subagent-driven-development, test-driven-development,
   systematic-debugging, verification-before-completion, dispatching-parallel-agents,
   using-git-worktrees, requesting-code-review, receiving-code-review,
   finishing-a-development-branch, writing-skills, using-superpowers
§2 9arm-skills (thananon) — ตาราง "สถานการณ์ → skill": debug-mantra, scrutinize,
   post-mortem, management-talk, qwenchance, qwen-agent
   (qwen-agent ต้องมี backend `claude-9arm` — ถ้าไม่มีให้ใส่หมายเหตุ "skip until installed")
§3 Precedence: Direct user instructions > project CLAUDE.md > this file > skills > defaults

กติกา: หยิบ skill "ก่อน" ลงมือ (process skills วางแนวทางก่อน implementation ลงมือ) และ
ประกาศ `Using [skill] to [purpose]` — แต่ข้ามได้ถ้าเป็นงานจิ๊บจ๊อย/คำถามสั้นๆ
ในตารางให้ใส่เฉพาะ skill ที่ติดตั้งจริงในขั้น 1 เท่านั้น

## 3. Verify
อ่าน ~/.claude/CLAUDE.md กลับมาโชว์ + ยืนยันว่าไม่มีแถวไหนชี้ไป skill ที่ยังไม่ได้ติดตั้ง
แล้วสรุปสั้นๆ ว่าติดตั้งอะไรไปบ้าง
````

---

**ผลลัพธ์:** ทุก session จะทำงานด้วยวินัยเดียวกัน — reproduce บั๊กก่อนแก้, วางแผน+TDD ก่อนเขียน,
พิสูจน์ก่อนบอกเสร็จ, แก้เฉพาะจุด ไม่รื้อเกินเหตุ

> ปรับได้: อยากให้ตอบภาษาไทย/อังกฤษ หรือใส่ stack หลัก (Next.js / Spring Boot) ก็บอก Claude
> เพิ่มในขั้น 2 ได้เลย
