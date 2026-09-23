# Ubuntu + LibreOffice: ชุดฟอนต์ไทยแบบ Lean

คู่มือนี้ใช้แนวคิด **Functional Minimalism**: เก็บเฉพาะฟอนต์ที่ระบบปฏิบัติการต้องใช้จริง ฟอนต์ fallback ที่จำเป็น และฟอนต์งานเอกสารราชการไทย ไม่ติดตั้งชุดฟอนต์ขนาดใหญ่เพียงเพราะมากับระบบหรือ LibreOffice

> ทดสอบแนวทางกับ Ubuntu 24.04 LTS / LibreOffice  
> หลักสำคัญ: **อย่าถอนฟอนต์แบบเหมารวม** และต้อง `--simulate` ก่อนทุกครั้ง

## เป้าหมาย

เครื่องใช้งานหลักเป็นภาษาไทย/อังกฤษ และ LibreOffice สำหรับเอกสารราชการ จึงแบ่งฟอนต์เป็น 3 ชั้น:

1. **System/UI + fallback** — ต้องมี เพื่อไม่ให้เมนูหรือภาษาไทยกลายเป็น □□□
2. **Office compatibility** — เก็บไว้เท่าที่จำเป็นสำหรับเปิดไฟล์จาก Microsoft Office
3. **Thai official documents** — ใช้ TH Sarabun New เป็นหลัก

---

## 1. ชุดที่ควรเก็บ

### System / UI

ควรเก็บอย่างน้อย:

- `fonts-noto-ui-core` — ฟอนต์ UI Unicode/fallback สำคัญ
- `fonts-noto-core` — Unicode core coverage
- `fonts-noto-mono` — monospace/fallback
- `fonts-dejavu-core` / DejaVu — ฟอนต์พื้นฐาน Linux
- `fonts-liberation` หรือ Liberation ที่ระบบติดตั้งอยู่

**บทเรียนจากเครื่องจริง:** ถอน `fonts-noto-ui-core` แล้วตัวอักษรบางส่วนกลายเป็นสี่เหลี่ยม จึงจัดแพ็กเกจนี้เป็น **KEEP** ไม่ใช่ของเกิน

ตรวจสถานะ:

```bash
dpkg -l | grep -E 'fonts-(noto|dejavu|liberation)'
```

ถ้าภาษาไทยกลายเป็นสี่เหลี่ยม ให้กู้ก่อน:

```bash
sudo apt update
sudo apt install fonts-noto-ui-core fonts-noto-core fonts-noto-mono
fc-cache -f -v
```

จากนั้น logout/login หรือ reboot หาก UI ยังไม่ refresh

---

## 2. ฟอนต์เอกสารราชการไทย

สำหรับเครื่องนี้ใช้ **TH Sarabun New** เป็นฟอนต์หลักในการพิมพ์เอกสารราชการ

ไฟล์ที่จำเป็นมีเพียง 4 style:

- THSarabunNew.ttf
- THSarabunNew Bold.ttf
- THSarabunNew Italic.ttf
- THSarabunNew BoldItalic.ttf

ติดตั้งเฉพาะผู้ใช้:

```bash
mkdir -p ~/.local/share/fonts/THSarabunNew
cp THSarabunNew*.ttf ~/.local/share/fonts/THSarabunNew/
fc-cache -f
```

ตรวจ:

```bash
fc-list | grep -i "TH Sarabun"
```

ฟอนต์ TH อื่นใน repository นี้เก็บไว้เป็นคลังได้ แต่ **ไม่จำเป็นต้องติดตั้งทุกตัวใน Ubuntu**

---

## 3. ฟอนต์ไทย TLWG ต้องลงไหม?

Ubuntu มีแพ็กเกจ `fonts-thai-tlwg` ซึ่งเป็น metapackage และจะดึงฟอนต์ไทยหลายตระกูล เช่น Garuda, Kinnari, Laksaman, Loma, Norasi, Purisa, Sawasdee, Waree ฯลฯ

สำหรับเครื่องที่ต้องการเพียง:

- UI ภาษาไทย
- เว็บภาษาไทย
- LibreOffice
- TH Sarabun New สำหรับงานราชการ

**ไม่จำเป็นต้องลง `fonts-thai-tlwg` ทั้งชุด** หาก Noto fallback และ TH Sarabun New ทำงานครบอยู่แล้ว

---

## 4. อะไรถือเป็น Extra และพิจารณาถอนได้

ตัวอย่างแพ็กเกจที่อาจไม่จำเป็นกับเครื่องไทย/อังกฤษ:

- `fonts-noto-cjk` — จีน ญี่ปุ่น เกาหลี
- `fonts-noto-cjk-extra`
- `fonts-noto-extra`
- `fonts-noto-ui-extra`
- ชุด TLWG ทั้งชุด หากไม่ได้ใช้ฟอนต์เหล่านั้น

แต่ **ห้ามสั่ง remove ทันที**

ตรวจว่ามีอะไรติดตั้งก่อน:

