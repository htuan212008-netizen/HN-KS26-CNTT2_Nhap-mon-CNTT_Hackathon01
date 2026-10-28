# BÀI LÀM – HACKATHON 01

- **Mã đề:** 13
- **Họ tên:** Hồ Anh Tuấn
- **Lớp:** CNTT2
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
Get-ChildItem -Force
mv .\thoi_khoa_bieu.txt docs; mv .\logo_trung_tam_ngoai_ngu.PNG .\media\
cp .\media\logo_trung_tam_ngoai_ngu.PNG .\backup\
rm .\temp_213.tmp
cd .\logs\; Get-ChildItem -Force; cd ..

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
 Directory: C:\Thi giua ki\starter-kit\starter-kit\ngoai-ngu-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026   1:45 PM                backup
d-----        10/28/2026   1:39 PM                data
d-----        10/28/2026   1:45 PM                docs
d-----        10/28/2026   1:39 PM                logs
d-----        10/28/2026   1:45 PM                media
------        10/27/2026   1:31 AM             68 .env
-a----        10/27/2026   1:31 AM           2227 bai_lam.md


    Directory: C:\Thi giua ki\starter-kit\starter-kit\ngoai-ngu-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:31 AM           4365 logo_trung_tam_ngoai_ngu.PNG


    Directory: C:\Thi giua ki\starter-kit\starter-kit\ngoai-ngu-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:31 AM           6109 dang_ky_hoc_thang_3.xlsx


    Directory: C:\Thi giua ki\starter-kit\starter-kit\ngoai-ngu-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:31 AM             67 thoi_khoa_bieu.txt


    Directory: C:\Thi giua ki\starter-kit\starter-kit\ngoai-ngu-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:31 AM           1117 course.log


    Directory: C:\Thi giua ki\starter-kit\starter-kit\ngoai-ngu-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:31 AM           4365 logo_trung_tam_ngoai_ngu.PNG

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
Get-content .\logs\course.log | Select-string "ERROR" > .\logs\daily_report.txt
Get-content .\logs\daily_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-03-28 08:24:28 [ERROR] Het thoi gian cho (timeout)
2026-03-28 08:30:28 [ERROR] Het thoi gian cho (timeout)

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] Heading 1: tên dự án
- [ ] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [ ] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [ ] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [ ] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [ ] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\auto_report.ps1

```

### Kết quả hiển thị

```text
===BAO CAO LOI===

2026-03-28 08:24:28 [ERROR] Het thoi gian cho (timeout)
2026-03-28 08:30:28 [ERROR] Het thoi gian cho (timeout)
2026-03-28 08:33:28 [ERROR] Thanh toan hoc phi bi tu choi
2026-03-28 08:39:28 [ERROR] Thanh toan hoc phi bi tu choi
2026-03-28 08:42:28 [ERROR] Thanh toan hoc phi bi tu choi
2026-03-28 09:12:28 [ERROR] Het thoi gian cho (timeout)


```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
(Get-Content .\logs\course.log | Select-String "ERROR" | Measure-object).Count

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
6

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
"===TONG HOP LOG===" > .\logs\tong_hop.txt
Get-Content .\logs\course.log | Select-string "WARNING" >> .\logs\tong_hop.txt
(Get-Content .\logs\course.log | Select-String "ERROR" | Measure-object).Count >> .\logs\tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
===TONG HOP LOG===

2026-03-28 08:51:28 [WARNING] Thoi gian tai trang cham
2026-03-28 08:54:28 [WARNING] Video bai giang dung luong lon
2026-03-28 08:57:28 [WARNING] Thoi gian tai trang cham


6


```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/dang_ky_hoc_thang_3.xlsx`, không cần ghi vào đây.
