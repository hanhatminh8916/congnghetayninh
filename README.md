# congnghetayninh.id.vn → Chrome Web Store

Trang chuyển hướng tối giản: truy cập `https://congnghetayninh.id.vn` sẽ mở thẳng
trang cài đặt tiện ích **226789 – AI Screen Assistant** trên Chrome Web Store.

- Đích đến: <https://chromewebstore.google.com/detail/mijpkahfmmldfoijfgclibogknhknknc>
- Host: GitHub Pages (miễn phí, HTTPS tự động)
- Tệp chính: `index.html` (chuyển hướng bằng JS + nút dự phòng), `404.html`, `CNAME`

## Cấu hình DNS (bắt buộc — làm tại PA Vietnam)

Vào trang quản trị DNS của tên miền `congnghetayninh.id.vn` (PA Vietnam / id.vn),
**xoá các bản ghi A cũ** (đang trỏ tới IP parking) rồi thêm:

| Loại | Tên (Host) | Giá trị |
|------|------------|---------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `hanhatminh8916.github.io` |

Tuỳ chọn (IPv6), thêm 4 bản ghi `AAAA` cho `@`:

```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```

Sau khi DNS đã trỏ đúng, vào **Settings → Pages** của repo và bật **Enforce HTTPS**
(GitHub cần vài phút → tối đa 24h để cấp chứng chỉ Let's Encrypt).

## Kiểm tra nhanh

```powershell
Resolve-DnsName congnghetayninh.id.vn -Type A
curl.exe -I https://congnghetayninh.id.vn
```
