# QuanLyCamdo
| Họ và tên | MSSV | Lớp |
|-----------|------|-----|
| Hoàng Nhất Long | K235480106046 | K59KMT.K01 |

# Phần 1: Thiết kế sơ đồ ERD và tạo bảng
## 1) Thiết kế sơ đồ ERD
Sử dụng phần mềm online để thiết kế sơ đồ ERD (ERDPlus):
<img width="2186" height="1181" alt="image" src="https://github.com/user-attachments/assets/ec281c8c-599c-442f-9db5-397964b5373e" />
<br>
## 2) Chuẩn hóa các bảng  
- Bảng KhachHang: <img width="185" height="140" alt="image" src="https://github.com/user-attachments/assets/00572d6b-1816-4a98-8ec3-5d2ec9ff01de" /><br>  
- Bảng NhanVien: <img width="188" height="73" alt="image" src="https://github.com/user-attachments/assets/b78eb96e-bb36-4fbd-adad-75de9158e0e0" /><br>  
- Bảng LoaiTaiSan: <img width="189" height="57" alt="image" src="https://github.com/user-attachments/assets/98a7dd2f-3d5d-4149-a974-f2b12675bce0" /><br>  
- Bảng TaiSanChiTiet: <img width="182" height="106" alt="image" src="https://github.com/user-attachments/assets/296b880c-1d16-43a8-8540-e13abcc740ff" /><br>  
- Bảng HopDong: <img width="183" height="142" alt="image" src="https://github.com/user-attachments/assets/491fe36d-6073-4a2e-a597-52a0e55a062a" /><br>  
- Bảng KeHoachTraGop: <img width="182" height="125" alt="image" src="https://github.com/user-attachments/assets/67a7f6f9-d696-41e1-aaee-f551e3fbffc6" /><br>  
- Bảng PhieuThu: <img width="182" height="160" alt="image" src="https://github.com/user-attachments/assets/2caf6d36-4517-4cad-b715-6612c93b23df" /><br>  
- Bảng BienDong: <img width="181" height="108" alt="image" src="https://github.com/user-attachments/assets/c6d0d97a-5390-490e-b1a3-ded123dcae9b" /><br>  
<br>

## 3) Xây dựng bảng trên SQL và tạo mối quan hệ liên kết
a) Tạo database QuanLyCamDo
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/6e4c3bb5-989e-4496-a6f3-71e02bfce016" />   
b) Tạo các bảng  
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/186da7cd-b4d7-4fba-99e0-d1a39c3ebc5b" />
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/6d49b56d-5c0b-4202-8feb-d254f9dbb527" />
<img width="959" height="538" alt="image" src="https://github.com/user-attachments/assets/11d6b16e-f8d3-41aa-94b2-8d574e846649" />
  
c) Điền thông tin nhân viên để chuẩn bị tạo hợp đồng
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/3dc7e6a6-6a97-4ebc-a541-f4791fe7cf19" />  
<br>  

# Phần 2: Cài đặt SQL (viết Scrips)  
## 1) Đăng ký hợp đồng mới  
- Viết Store procedure tiếp nhận hợp đồng: Lưu thông tin khách hàng, danh sách tài sản (kèm giá trị định giá), Số tiền vay gốc, thiết lập Deadline1 (Hạn thanh toán thỏa thuận), Deadline2 (Gia hạn thanh toán theo lãi kép).
- Thêm cột GiaTriTaiSan và bảng ChiTietTaiSan:  
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/6b21aa18-4466-4a9a-90d4-c4e34666647f" /><br>

- Tạo Store Procedure:  
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/56e9b333-80b1-4786-bb97-cb1d90574a78" />
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/390c2ef7-c986-4f25-9f14-0ece2d763493" />
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/065e93cb-978f-4055-a139-8af8f0dc50f7" /><br>

- Test thử Store procedure đã tạo:
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/5cd94e03-f587-4a12-95f4-0bf6e3c0ea42" />
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/5e79999a-7bf2-40d1-aab9-1052475ee9bb" /><br>

## 2) Tính toán công nợ thời gian thực


















