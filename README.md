# th_fonts

คลังฟอนต์ภาษาไทยสำหรับงานเอกสาร/เว็บ/โค้ด  
รวบรวมฟอนต์มาตรฐานราชการไทย เช่น TH Sarabun, TH Baijam, TH Chakra Petch ฯลฯ  
> **หมายเหตุเรื่องสิทธิ์ใช้งาน:** ฟอนต์ในคลังนี้ไม่ได้มีใบอนุญาตแบบเดียวกันทั้งหมด จึงไม่ควรเหมารวมว่าเป็น OFL ทุกไฟล์
>
> สำหรับ **TH Sarabun New** แหล่งอ้างอิงของตัวฟอนต์ระบุ GNU GPL v2-or-later พร้อม font-embedding exception ส่วน **Sarabun** รุ่นโอเพนซอร์สของ Cadson Demak/Google Fonts ใช้ SIL OFL 1.1
>
> ก่อนนำฟอนต์อื่นไป redistribute ให้ตรวจ license ของ family นั้นโดยตรงอีกครั้ง

---

## ⬇️ ดาวน์โหลดง่าย — TH Sarabun New สำหรับงานเอกสารราชการ

ถ้าต้องการเพียงฟอนต์สารบรรณ **ไม่ต้องโหลดทั้ง repository** ใช้ 4 style นี้พอ:

- [TH Sarabun New — Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew.ttf)
- [TH Sarabun New — Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew%20Bold.ttf)
- [TH Sarabun New — Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew%20Italic.ttf)
- [TH Sarabun New — Bold Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew%20BoldItalic.ttf)

### ดาวน์โหลดทั้ง repository เป็น ZIP

GitHub มี ZIP สาธารณะให้โดยอัตโนมัติ:

**[ดาวน์โหลด th_fonts ทั้งคลัง (.zip)](https://github.com/gwagk/th_fonts/archive/refs/heads/main.zip)**

> ZIP ทั้งคลังเหมาะสำหรับเก็บเป็น archive เท่านั้น — **ไม่แนะนำให้ติดตั้งทุกฟอนต์** เพราะจะทำให้รายการฟอนต์ใน LibreOffice ยาวโดยไม่จำเป็น

### Ubuntu: ดาวน์โหลด TH Sarabun New 4 style ด้วย Terminal

```bash
mkdir -p ~/.local/share/fonts/THSarabunNew
cd ~/.local/share/fonts/THSarabunNew

wget -O THSarabunNew.ttf \
  https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew.ttf
wget -O 'THSarabunNew Bold.ttf' \
  'https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew%20Bold.ttf'
wget -O 'THSarabunNew Italic.ttf' \
  'https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew%20Italic.ttf'
wget -O 'THSarabunNew BoldItalic.ttf' \
  'https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew%20BoldItalic.ttf'

fc-cache -f
fc-match 'TH Sarabun New'
```

จากนั้นปิดและเปิด LibreOffice ใหม่

---

## 📂 รายชื่อฟอนต์ + Raw links

> โครงสร้างลิงก์:  
> ```
> https://raw.githubusercontent.com/gwagk/th_fonts/main/<ชื่อไฟล์>.ttf
> ```

### 🔹 TH Sarabun New
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew%20BoldItalic.ttf)  

### 🔹 TH Sarabun
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabun.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabun%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabun%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabun%20Bold%20Italic.ttf)  

### 🔹 TH Baijam
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Baijam.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Baijam%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Baijam%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Baijam%20Bold%20Italic.ttf)  

### 🔹 TH Chakra Petch
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Chakra%20Petch.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Chakra%20Petch%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Chakra%20Petch%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Chakra%20Petch%20Bold%20Italic.ttf)  

### 🔹 TH Charmonman
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Charmonman.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Charmonman%20Bold.ttf)  

### 🔹 TH Charm of AU
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Charm%20of%20AU.ttf)  

### 🔹 TH Fahkwang
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Fahkwang.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Fahkwang%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Fahkwang%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Fahkwang%20Bold%20Italic.ttf)  

### 🔹 TH KoHo
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20KoHo.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20KoHo%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20KoHo%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20KoHo%20Bold%20Italic.ttf)  

### 🔹 TH Kodchasal
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Kodchasal.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Kodchasal%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Kodchasal%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Kodchasal%20Bold%20Italic.ttf)  

### 🔹 TH Krub
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Krub.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Krub%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Krub%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Krub%20Bold%20Italic.ttf)  

### 🔹 TH Mali Grade6
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Mali%20Grade6.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Mali%20Grade6%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Mali%20Grade6%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Mali%20Grade6%20Bold%20Italic.ttf)  

### 🔹 TH Niramit (และ ITù เวอร์ชัน)
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Niramit%20AS.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Niramit%20AS%20Bold.ttf)  
- [Italic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Niramit%20AS%20Italic.ttf)  
- [BoldItalic](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Niramit%20AS%20Bold%20Italic.ttf)  
- … (เวอร์ชัน ITù เพิ่มได้ตามชื่อไฟล์จริง)

### 🔹 TH Srisakdi
- [Regular](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Srisakdi.ttf)  
- [Bold](https://raw.githubusercontent.com/gwagk/th_fonts/main/TH%20Srisakdi%20Bold.ttf)  

---

## 🐧 Ubuntu / LibreOffice แบบ Lean

สำหรับเครื่องที่ต้องการภาษาไทย + เอกสารราชการ โดยไม่ติดตั้งฟอนต์เกินจำเป็น:

- [คู่มือ Ubuntu + LibreOffice: ชุดฟอนต์ไทยแบบ Lean](docs/ubuntu-thai-font-minimal.md)
- หลัก: เก็บ System/UI fallback + Office compatibility + TH Sarabun New
- ก่อนถอนฟอนต์ทุกครั้งใช้ `apt remove --simulate`

---

## 🐍 ใช้กับ Python (matplotlib)
```python
import matplotlib.pyplot as plt
import matplotlib.font_manager as fm
import urllib.request, tempfile, os

RAW = "https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew.ttf"
tmp = tempfile.mkdtemp()
fp = os.path.join(tmp, "THSarabunNew.ttf")
urllib.request.urlretrieve(RAW, fp)

thai = fm.FontProperties(fname=fp)
plt.text(0.5, 0.5, "สวัสดีครับ", fontproperties=thai, fontsize=24, ha="center")
plt.axis("off"); plt.show()
