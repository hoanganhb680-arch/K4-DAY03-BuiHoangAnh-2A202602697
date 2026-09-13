# 📊 BÁO CÁO THU HOẠCH NGHIỆM THU BÀI LAB 3 (BƯỚC 3 — SUBMISSION ARTIFACT)

> **Họ và Tên Học viên:** Chưa cập nhật
> **Mã Sinh Viên / Mã học viên:** Chưa cập nhật
> **Chủ đề Lựa chọn:** Trợ lý học vụ sinh viên VinUni

---

## 1. BẢNG CHẤM ĐIỂM AGENTIC FIT SCORING MATRIX (ĐÁNH GIÁ CHỦ ĐỀ)

| Tiêu chí Đánh giá | Mức độ (1 - 5) | Giải trình chi tiết lý do chọn điểm |
| :--- | :---: | :--- |
| **1. Multi-step Reasoning** | 4 / 5 | Tra cứu hồ sơ và xử lý yêu cầu đặt lịch cần nhiều bước nghiệp vụ. |
| **2. Tool Interaction** | 4 / 5 | Agent phải gọi các tool học vụ được công bố qua MCP Server. |
| **3. Dynamic Decision** | 3 / 5 | Kết quả tra cứu quyết định thông tin được dùng ở bước tiếp theo. |
| **4. Long Horizon Goal** | 2 / 5 | Các test hiện tại chủ yếu hoàn tất trong một đến hai lượt xử lý. |
| **TỔNG ĐIỂM AGENTIC FIT** | **13 / 20** | *Bài toán phù hợp triển khai Agentic System.* |

---

## 2. TRÍCH XUẤT KẾT QUẢ WATERFALL TRACE LOG

> ⚠️ **YÊU CẦU NGHIỆM THU:** Mở tệp `.env` điền `GEMINI_API_KEY` (hoặc `OPENAI_API_KEY`) để kết nối LLM thật trước khi thực thi `python src/app.py --all`. Bài nộp chỉ dùng Mock Offline Provider sẽ không đạt điểm nghiệm thực tế.

Dưới đây là đoạn trích xuất từ `docs/trace_waterfall.json` sau khi chạy `python .venv/Scripts/python.exe src/app.py --all` với Gemini API thật:

```json
[
  {
    "step": 1,
    "action_type": "TOOL_EXECUTION",
    "tool_name": "academic_query",
    "arguments": {"student_id": "SV2026001"},
    "observation": {
      "status": "SUCCESS",
      "student_id": "SV2026001",
      "data": {"full_name": "Nguyễn Văn An", "class": "AI-K4", "gpa": 3.85}
    },
    "latency_ms": 765.87
  },
  {
    "step": 1,
    "action_type": "TOOL_EXECUTION",
    "tool_name": "academic_query",
    "arguments": {"student_id": "SV0999999"},
    "observation": {
      "status": "NOT_FOUND",
      "message": "Không tìm thấy dữ liệu sinh viên có mã 'SV0999999'"
    },
    "latency_ms": 777.42
  }
]
```

Trace đầy đủ hiện có 9 sự kiện: 5 `FINAL_ANSWER` và 4 `TOOL_EXECUTION`, tương ứng 5/5 test cases.

---

## 3. TỔNG KẾT KẾT QUẢ NGHIỆM THU & NỘP BÀI

- [x] Đã điền API Key thật trong `.env` và xác nhận Agent chạy thành công trên Gemini API thật.
- **Tổng số Test Cases đã chạy thành công:** 5 / 5 test cases trên Gemini API thật.
- **Tổng số sự kiện Waterfall Trace:** 9 sự kiện (4 `TOOL_EXECUTION`, 5 `FINAL_ANSWER`).
- **Số lượt gọi Tool qua MCP Server chính xác:** 4 lượt.
- **Kết quả đẩy Repo nộp bài:** [ ] Chưa commit/push; cần cập nhật thông tin cá nhân và API key trước khi nộp.

---

> ✅ **HOÀN TẤT NỘP BÀI:** Sao chép đường link GitHub Repository cá nhân của bạn và dán vào ô nộp bài trên hệ thống LMS VLearn để hoàn tất Bài Lab 3!
