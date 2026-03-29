# CPAC Silo Monitor Dashboard

แปลงจาก [cpac-silo-dashboard.html](/d:/CPAC2026/04%20Codex/Cement%20Qaulity/cpac-silo-dashboard.html)

## ภาพรวม

แดชบอร์ดนี้ใช้สำหรับติดตามสถานะไซโลปูนซีเมนต์ของโรงงานปูนและโรงงาน CPAC พร้อมมุมมองแผนที่ระดับประเทศ และหน้าติดตามผลคุณภาพแบบ traceability ระดับ DN

## เมนูหลัก

1. `Cement Plants`
2. `CPAC Plants`
3. `National Map`
4. `Quality Traceability`

## 1. Cement Plants

### โรงงานที่เลือกได้

- โรงงานลำปาง (SLP)
- โรงงานท่าหลวง (STL)
- โรงงานเขาวง (SKW)
- โรงงานแก่งคอย (SKK)
- โรงงานทุ่งสง (STS)

### KPI บนส่วนหัว

- อัปเดตล่าสุด: `20 ก.พ. 2568 14:32`
- สต็อกรวม: `42,850 ตัน`
- Utilization: `67.4%`
- จำนวนไซโลทั้งหมด: `10 ไซโล`

### Summary Strip

- ระดับปกติ: `6 ไซโล`
- ระดับต่ำ: `2 ไซโล`
- วิกฤต: `1 ไซโล`
- จัดส่งวันนี้: `28 รายการ DN`
- Lot ปัจจุบัน: `LOT-47`

### Alert Strip

- `SILO 3` ระดับต่ำกว่า Min
- `SILO 7` มี Strength drop ต่อเนื่อง 3 DN
- `SILO 9` ไม่มีข้อมูล 2 ชั่วโมง

### Cement Silos

| Silo | Brand | Capacity (T) | Volume (T) | Min (T) | Max (T) | Lot | Quality |
| --- | --- | ---: | ---: | ---: | ---: | --- | --- |
| SILO 1 | SCG SHC (Hybrid Cement) | 8,000 | 5,392 | 800 | 7,680 | LOT-47 | ok |
| SILO 2 | SCG SHC (Hybrid Cement) | 8,000 | 5,696 | 800 | 7,680 | LOT-47 | ok |
| SILO 3 | SCG Mortar Grade | 8,000 | 1,136 | 800 | 7,680 | LOT-47 | ok |
| SILO 7 | SCG HY-Bond (Low Heat) | 8,000 | 2,248 | 800 | 7,680 | LOT-46 | warn |
| SILO 9 | SCG Super G (Export) | 10,000 | 0 | 1,000 | 9,500 | - | nodata |

## 2. CPAC Plants

### KPI บนส่วนหัว

- สต็อกรวม: `342 ตัน`
- แหล่งที่มา: `STL + SKK`
- จำนวนไซโลทั้งหมด: `4 ไซโล`

### ข้อความแจ้งสถานะ

ไซโลในมุมมองนี้รับซีเมนต์จากโรงงาน `ท่าหลวง STL (LOT-47)` และ `แก่งคอย SKK (LOT-23)` โดยมีสัดส่วน Blend โดยประมาณ `60% / 40%`

### CPAC Plant Silos

| Silo | Brand | Source | Capacity (T) | Volume (T) | Min (T) | Max (T) | Lot | Quality | Plant |
| --- | --- | --- | ---: | ---: | ---: | ---: | --- | --- | --- |
| SILO C1 | SHC - ท่าหลวง LOT-47 | STL | 180 | 124 | 20 | 170 | LOT-47 | ok | CPAC บางนา-ตราด |
| SILO C2 | SHC - แก่งคอย LOT-23 | SKK | 180 | 48 | 20 | 170 | LOT-23 | warn | CPAC ฉะเชิงเทรา |
| SILO C3 | Mortar Grade - ท่าหลวง | STL | 100 | 82 | 12 | 95 | LOT-47 | ok | CPAC พระราม 2 |
| SILO C4 | SHC Blend Mix | STL+SKK | 100 | 14 | 12 | 95 | MIX | fail | CPAC สระบุรี |

### ตัวอย่าง DN ภายในไซโล CPAC

| Silo | DN | Tons | Status | Received At | QC |
| --- | --- | ---: | --- | --- | --- |
| SILO C1 | DN123458 | 38 | ok | 10/03/2026 12:10 | ผ่าน |
| SILO C1 | DN123457 | 86 | ok | 10/03/2026 08:30 | ผ่าน |
| SILO C2 | DN123456 | 14 | warn | 10/03/2026 11:45 | เฝ้าระวัง |
| SILO C3 | DN123453 | 82 | ok | 10/03/2026 07:55 | ผ่าน |
| SILO C4 | DN123452 | 2 | fail | 10/03/2026 12:25 | กักใช้งาน |

