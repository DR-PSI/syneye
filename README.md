# SynEye PWA

แอปนัดหมายและติดตามงานตรวจสอบสายไฟฟ้าภายใน (ต้นแบบ) — 2 แอปในไฟล์เดียว: แอปลูกค้า และ แอปช่าง
แผนที่ใช้ OpenStreetMap (tile: CARTO Voyager) ผ่าน Leaflet 1.9.4

## ไฟล์
- `index.html` — ตัวแอปทั้งหมด (self-contained ไม่ต้อง build)
- `manifest.webmanifest` — ตั้งค่า PWA (ติดตั้งบนหน้าจอหลักได้)
- `sw.js` — service worker: cache app shell + cache tile แผนที่ที่เคยเปิด
- `icon-192.png`, `icon-512.png` — ไอคอนแอป (placeholder รอไอคอนจริง)
- `.nojekyll` — ให้ GitHub Pages เสิร์ฟไฟล์ตามเดิม

## ขึ้น GitHub Pages
```bash
git init
git add .
git commit -m "SynEye PWA prototype"
git branch -M main
git remote add origin https://github.com/<user>/<repo>.git
git push -u origin main
```
แล้วเปิด Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / `root`

PWA ต้องเสิร์ฟผ่าน HTTPS (GitHub Pages เป็น HTTPS อยู่แล้ว) จึงจะติดตั้งและใช้ service worker ได้

## หมายเหตุ
- ข้อมูลทั้งหมดเป็นข้อมูลตัวอย่างในหน้าจอ ยังไม่ต่อ backend
- ตำแหน่งช่างเป็นการจำลองเดินตามเส้นทางถนนลาดกระบัง หากต่อของจริงให้แทนด้วยพิกัดจาก GPS ของแอปช่าง
- ปุ่ม EN/ไทย สลับภาษาทุกหน้าจอ
- ชุดนี้ใช้แนวหน้าตา A (เรียบสว่าง) ครบ 15 หน้า: แอปลูกค้า 8 หน้า + แอปช่าง 7 หน้า
