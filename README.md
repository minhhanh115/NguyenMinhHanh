# NguyenMinhHanh
BTVN
# Bài tập môn Hệ quản trị cơ sở dữ liệu, Lớp: 59KMT

---

## 1. Cài đặt SQL Server 2025 Developer

Download và cài đặt SQL Server 2025 phiên bản Developer 
<img width="1920" height="1080" alt="Screenshot (170)" src="https://github.com/user-attachments/assets/c7fea634-2807-474d-967e-2d278765df28" />

---

## 2. Cấu hình cổng động (Dynamic Port)

<img width="1920" height="1080" alt="Screenshot (171)" src="https://github.com/user-attachments/assets/b70ab26a-9d47-4ca1-a864-bc72e498b9f0" />


---

## 3. Kiểm tra service SQL Server và cổng đang mở

<img width="1920" height="1080" alt="Screenshot (172)" src="https://github.com/user-attachments/assets/a50d7b08-8977-49b6-a399-4af3767a81bf" />




## 4. Cài đặt SQL Server Management Studio (SSMS)

<img width="1920" height="1080" alt="Screenshot (174)" src="https://github.com/user-attachments/assets/5f1c7e38-af52-4ade-9c0e-bea74580d3a2" />




---

## 5. Đăng nhập SQL Server bằng 2 cách

Servername: `localhost,xxxxx` (với `xxxxx` là cổng đã chọn ở mục 2)

**Windows Authentication:**

<img width="1920" height="1080" alt="Screenshot (175)" src="https://github.com/user-attachments/assets/962a1f72-24fd-4a00-92dc-abf3afa55443" />

SQL Server Authentication:
<img width="1920" height="1080" alt="Screenshot (176)" src="https://github.com/user-attachments/assets/8da6283f-1842-4286-b5ce-c6e39eb4a609" />


---

## 6. Tạo cơ sở dữ liệu mới

Dùng giao diện đồ hoạ SSMS tạo database mới và kiểm tra đường dẫn các file.

<img width="1920" height="1080" alt="Screenshot (177)" src="https://github.com/user-attachments/assets/3951e7a6-75fc-4c5f-9774-5209eb87e2f8" />


---

## 7. Tạo bảng dữ liệu (Table)

<img width="1920" height="1080" alt="Screenshot (178)" src="https://github.com/user-attachments/assets/6438d7fe-3bfa-450c-98bb-8648f5347f66" />



## 8. Import dữ liệu từ file CSV

Dùng giao diện đồ hoạ SSMS import dữ liệu từ file mẫu vào bảng vừa tạo.
<img width="1920" height="1080" alt="Screenshot (179)" src="https://github.com/user-attachments/assets/b9287b95-089d-47f8-aff0-93b2fcb2e6dd" />



---

## 9. Kiểm tra số dòng sau khi import

Mở cửa sổ gõ lệnh trong SSMS, chạy lệnh đếm số dòng. Kết quả hợp lệ: **khoảng 12020 dòng**.

```sql
SELECT COUNT(*) FROM hihi;
```
<img width="1920" height="1080" alt="Screenshot (180)" src="https://github.com/user-attachments/assets/e4c5c3c9-97a3-407c-b4da-0c66ce0c3522" />



## 10. Thêm 1 dòng dữ liệu cá nhân (INSERT)

Gõ lệnh INSERT để thêm thông tin cá nhân của bản thân vào bảng.


<img width="1920" height="1080" alt="Screenshot (181)" src="https://github.com/user-attachments/assets/6563d5aa-bf53-4d3f-ab5d-4b13fb4d070d" />



## 11. Cập nhật nơi sinh thành 'Sao Hoả' (UPDATE)

Gõ lệnh UPDATE để cập nhật trường `noisinh` thành `'Sao Hoả'` cho những dòng có `noisinh` và `diachi` đều là `NULL`.

```sql
UPDATE hihi
SET noisinh = N'Sao Hoả'
WHERE noisinh='NULL' AND diachi='NULL';
```

<img width="1920" height="1080" alt="Screenshot (182)" src="https://github.com/user-attachments/assets/64ec8d14-7bb0-4497-a878-25571498c3dc" />


## 12. Tạo bảng SaoHoa từ SELECT INTO

Dùng giao diện đồ hoạ SSMS tạo bảng **SaoHoa** gồm những sinh viên có nơi sinh là `'Sao Hoả'`.

```sql
SELECT * INTO SaoHoa
FROM hihi
WHERE noisinh = N'Sao Hoả';
```
<img width="1920" height="1080" alt="Screenshot (183)" src="https://github.com/user-attachments/assets/b9b01326-9d6d-4522-8bc1-6438eda8f3fc" />


## 13. Xoá sinh viên cùng họ trong bảng SaoHoa (DELETE)

Gõ lệnh DELETE trong bảng **SaoHoa** để xoá những sinh viên cùng họ với bản thân *(họ Nguyễn)*.

```sql
DELETE FROM SaoHoa
WHERE hoten LIKE N'Nguyễn%';
```
<img width="1920" height="1080" alt="Screenshot (185)" src="https://github.com/user-attachments/assets/e2864eca-c250-4cea-badd-758986c3aba6" />




## 14. Xuất kết quả ra file dulieu.sql

Dùng giao diện đồ hoạ SSMS xuất toàn bộ kết quả của các mục 6 → 13 ra file **dulieu.sql**.

<img width="1920" height="1080" alt="Screenshot (187)" src="https://github.com/user-attachments/assets/07db862a-1d08-4852-b55a-975669a1ef52" />


## 15. Xoá cơ sở dữ liệu và kiểm tra file

Dùng giao diện đồ hoạ SSMS xoá database đã tạo. Sau khi xoá thành công, mở path đã chọn ở mục 6 kiểm tra 2 file `.mdf` và `.ldf` còn tồn tại hay không.



Xóa cơ sở dữ liệu.
<img width="1920" height="1080" alt="Screenshot (188)" src="https://github.com/user-attachments/assets/320e13f9-7ee6-49da-8f19-09f51e9b0884" />




Kiểm tra các file sau khi xóa.
<img width="1920" height="1080" alt="Screenshot (189)" src="https://github.com/user-attachments/assets/3b0187bc-c598-479c-afc8-2d8f4f16fdf5" />


## 16. Chạy lại file dulieu.sql để khôi phục

Mở cửa sổ gõ lệnh trong SSMS, mở file **dulieu.sql** của mục 14 và chạy toàn bộ các lệnh.


<img width="1920" height="1080" alt="Screenshot (191)" src="https://github.com/user-attachments/assets/5da2b5c0-d874-46b8-b4d0-bae01e50e086" />



## 17. Upload file dulieu.sql lên GitHub

Upload file **dulieu.sql** lên repository GitHub cá nhân (repository đang chứa file README.md này).

