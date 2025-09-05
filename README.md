# th_fonts

รวมฟอนต์ภาษาไทยสำหรับงานเอกสารและงานพัฒนาโปรแกรม  
โดยเฉพาะ **TH Sarabun New (ฟอนต์สารบรรณ)** ซึ่งเป็นฟอนต์มาตรฐานราชการไทย  
เปิดให้ใช้งานได้ฟรี (SIL Open Font License) ไม่มีข้อจำกัดลิขสิทธิ์  

---

## 📌 ฟอนต์ที่มีอยู่
- THSarabunNew.ttf
- THSarabunNew-Bold.ttf
- THSarabunNew-Italic.ttf
- THSarabunNew-BoldItalic.ttf

---

## 🚀 วิธีใช้งาน

### 1) ติดตั้งในเครื่อง (Windows/Mac/Linux)
- ดาวน์โหลดไฟล์ `.ttf` ไปที่เครื่อง  
- ดับเบิลคลิกที่ไฟล์ → กด **Install**  
- จากนั้นจะใช้งานได้ใน Word, PowerPoint, Google Docs และซอฟต์แวร์อื่น ๆ  

### 2) ใช้กับ Python (matplotlib)
```python
import matplotlib.pyplot as plt
import matplotlib.font_manager as fm

# โหลดฟอนต์จาก repo (Raw link)
font_path = "https://raw.githubusercontent.com/<username>/th_fonts/main/THSarabunNew.ttf"
thai_font = fm.FontProperties(fname=font_path)

plt.title("ทดสอบกราฟภาษาไทย", fontproperties=thai_font, fontsize=18)
plt.plot([1,2,3], [1,4,9])
plt.show()