```bash
dpkg -l | grep '^ii.*fonts-'
```

แล้วจำลองการถอน เช่น:

```bash
sudo apt remove --simulate fonts-noto-cjk fonts-noto-cjk-extra fonts-noto-extra fonts-noto-ui-extra
```

อ่านรายการ `REMOVING:` ให้ครบ ถ้ามี desktop, LibreOffice, language support หรือแพ็กเกจสำคัญถูกลากออกมาด้วย ให้ **ยกเลิก**

เมื่อแน่ใจแล้วจึงถอนเฉพาะแพ็กเกจที่ไม่ใช้:

```bash
sudo apt remove <package-name>
sudo apt autoremove --simulate
```

อย่าเพิ่ง `autoremove` จริงจนกว่าจะตรวจรายการครบ

---

## 5. ฟอนต์ Office compatibility

ถ้ามี **Carlito** และ **Caladea** อยู่แล้ว แนะนำให้เก็บไว้ เพราะมีประโยชน์เวลาเปิดเอกสาร Office ที่สร้างจากเครื่องอื่น และขนาดตัวอักษรใกล้เคียงตระกูล Microsoft ที่พบบ่อย

หลักคือ **ไม่ต้องมีฟอนต์เยอะ แต่ต้องเปิดเอกสารคนอื่นแล้ว layout ไม่พังง่าย**

---

## 6. ตรวจหลัง Clean

ดูรายชื่อ family:

```bash
fc-list : family | sort -u
```

ทดสอบ fallback ภาษาไทย:

```bash
fc-match sans-serif
fc-match "sans-serif:lang=th"
fc-match "TH Sarabun New"
```

จากนั้นเปิด LibreOffice Writer ทดสอบ:

```text
ภาษาไทยทดสอบ ๑๒๓๔๕๖๗๘๙๐
ABCDEFGHIJKLMNOPQRSTUVWXYZ
TH Sarabun New — Regular / Bold / Italic / Bold Italic
```

ถ้าไทยแสดงครบ ไม่มี □□□ และ LibreOffice เห็น TH Sarabun New ถือว่าผ่าน

---

## 7. Golden Rule

> **อย่าถอนเพราะชื่อฟอนต์ดูเหมือนไม่ได้ใช้ — ถอนเมื่อรู้ว่า package ทำหน้าที่อะไร**

ลำดับมาตรฐาน:

```text
LIST → IDENTIFY → SIMULATE → REVIEW → REMOVE → FC-CACHE → TEST
```

เป้าหมายไม่ใช่ Ubuntu ที่มีฟอนต์น้อยที่สุด แต่เป็น Ubuntu ที่ **ไม่มีของเกิน และไม่ทำลาย fallback ของระบบ**

---

## ชุดเป้าหมายของเครื่องนี้

```text
KEEP
├── Noto UI/Core/Mono        ← system + Unicode fallback
├── DejaVu                   ← Linux base
├── Liberation              ← document compatibility
├── Carlito / Caladea       ← Office compatibility
└── TH Sarabun New (4 styles) ← เอกสารราชการไทย

OPTIONAL / REMOVE IF UNUSED
├── Noto CJK / CJK Extra
├── Noto Extra / UI Extra
├── TLWG font collection
└── decorative fonts
```

**หลักเดียว:** Core เล็ก เสถียร อ่านไทยได้ และพิมพ์เอกสารราชการได้ครบ


---

## 8. Minimal Font Policy — เป้าหมายให้ LibreOffice เลือกฟอนต์ง่าย

ปัญหาที่ต้องการแก้ไม่ใช่แค่พื้นที่ดิสก์ แต่คือ **Font menu pollution**: เมื่อติดตั้ง font collection จำนวนมาก LibreOffice จะแสดง family จำนวนมากจนต้องเลื่อนหารายการยาวเกินความจำเป็น

### กลุ่ม A — MUST KEEP: ระบบ Ubuntu / Browser / Terminal

บนเครื่องภาษาไทย-อังกฤษ ให้ถือกลุ่มนี้เป็นฐานและ **ไม่ถอนเพียงเพราะไม่ได้เลือกชื่อฟอนต์เอง**

- `fonts-noto-core` — Unicode core/fallback
- `fonts-noto-ui-core` — UI fallback; เครื่องจริงเคยถอนแล้วเกิด □□□ ใน Browser/UI
- `fonts-noto-mono` — monospace Unicode สำหรับ terminal/code
- `fonts-dejavu-core` — Linux base fonts
- `fonts-liberation` — metric-compatible base สำหรับเอกสาร

หลัก: package เหล่านี้เป็น infrastructure ของการแสดงผลมากกว่าฟอนต์ตกแต่ง

### กลุ่ม B — KEEP: เปิดเอกสาร Office จากคนอื่น

เก็บเท่าที่จำเป็น:

- `fonts-crosextra-carlito` — metric-compatible กับ Calibri
- `fonts-crosextra-caladea` — metric-compatible กับ Cambria (ถ้ามี/ใช้งานเอกสารลักษณะนี้)
- Liberation — รองรับเอกสารที่อิง Times/Arial/Courier metrics

