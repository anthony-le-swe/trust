# review-nyc

Ứng dụng web **ExCheck** để cộng đồng chia sẻ review người yêu cũ và check auth FB/Instagram (real/fake).

![ExCheck preview](assets/readme-preview.svg)

## Stack hiện tại

- Frontend: HTML/CSS/JS thuần
- Database online: **Supabase (PostgreSQL)**
- Fallback: nếu chưa cấu hình Supabase thì chạy dữ liệu demo local

## Tính năng

- Thêm review mối quan hệ có bằng chứng.
- Bắt buộc bằng chứng bổ sung nếu review tiêu cực.
- Tìm kiếm/lọc review theo tên, khu vực, sentiment.
- Gửi auth-report cho link FB/Instagram (real/fake/chưa rõ).
- Tra cứu theo link profile + upvote/downvote từng báo cáo.

## Cấu hình Supabase

### 1) Tạo bảng

Chạy SQL trong file `supabase/schema.sql` trên Supabase SQL Editor.

### 2) Cấu hình URL + ANON KEY

Mở file `config.js` và điền:

```js
window.EXCHECK_SUPABASE_URL = "https://<project-ref>.supabase.co";
window.EXCHECK_SUPABASE_ANON_KEY = "<your-anon-key>";
```

> Không commit service_role key vào frontend.

### 3) Chạy local

```bash
python3 -m http.server 4173
```

Mở `http://localhost:4173`.
