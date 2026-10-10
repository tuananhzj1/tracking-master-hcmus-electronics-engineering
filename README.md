# 🎓 HCMUS Master Tracker — README

Bookmarklet theo dõi tiến độ học tập Thạc sĩ ngành **Viễn thông – Mạng máy tính (VTMT) khóa K35**, Trường Đại học Khoa học Tự nhiên – ĐHQG-HCM.

---

## ✨ Tính năng

### 📚 Tab Học phần
- Tự động đọc **bảng điểm** từ trang `/academic-results` và tô màu:
  - 🟢 **Xanh** — môn đạt (điểm ≥ 5.0)
  - 🔴 **Đỏ** — môn không đạt (điểm < 5.0)
- Tự động đọc **học phần đã đăng ký** từ trang `/course-registration-result` và tô **vàng** — môn đang học (in-progress).
- **Hộp tracker** hiển thị:
  - Tổng TC tích lũy / tổng TC yêu cầu
  - GPA hệ 10 và hệ 4
  - Điều kiện đạt của từng phương thức (PT1 / PT2 / PT3)
  - Danh sách môn theo 4 nhóm: Kiến thức chung, Bắt buộc, Tự chọn, Luận văn/Đồ án
- **Chọn phương thức** (PT1/PT2/PT3) → tracker tự động cập nhật chỉ tiêu TC, môn bắt buộc, và loại luận văn/đồ án tương ứng.
- **Checkbox thủ công** cho môn chưa có điểm; môn đã có điểm bị **khóa** (không thể bỏ tick).
- **Phân loại trạng thái môn:**
  | Trạng thái | Màu | Badge | Checkbox |
  |---|---|---|---|
  | Passed (≥ 5.0) | Xanh | ✔ 8.6 | Tick + Khóa |
  | Failed (< 5.0) | Đỏ | ✘ 4.5 | Không tick + Khóa |
  | In-progress (chưa có điểm) | Vàng | ⏳ | Tick + Cho phép |
  | Chưa học | Đen | — | Cho phép |

### 🌐 Tab Ngoại ngữ
- Theo dõi chuẩn đầu ra ngoại ngữ theo **QĐ 315/QĐ-KHTN ngày 14/02/2025** (Bậc 4 / B2, hiệu lực 24 tháng).
- **Miễn ngoại ngữ qua văn bằng:** tick nếu có bằng ĐH nước ngoài / ngành ngôn ngữ / chương trình giảng dạy bằng ngoại ngữ.
- **Chọn chứng chỉ** từ 13 loại:
  - Tiếng Anh: TOEFL iBT, IELTS, TOEIC 4 kỹ năng, Cambridge B2, Aptis ESOL B2, VSTEP Bậc 4
  - Ngoại ngữ khác: TCF/DELF (Pháp), Goethe/TestDaF (Đức), HSK 4 (Trung), JLPT N3 (Nhật), ТРКИ-2 (Nga), TOPIK 4 (Hàn)
- **Nhập điểm** → tự động so với ngưỡng, hiện ✔/✘.
- **Nhập ngày thi** → tự động tính hạn 24 tháng:
  - ✔ Còn > 180 ngày (xanh)
  - ⚠️ Còn ≤ 180 ngày (vàng)
  - ⚠️ Đã hết hạn (đỏ)
- **Trạng thái tổng:** `✔ ĐẠT CHUẨN NGOẠI NGỮ` hoặc `✘ CHƯA ĐẠT`.

### 💾 Lưu trữ
Tất cả dữ liệu (điểm, tick thủ công, môn đang học, phương thức, thông tin ngoại ngữ) được lưu vào `localStorage` với key `master-tracking-hcmus`, tồn tại trên toàn domain `student.hcmus.edu.vn`.

---

## 🚀 Cài đặt

### Cách 1: Lưu thành bookmark (khuyến nghị)

1. Mở trình duyệt (Chrome / Edge / Firefox / Safari).
2. Hiện thanh bookmark: `Ctrl + Shift + B` (Windows) hoặc `Cmd + Shift + B` (Mac).
3. Chuột phải vào thanh bookmark → **Thêm trang** / **Add page**.
4. Điền:
   - **Tên:** `HCMUS Tracker`
   - **URL:** dán toàn bộ đoạn `javascript:(function(){...})();` (một dòng duy nhất).
5. Nhấn **Lưu**.

### Cách 2: Dán trực tiếp vào thanh địa chỉ

