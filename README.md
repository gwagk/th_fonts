# th_fonts

คลังฟอนต์ภาษาไทย (ราชการ) สำหรับใช้งานในโค้ด/เว็บ  
หลัก ๆ คือ **TH Sarabun New (สารบรรณ)** ภายใต้ SIL Open Font License (OFL)

---

## 🔗 Raw links (ดึงใช้ตรงได้ทันที)
- Regular: https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew.ttf
- Bold: https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew-Bold.ttf
- Italic: https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew-Italic.ttf
- BoldItalic: https://raw.githubusercontent.com/gwagk/th_fonts/main/THSarabunNew-BoldItalic.ttf

> ถ้ามีไฟล์อื่น ๆ เพิ่ม เติมบรรทัดตามรูปแบบด้านบนได้เลย  
> โครงสร้างลิงก์: `https://raw.githubusercontent.com/gwagk/th_fonts/main/<ชื่อไฟล์>.ttf`

### ตรึงเวอร์ชัน (แนะนำเวลาขึ้นโปรดักชัน)
ใช้ commit hash แทน `main` เช่น

หา `<commit-hash>` ได้จากปุ่ม **History** ของไฟล์ แล้วกดเข้า commit นั้น

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
plt.figure(figsize=(6,3))
plt.text(0.5, 0.6, "สวัสดีครับ", fontproperties=thai, fontsize=24, ha="center")
plt.axis("off"); plt.tight_layout(); plt.show()
