# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 04
- **Họ tên:Phạm Đăng Khoa**
- **Lớp:CNTT!**
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé xe ra JSON

**KET QUA AI**

```text

[
  {
    "ma_tuyen": "SGDL",
    "ngay_di": "2026-12-22",
    "ve_nguoi_lon": 2,
    "ve_tre_em": 1,
    "loai_cho": "giuong",
    "ghi_chu": null
  },
  {
    "ma_tuyen": "SGNT",
    "ngay_di": "2027-01-02",
    "ve_nguoi_lon": 3,
    "ve_tre_em": 0,
    "loai_cho": null,
    "ghi_chu": "một người đang mang thai 6 tháng"
  },
  {
    "ma_tuyen": "SGCT",
    "ngay_di": null,
    "ve_nguoi_lon": 4,
    "ve_tre_em": 0,
    "loai_cho": "ghe",
    "ghi_chu": "bà nội đi xe lăn"
  }
]
```

**Link trò chuyện:**
https://chatgpt.com/share/6b078eeb-5f94-83ec-8c22-a85816b169bd
## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
BÁO GIÁ VÉ – PHƯƠNG NAM EXPRESS
; 1. Đọc yêu cầu khách hàng
- Tuyến: SGDL – Sài Gòn → Đà Lạt
- Giá vé người lớn: 320.000 đồng/vé
- Người lớn: 8 người
- Trẻ em từ 5–10 tuổi: 3 bé (6, 7, 9 tuổi)
- Trẻ dưới 5 tuổi: 1 bé (2 tuổi, miễn phí)
- Hành lý cồng kềnh: 2 kiện
- Giảm giá đoàn: 5% (đoàn từ 6 người lớn trở lên)

; 2. Tính tiền vé người lớn

8 người lớn × 320.000 = 2.560.000 đồng

; 3. Tính tiền vé trẻ em

Trẻ em từ 5–10 tuổi được tính 75% giá vé người lớn:

320.000 × 75% = 240.000 đồng/vé

3 trẻ em × 240.000 = 720.000 đồng

Bé 2 tuổi: Miễn phí = 0 đồng

; 4. Tính giảm giá đoàn (5%)

Tổng tiền vé trước giảm:

2.560.000 + 720.000 = 3.280.000 đồng

Tiền giảm giá:

3.280.000 × 5% = 164.000 đồng

Tổng tiền vé sau giảm:

3.280.000 − 164.000 = 3.116.000 đồng

; 5. Tính phụ thu hành lý cồng kềnh

2 kiện × 100.000 = 200.000 đồng

(Phụ thu không áp dụng giảm giá)

; 6. Tổng tiền thanh toán

3.116.000 + 200.000 = 3.316.000 đồng

; 7. Kết quả cuối cùng
3.316.000 đồng
Tổng thanh toán – Phương Nam Express

[RESULT :3316000 đông ]
```

**Link trò chuyện:**
https://chatgpt.com/share/6b078f56-469c-83ec-a1c3-4c3d1e63d45d
### b) Kiểm tra kết quả AI
AI làm đúng các bước
## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**
```text
{
  "loai_su_co": "sai_loai_xe",
  "so_khach": 3,
  "so_chang_bi_doi": 2,
  "tom_tat": "Khách đặt xe giường nằm tuyến SG-ĐL nhưng cả 2 chặng đi và về đều bị đổi sang ghế ngồi."
}
```

**Link trò chuyện:**
https://share.gemini.google/5U4J8YYo3eSf
## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Tiêu chí	Điểm	Minh chứng	Đề xuất sửa
Đúng thông tin (50%)	0/5	“Vé đi Nha Trang bên em 350.000đ nha chị” – Sai giá vé, giá chuẩn là 380.000đ/vé người lớn. “Chị đổi trước 12 tiếng thì đổi free nha chị” – Sai chính sách, đổi trước 12 tiếng mất phí 20% giá vé.	Sửa giá vé thành 380.000đ/vé người lớn. Đổi vé trước 12 tiếng mất phí 20% = 76.000đ/vé.
Đầy đủ (30%)	1/3	Có trả lời cả giá vé và phí đổi vé nhưng chưa giải thích cụ thể mức phí. Không yêu cầu khách cung cấp ngày đi và số lượng vé để hỗ trợ đặt chỗ.	Nêu rõ phí đổi vé là 76.000đ/vé và hỏi khách ngày đi, số lượng vé.
Giọng điệu (20%)	1/2	“Xe xịn lắm luôn”, “free nha chị”, “Cần gì chị nhắn em liền!” – Cách diễn đạt hơi suồng sã, chưa chuyên nghiệp trong tư vấn dịch vụ.	Sử dụng từ ngữ lịch sự, rõ ràng, chuyên nghiệp và phù hợp với dịch vụ chăm sóc khách hàng.
Tổng điểm	2/10	Bài trả lời sai giá vé, sai chính sách đổi vé và chưa đáp ứng đầy đủ yêu cầu tư vấn.	Cần sửa lại nội dung theo thông tin chuẩn và bổ sung lời mời khách đặt vé.

Câu trả lời đề xuất
Dạ, vé tuyến Sài Gòn – Nha Trang bên Phương Nam Express có giá 380.000 đồng/vé người lớn.

Nếu chị muốn đổi ngày đi trước giờ xe chạy 12 tiếng, phí đổi vé là 20% giá vé, tương đương 76.000 đồng/vé.

Chị vui lòng cho em xin ngày đi dự kiến và số lượng vé để em hỗ trợ kiểm tra chuyến xe và đặt chỗ cho chị nhé!

Tổng điểm: 2/10.
```

**Link trò chuyện:**
https://chatgpt.com/share/6b0790fc-012c-83ec-9a52-4617d31dfe45