## 3. National Map

มุมมองแผนที่ประเทศใช้ `Leaflet` และแสดงข้อมูลดังนี้

- โรงงานปูนซีเมนต์ `5` แห่ง
- กลุ่มจุดของ `CPAC Plants`
- จุดแจ้งเตือนคุณภาพ `1` จุด

### รายชื่อ Cement Plants บนแผนที่

| Plant | Province | Warning |
| --- | --- | --- |
| Lampang (SLP) | Lampang | No |
| Tha Luang (STL) | Saraburi | No |
| Khao Wong (SKW) | Saraburi | No |
| Kaeng Khoi (SKK) | Saraburi | Yes |
| Thung Song (STS) | Nakhon Si Thammarat | No |

## 4. Quality Traceability

### หน้าที่รองรับ

- กรองตามโรงงาน
- กรองตาม Lot
- ค้นหา DN, Lot และ SILO
- สลับมุมมอง parameter ได้ 5 แบบ
  - `summary`
  - `chemical`
  - `physical`
  - `compound`
  - `all`

### Traceability Flow

`DN -> SILONO -> Lot -> ผลคุณภาพซีเมนต์ -> CPAC Destination`

### ตัวอย่างข้อมูล DN

| DN | Silo | Lot | Plant | Ship To | Bayout | Status |
| --- | --- | --- | --- | --- | --- | --- |
| DN-250220-001 | SILO-1 | LOT-47 | STL | CPAC บางนา-ตราด | 20/02/68 08:14 | pass |
| DN-250220-002 | SILO-2 | LOT-47 | STL | CPAC รัชดา | 20/02/68 09:02 | pass |
| DN-250220-003 | SILO-7 | LOT-46 | STL | CPAC ลาดกระบัง | 20/02/68 10:30 | warn |
| DN-250220-004 | SILO-7 | LOT-46 | STL | CPAC บางบัวทอง | 20/02/68 11:15 | fail |
| DN-250220-005 | SILO-3 | LOT-47 | STL | CPAC สุขุมวิท | 20/02/68 12:00 | pass |
| DN-250219-047 | SILO-1 | LOT-47 | STL | CPAC รัชดา | 19/02/68 15:22 | pass |

### กลุ่มผลทดสอบที่แสดงในหน้า Detail

- Chemical Composition
- Bogue Compound Composition
- Physical Properties
- Mortar Compressive Strength
- ตารางเปรียบเทียบ Cement Quality Testing: Daily vs Lot
- หมายเหตุการตรวจสอบคุณภาพปูนซีเมนต์

### Spec Limits ที่ใช้ในแดชบอร์ด

| Parameter | Spec |
| --- | --- |
| SiO2 | 19.0-22.0 % |
| Al2O3 | 4.0-6.5 % |
| Fe2O3 | 2.5-4.5 % |
| CaO | 62.0-67.0 % |
| MgO | <= 5.0 % |
| SO3 | <= 3.5 % |
| K2O | <= 1.5 % |
| Na2O | <= 0.6 % |
| Alkalies | <= 0.80 % |
| LOI | <= 3.0 % |
| Insoluble | <= 1.5 % |
| C3S | 50.0-65.0 % |
| C2S | 10.0-25.0 % |
| C3A | 6.0-11.0 % |
| C4AF | 8.0-14.0 % |
| Blaine | 3200-3600 cm²/g |
| Autoclave | <= 0.80 % |
| Vicat Initial | 120-180 นาที |
| Vicat Final | <= 240 นาที |
| Aircontent | <= 12.0 % |
| STR1D | >= 12.0 MPa |
| STR3D | >= 28.0 MPa |
| STR7D | >= 34.0 MPa |
| STR28D | >= 42.0 MPa |

## Modal / Detail View

แดชบอร์ดมี modal สำหรับดูรายละเอียดไซโล โดยแสดงข้อมูลหลักดังนี้

- กราฟระดับไซโลย้อนหลัง `7 วัน`
- ค่า Min / Max เทียบกับระดับปัจจุบัน
- Quality parameters ของ Lot ปัจจุบัน
- ตาราง dispatch / DN
- ข้อมูลการทดสอบคุณภาพแบบ daily และ lot

## เทคโนโลยีที่ใช้ในไฟล์ HTML

- HTML + CSS + Vanilla JavaScript
- Google Fonts: `IBM Plex Sans Thai`, `IBM Plex Mono`
- `Leaflet 1.9.4`
- `Leaflet.markercluster 1.5.3`

## หมายเหตุ

ไฟล์ Markdown นี้เป็นฉบับสรุปเนื้อหาและข้อมูลสำคัญจากแดชบอร์ด ไม่ได้คงพฤติกรรม interactive, style, animation, modal และการ render แบบ dynamic ของไฟล์ HTML ต้นฉบับ
