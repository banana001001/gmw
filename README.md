# TradingView Indicators — MACD + FVG

Pine Script v5 | ใช้งานได้บน TradingView (Free / Pro / Pro+)

---

## ไฟล์ที่มี

| ไฟล์ | ชนิด | วางบน chart |
|---|---|---|
| `MACD_Indicator.pine` | Separate pane (ด้านล่าง) | ✅ |
| `FVG_Indicator.pine` | Overlay (บน price chart) | ✅ |

แต่ละไฟล์เพิ่ม/ลบได้อิสระ — ไม่ขึ้นต่อกัน

---

## วิธีนำไปใช้ใน TradingView

1. เปิด **TradingView** → เลือก chart
2. คลิก **Pine Editor** (แถบด้านล่าง)
3. ลบโค้ดเดิมออก → Copy โค้ดจากไฟล์ที่ต้องการวางลง
4. กด **Add to chart** (ปุ่มสีน้ำเงินด้านบน)
5. ทำซ้ำกับไฟล์ที่สอง

---

## MACD Indicator

**ไฟล์:** `MACD_Indicator.pine`  
**ตำแหน่ง:** แสดงใน pane แยกด้านล่าง chart

### การตั้งค่า

| กลุ่ม | ตัวเลือก | ค่า Default |
|---|---|---|
| ⚙️ MACD Settings | Fast / Slow / Signal Length | 12 / 26 / 9 |
| ⚙️ MACD Settings | Source | Close |
| 📊 Histogram | Show / ซ่อน Histogram | เปิด |
| 📊 Histogram | สีทั้ง 4 state | Teal / Red |
| 📈 Lines | Show/Hide MACD & Signal line | เปิดทั้งคู่ |
| 🔔 Crossover Signals | Show/Hide signal markers | ปิด (toggle ได้) |

### สี Histogram (4 state เหมือน TradingView built-in)

```
Positive + Rising  → Teal เข้ม  🟢  (momentum แรง)
Positive + Falling → Teal จาง  🔵  (momentum อ่อน)
Negative + Falling → Red เข้ม   🔴  (momentum แรง)
Negative + Rising  → Red จาง    🟠  (momentum อ่อน)
```

### Alerts ที่รองรับ
- MACD ตัด Signal ขึ้น (Bull Cross)
- MACD ตัด Signal ลง (Bear Cross)
- MACD ตัด Zero Line ขึ้น/ลง

---

## FVG Indicator — Fair Value Gap

**ไฟล์:** `FVG_Indicator.pine`  
**ตำแหน่ง:** Overlay บน price chart

### หลักการ FVG (3-candle imbalance)

```
Bullish FVG: low[0] > high[2]
             ช่องว่างระหว่าง high ของแท่ง 1 กับ low ของแท่ง 3

Bearish FVG: high[0] < low[2]
             ช่องว่างระหว่าง low ของแท่ง 1 กับ high ของแท่ง 3
```

### การตั้งค่า

| กลุ่ม | ตัวเลือก | ค่า Default |
|---|---|---|
| ⚙️ General | Show Bullish / Bearish FVG | เปิดทั้งคู่ |
| ⚙️ General | Show Midline | เปิด |
| ⚙️ General | Extend Box to Right | เปิด |
| ⚙️ General | Delete When Price Fills | ปิด (เปลี่ยนสีแทน) |
| ⚙️ General | Show Labels | ปิด |
| ⚙️ General | Max FVG on Chart | 100 |
| 🟢 Bullish | Box / Border / Midline colors | Green |
| 🔴 Bearish | Box / Border / Midline colors | Red |
| ⬜ Filled | สีเมื่อ FVG ถูก fill | Gray |

### พฤติกรรม

- Box จะ **ขยายไปทางขวา** จนกว่าราคาจะเข้ามา fill โซนนั้น
- เมื่อ fill แล้ว → เปลี่ยนเป็นสีเทา + หยุดขยาย
- เปิด **Delete When Price Fills** → ลบ box ออกเลยเมื่อ fill

### Alerts ที่รองรับ
- พบ Bullish FVG ใหม่
- พบ Bearish FVG ใหม่

---

## เปิด/ปิดแต่ละตัว

- **ซ่อนชั่วคราว:** คลิกปุ่ม 👁️ ที่ Legend บน chart
- **ลบออกถาวร:** คลิก ⋮ → Remove indicator
- **ปิดบาง feature:** เข้า Settings ของ indicator → toggle ตัวที่ไม่ต้องการ

---

*Pine Script v5 — ทดสอบบน TradingView.com*
