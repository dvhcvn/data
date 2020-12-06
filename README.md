# Thông tin về các đơn vị hành chính Việt Nam qua từng năm

Dữ liệu được cập nhật từ trang [Danh mục hành chính](https://danhmuchanhchinh.gso.gov.vn) của Tổng cục thống kê.

## Các tập dữ liệu

### data.json

Thông tin 3 cấp đơn vị hành chính được thu thập bởi [daohoangson/dvhcvn](https://github.com/daohoangson/dvhcvn):

- Tỉnh thành:
  - `level1_id`
  - `name`
  - `type`: Thành phố Trung ương | Tỉnh
  - `level2s`
- Quận huyện
  - `level2_id`
  - `name`
  - `type`: Quận | Huyện | Thành phố | Thị xã
  - `level3s`
- Phường xã
  - `level3_id`
  - `name`
  - `type`: Phường | Xã | Thị trấn

Ví dụ:

```json
{
  "level1_id": "56",
  "name": "Tỉnh Khánh Hòa",
  "type": "Tỉnh",
  "level2s": [
    {
      "level2_id": "568",
      "name": "Thành phố Nha Trang",
      "type": "Thành phố",
      "level3s": [
        {
          "level3_id": "22363",
          "name": "Phường Lộc Thọ",
          "type": "Phường"
        },
        "..."
      ]
    },
    "..."
  ]
```

### tree.json

Thông tin về các đơn vị hành chính từ trước đến nay (bao gồm cả tên cũ, các đơn vị đã bị xoá) theo cấu trúc cây.

Ví dụ: Hà Nội tách huyện Từ Liêm thành ha quận Bắc Từ Liêm và Nam Từ Liêm theo [nghi định 132/NQ-CP](https://github.com/daohoangson/dvhcvn-historical-data/commit/e2440d87f1e44d6a4b80c9491d31148b2e27ce50).
Thông tin cả cũ và mới đều có trong `tree.json`:

```json
{
    "Thành phố Hà Nội": {
        "...": "...",
        "Huyện Từ Liêm": [
            "Thị trấn Cầu Diễn",
            "Xã Thượng Cát",
            "Xã Liên Mạc",
            "Xã Đông Ngạc",
            "Xã Thụy Phương",
            "Xã Tây Tựu",
            "Xã Xuân Đỉnh",
            "Xã Minh Khai",
            "Xã Cổ Nhuế",
            "Xã Phú Diễn",
            "Xã Xuân Phương",
            "Xã Mỹ Đình",
            "Xã Tây Mỗ",
            "Xã Mễ Trì",
            "Xã Đại Mỗ",
            "Xã Trung Văn"
        ],
        "...": "...",
        "Quận Nam Từ Liêm": [
            "Phường Cầu Diễn",
            "Phường Xuân Phương",
            "Phường Phương Canh",
            "Phường Mỹ Đình 1",
            "Phường Mỹ Đình 2",
            "Phường Tây Mỗ",
            "Phường Mễ Trì",
            "Phường Phú Đô",
            "Phường Đại Mỗ",
            "Phường Trung Văn"
        ],
        "Quận Bắc Từ Liêm": [
            "Phường Thượng Cát",
            "Phường Liên Mạc",
            "Phường Đông Ngạc",
            "Phường Đức Thắng",
            "Phường Thụy Phương",
            "Phường Tây Tựu",
            "Phường Xuân Đỉnh",
            "Phường Xuân Tảo",
            "Phường Minh Khai",
            "Phường Cổ Nhuế 1",
            "Phường Cổ Nhuế 2",
            "Phường Phú Diễn",
            "Phường Phúc Diễn"
        ]
    },
    "..."
}
```

## Nguồn tham khảo

- Tổng cục thống kê https://danhmuchanhchinh.gso.gov.vn
- https://github.com/daohoangson/dvhcvn/tree/master/history