กลุ่มนี้ช่วยลดโอกาส layout เอกสารจาก Windows เพี้ยน โดยไม่ต้องติดตั้ง font collection ขนาดใหญ่

### กลุ่ม C — USER FONT: งานราชการไทย

ติดตั้งเพียง:

- TH Sarabun New Regular
- TH Sarabun New Bold
- TH Sarabun New Italic
- TH Sarabun New Bold Italic

นี่คือชุดที่ผู้ใช้จะเลือกใน LibreOffice เป็นหลัก

### กลุ่ม D — OPTIONAL / REMOVE IF UNUSED

เครื่องไทย-อังกฤษที่ไม่ได้ทำงานหลายภาษา สามารถพิจารณาถอน:

- `fonts-noto-cjk` / CJK Extra — หากไม่ต้องใช้จีน ญี่ปุ่น เกาหลี
- `fonts-noto-extra`
- `fonts-noto-ui-extra`
- `fonts-thai-tlwg` metapackage และ TLWG families ที่ไม่ได้ใช้
- decorative/display font collections อื่น ๆ

`fonts-thai-tlwg` เป็น metapackage ที่ดึงหลาย family เช่น Garuda, Kinnari, Laksaman, Loma, Norasi, Purisa, Sawasdee, Waree และ TLWG families อื่น ๆ ดังนั้นถ้าเป้าหมายคือ LibreOffice แบบลีน ไม่ควรติดตั้งทั้งชุดเพียงเพราะชื่อว่า “Thai fonts”

### Target font menu

แนวคิดไม่ใช่บังคับให้เหลือจำนวน family ตายตัว แต่ให้รายการที่ผู้ใช้เห็นเป็นกลุ่มเล็กและมีเหตุผล:

```text
SYSTEM / FALLBACK
Noto Sans / Noto Serif / Noto Mono
DejaVu Sans / Serif / Mono
Liberation Sans / Serif / Mono

OFFICE COMPATIBILITY
Carlito
Caladea

THAI OFFICIAL
TH Sarabun New
```

หมายเหตุ: package หนึ่งอาจมีหลาย family/style และบาง font อาจถูกติดตั้งเป็น dependency ของ desktop/application จึงห้ามลบจากชื่อที่เห็นใน LibreOffice อย่างเดียว

### Audit ก่อน Clean

```bash
# package fonts ที่ติดตั้ง
dpkg -l | awk '/^ii/ && $2 ~ /^fonts-/ {print $2}' | sort

# family ที่ Fontconfig เห็นจริง
fc-list : family | sort -u

# ตรวจ Thai fallback
fc-match "sans-serif:lang=th"

# ตรวจ UI/general fallback
fc-match sans-serif

# ตรวจ monospace
fc-match monospace

# ตรวจฟอนต์งานราชการ
fc-match "TH Sarabun New"
```

จากนั้นค่อยเลือก package ที่จะถอน และ **simulate ทีละกลุ่ม** ห้ามยิง remove รายการใหญ่รวดเดียว

---

## 9. Incident: The □□□ Incident

ระหว่างทดลองลดจำนวนฟอนต์บน Ubuntu มีการจำลองตรวจแล้วถอน font packages ที่คิดว่าเป็นของเกิน หลังถอนพบอาการทันทีใน graphical session:

1. Terminal ที่กำลังเปิดใช้งานอยู่ปิด/หลุดอย่างผิดปกติ ซึ่งก่อนหน้านี้ไม่เคยพบอาการลักษณะนี้
2. ข้อความจำนวนมากบน Browser กลายเป็นสี่เหลี่ยม `□□□□`
3. UI/fallback ภาษาไทยเสียหาย
4. ต้องติดตั้ง font system/fallback กลับและ rebuild Fontconfig cache

เหตุการณ์เกิดหลังการถอน font packages รวมถึง `fonts-noto-ui-core` แต่ **ยังไม่มี log หรือ reproduction ที่พิสูจน์ว่า package ตัวเดียวเป็นสาเหตุของ Terminal ปิด** จึงบันทึกเป็น temporal association ไม่ใช่ข้อสรุปเชิงสาเหตุ

### Recovery

```bash
sudo apt update
sudo apt install fonts-noto-core fonts-noto-ui-core fonts-noto-mono
fc-cache -f -v
```

แล้ว logout/login หรือ reboot หาก application เดิมยังถือ font cache เก่า

### Lesson learned

> ฟอนต์ระบบไม่ใช่ของตกแต่งทั้งหมด บาง package เป็น fallback infrastructure ที่ Browser, Desktop UI และ Terminal ใช้โดยอ้อม แม้ผู้ใช้ไม่เคยเลือกชื่อ font นั้นเอง

ดังนั้นเป้าหมายของการ Clean คือ **ลด font menu pollution โดยไม่ทำลาย fallback chain** ไม่ใช่ลบให้เหลือน้อยที่สุด