1. Copy toàn bộ đoạn `javascript:...`.
2. Mở trang cần dùng.
3. Dán vào thanh địa chỉ → nhấn `Enter`.

> ⚠️ **Lưu ý:** Chrome/Edge có thể tự động xóa tiền tố `javascript:` khi dán. Nếu bị, hãy gõ tay `javascript:` trước khi dán phần còn lại.

---

## 📖 Hướng dẫn sử dụng

### Bước 1: Đăng nhập
Truy cập [https://student.hcmus.edu.vn](https://student.hcmus.edu.vn) và đăng nhập bằng email `@student.hcmus.edu.vn`.

### Bước 2: Lấy dữ liệu điểm
1. Mở trang **Kết quả học tập**: [https://student.hcmus.edu.vn/academic-results](https://student.hcmus.edu.vn/academic-results)
2. Nhấn bookmark **HCMUS Tracker**.
3. Bảng điểm sẽ được tô màu xanh/đỏ. Hộp tracker hiện ra ở góc phải.
4. Dữ liệu điểm được lưu tự động.

### Bước 3: Lấy dữ liệu môn đang học
1. Mở trang **Kết quả đăng ký học phần**: [https://student.hcmus.edu.vn/course-registration-result](https://student.hcmus.edu.vn/course-registration-result)
2. Nhấn bookmark **HCMUS Tracker**.
3. Bảng học phần sẽ được tô vàng. Hộp tracker hiện ra với thông tin môn đang học.
4. Dữ liệu in-progress được lưu tự động.

### Bước 4: Xem và tương tác với tracker

**Tab 📚 Học phần:**
- Chọn **phương thức** (PT1/PT2/PT3) ở dropdown.
- Xem **tổng TC**, **GPA hệ 10**, **GPA hệ 4**.
- Xem **điều kiện đạt** của PT đã chọn (Triết học / Bắt buộc / Tự chọn / Luận văn hoặc Đồ án).
- Tick checkbox cho môn chưa có điểm nếu muốn đánh dấu thủ công.

**Tab 🌐 Ngoại ngữ:**
- Tick **"Miễn ngoại ngữ qua văn bằng"** nếu thuộc diện miễn.
- Hoặc chọn **chứng chỉ** → nhập **điểm** → nhập **ngày thi**.
- Xem **trạng thái tổng** ở cuối panel.

### Bước 5: Đóng tracker
Nhấn nút **✕** ở góc trên bên phải hộp tracker.

---

## 🔄 Quy trình khuyến nghị

```
┌─────────────────────────────┐
│ 1. Đăng nhập student.hcmus  │
└──────────────┬──────────────┘
               ▼
┌─────────────────────────────┐
│ 2. Mở /academic-results     │
│    → Chạy bookmarklet       │
│    → Lưu điểm               │
└──────────────┬──────────────┘
               ▼
┌─────────────────────────────┐
│ 3. Mở /course-registration  │
│    → Chạy bookmarklet       │
│    → Lưu in-progress        │
└──────────────┬──────────────┘
               ▼
┌─────────────────────────────┐
│ 4. Xem tracker (ở bất kỳ    │
│    trang nào trong 2 trang) │
│    → Chọn PT, xem GPA, NN   │
└─────────────────────────────┘
```

> 💡 **Mẹo:** Chạy bookmarklet trên **cả 2 trang** mỗi khi có điểm mới hoặc đăng ký môn mới, để tracker luôn cập nhật.

---

## 🧮 Công thức tính

### GPA hệ 10
```
GPA10 = Σ(điểm × TC) / Σ(TC)
```
Chỉ tính các môn **đã đạt** (điểm ≥ 5.0).

### GPA hệ 4 (quy đổi)
| Điểm hệ 10 | Điểm hệ 4 |
|---|---|
| ≥ 8.5 | 4.0 |
| ≥ 7.0 | 3.0 |
| ≥ 5.5 | 2.0 |
| ≥ 4.0 | 1.0 |
| < 4.0 | 0 |

```
GPA4 = Σ(điểm hệ 4 × TC) / Σ(TC)
```

### Hạn chứng chỉ ngoại ngữ
```
Hạn = Ngày thi + 24 tháng
```
Cảnh báo nếu còn ≤ 180 ngày hoặc đã hết hạn.

---

## 📋 Điều kiện đạt theo phương thức

| Phương thức | Tổng TC | Triết học | Bắt buộc | Tự chọn | Luận văn/Đồ án |
|---|---|---|---|---|---|
| **PT1** — Nghiên cứu | 60 | 3 | 11 | 16 | 30 (LV) |
| **PT2** — Ứng dụng (LV) | 62 | 3 | 11 | 36 | 12 (LV) |
| **PT3** — Ứng dụng (ĐA) | 62 | 3 | 17 | 36 | 6 (ĐA) |

**Môn bắt buộc:**
- **PT1/PT2:** `MDT034`, `MDT035`, `MNC` (11 TC)
- **PT3:** thêm `MDT055` — Thực tập thực tế (17 TC)

---

## ❓ Câu hỏi thường gặp

### 1. Bookmarklet không chạy?
- Kiểm tra đã gõ đúng tiền tố `javascript:` chưa.
- Một số trình duyệt chặn bookmarklet trên trang HTTPS có CSP nghiêm ngặt. Thử dùng Chrome hoặc Firefox.
- Mở Console (F12) xem có lỗi không.

### 2. Không thấy môn in-progress?
- Phải chạy bookmarklet trên trang `/course-registration-result` ít nhất 1 lần.
- Kiểm tra Console: `JSON.parse(localStorage.getItem('master-tracking-hcmus'))` xem `inProgress` có dữ liệu không.

### 3. Môn đã có điểm nhưng vẫn hiện vàng?
- Trong logic mới, **điểm luôn thắng in-progress**. Nếu vẫn vàng, có thể `store.scores` chưa có mã đó → chạy lại bookmarklet trên `/academic-results`.

### 4. Muốn reset toàn bộ dữ liệu?
Mở Console, chạy:
```javascript
localStorage.removeItem('master-tracking-hcmus');
```
Rồi chạy lại bookmarklet.

### 5. Dữ liệu có mất khi đổi máy không?
Có. Dữ liệu lưu trong `localStorage` của trình duyệt, **không đồng bộ** giữa các máy. Muốn chuyển, export/import thủ công qua Console:
```javascript
// Export
copy(localStorage.getItem('master-tracking-hcmus'));
// Import
localStorage.setItem('master-tracking-hcmus', 'DÁN_CHUỖI_JSON_VÀO_ĐÂY');
```

### 6. Tracker che mất nội dung trang?
Kéo thả hộp tracker bằng cách giữ chuột vào tiêu đề (nếu hỗ trợ), hoặc nhấn **✕** để đóng, chạy lại bookmarklet khi cần.

---

## ⚠️ Miễn trừ trách nhiệm

- Đây là công cụ **cá nhân**, không chính thức từ nhà trường.
- Dữ liệu điểm và TC chỉ mang tính **tham khảo**, không thay thế cho việc xác nhận chính thức từ Phòng Đào tạo Sau đại học.
- Người dùng tự chịu trách nhiệm khi sử dụng bookmarklet trên trình duyệt của mình.

---

## 📝 Ghi chú kỹ thuật

- **Ngôn ngữ:** JavaScript thuần (ES6+).
- **Lưu trữ:** `localStorage` với key `master-tracking-hcmus`.
- **Không gửi dữ liệu ra ngoài** — mọi thứ chạy local trong trình duyệt.
- **Tương thích:** Chrome 90+, Edge 90+, Firefox 88+, Safari 14+.
- **Cấu trúc dữ liệu:**
  ```javascript
  {
    scores: { "MDT042": 6.5, "MDT043": 9.5, ... },   // điểm từ bảng điểm
    manual: { "MDT047": true, ... },                  // tick thủ công
    inProgress: { "MDT051": true, ... },              // môn đang học
    pt: "PT1",                                        // phương thức đã chọn
    tab: "hocphan",                                   // tab đang mở
    ngoaiNgu: {
      mien: false,
      cert: "IELTS",
      score: "6.5",
      toeic: { nghe: "", doc: "", noi: "", viet: "" },
      examDate: "2025-03-15"
    }
  }
  ```

---

## 📚 Tài liệu tham khảo

- Quyết định số **315/QĐ-KHTN** ngày 14/02/2025 của Hiệu trưởng Trường ĐH KHTN, ĐHQG-HCM.
- Danh sách cơ sở cấp chứng chỉ VSTEP: [https://sdh.hcmus.edu.vn/](https://sdh.hcmus.edu.vn/)
- Trang người học: [https://student.hcmus.edu.vn](https://student.hcmus.edu.vn)

---

**Chúc bạn hoàn thành chương trình Thạc sĩ đúng hạn! 🎓**
