# Book Hashtag

## Mô tả

Book Hashtag là một ứng dụng/thư viện giúp quản lý và tạo hashtag cho sách, hỗ trợ người dùng trong việc phân loại, tìm kiếm và chia sẻ thông tin về sách thông qua hashtag.

## Tính năng

-  Tạo hashtag tự động cho sách dựa trên thể loại, tác giả, và nội dung
-  Tìm kiếm sách thông qua hashtag
-  Thống kê và phân tích hashtag phổ biến
-  Quản lý danh sách hashtag cá nhân
-  Giao diện thân thiện với người dùng

## Cài đặt

### Yêu cầu hệ thống
- Python 3.8+
- Node.js 14+ (nếu có frontend)
- Git

### Hướng dẫn cài đặt

1. Clone repository:
```bash
git clone https://github.com/lmtndy/book_hashtag.git
cd book_hashtag
```

2. Tạo môi trường ảo:
```bash
python -m venv venv
source venv/bin/activate  # Trên Windows: venv\Scripts\activate
```

3. Cài đặt dependencies:
```bash
pip install -r requirements.txt
```

4. Cấu hình database (nếu có):
```bash
python manage.py migrate
```

5. Chạy ứng dụng:
```bash
python main.py
```

## Sử dụng

### Tạo hashtag cho sách

```python
from book_hashtag import BookHashtagGenerator

generator = BookHashtagGenerator()
book_info = {
    "title": "Tên sách",
    "author": "Tác giả",
    "genre": "Thể loại",
    "description": "Mô tả sách"
}

hashtags = generator.generate_hashtags(book_info)
print(hashtags)
# Output: ['#tiểu_thuyết', '#việt_nam', '#tình_yêu', '#văn_học_đương_đại']
```

### Tìm kiếm sách theo hashtag

```python
from book_hashtag import BookSearch

searcher = BookSearch()
results = searcher.search_by_hashtag("#tiểu_thuyết")
print(results)
```

## API Documentation

### Endpoints

#### `POST /api/hashtags/generate`
Tạo hashtag cho sách

**Request Body:**
```json
{
  "title": "Tên sách",
  "author": "Tác giả", 
  "genre": "Thể loại",
  "description": "Mô tả"
}
```

**Response:**
```json
{
  "hashtags": ["#tag1", "#tag2", "#tag3"],
  "confidence": 0.85
}
```

#### `GET /api/books/search?hashtag={hashtag}`
Tìm kiếm sách theo hashtag

**Response:**
```json
{
  "books": [
    {
      "id": 1,
      "title": "Tên sách",
      "author": "Tác giả",
      "hashtags": ["#tag1", "#tag2"]
    }
  ],
  "total": 1
}
```

## Cấu trúc thư mục

```
book_hashtag/
├── src/
│   ├── models/          # Các model dữ liệu
│   ├── services/        # Logic xử lý chính
│   ├── api/            # API endpoints
│   └── utils/          # Utilities và helpers
├── tests/              # Test cases
├── docs/               # Tài liệu
├── requirements.txt    # Python dependencies
├── config.py          # Cấu hình ứng dụng
└── main.py           # Entry point
```

## Đóng góp

Chúng tôi hoan nghênh mọi đóng góp! Vui lòng:

1. Fork repository
2. Tạo feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Tạo Pull Request

### Quy tắc đóng góp
- Viết test cho code mới
- Tuân thủ coding style hiện tại
- Cập nhật documentation nếu cần
- Đảm bảo tất cả test pass

## Testing

Chạy test:
```bash
python -m pytest tests/
```

Chạy test với coverage:
```bash
python -m pytest --cov=src tests/
```

## Giấy phép

Dự án này được cấp phép dưới [MIT License](LICENSE).

## Liên hệ

- Tác giả: [lmtndy](https://github.com/lmtndy)
- Email: lamtanduy1605@gmail.com
- Issues: [GitHub Issues](https://github.com/lmtndy/book_hashtag/issues)

## Roadmap

- [ ] Tích hợp AI để tạo hashtag thông minh hơn
- [ ] Hỗ trợ nhiều ngôn ngữ
- [ ] Mobile app
- [ ] Tích hợp với các nền tảng sách phổ biến
- [ ] API rate limiting
- [ ] Caching system

## Changelog

### v1.0.0 (2025-01-XX)
- Phiên bản đầu tiên
- Tính năng tạo hashtag cơ bản
- API endpoints cơ bản
- Web interface đơn giản

---

 Nếu dự án hữu ích, hãy cho chúng tôi một star trên GitHub!
