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
- Thêm cột GiaTriTaiSan vào bảng ChiTietTaiSan:  
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/6b21aa18-4466-4a9a-90d4-c4e34666647f" /><br>

- Tạo Store Procedure:  
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/56e9b333-80b1-4786-bb97-cb1d90574a78" />
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/390c2ef7-c986-4f25-9f14-0ece2d763493" />
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/065e93cb-978f-4055-a139-8af8f0dc50f7" /><br>

- Test thử Store procedure đã tạo:
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/5cd94e03-f587-4a12-95f4-0bf6e3c0ea42" />
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/5e79999a-7bf2-40d1-aab9-1052475ee9bb" /><br>

## 2) Tính toán công nợ thời gian thực
a) Hàm Function tính tiền phải trả trước hạn Deadline1
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/3d62f3c0-b3b7-4437-b6c6-becaa41fbd76" /><br>  
b) Hàm Function tính tiền phải trả khi quá Deadline1 và trước DeadLine2  
Thêm một biến thể hiện ngày khách đến trả tiền (vì có thể trả trước hạn deadline2, quá deadline2 là trả trong đồn)
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/95f2aca4-bd03-4124-8da2-a1ce5a3b5814" />
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/039bc775-2df3-4b84-a0fc-3332a1b0fc82" /><br>  
 
c) Chạy thử các hàm với HD001 và HD002 đồng thời điền thông tin vào PhieuThu
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/4f9f23aa-53d8-4d5e-b0b2-ef41a6acda29" /><br>  
Kết quả: Vì cả 2 HD không đăng ký Trả góp lên MaKHG = Null
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/6cfb91d8-5370-4284-914d-dbd861a7762d" /><br>  

# Phần 3: Xử lý trả nợ và hoàn trả tài sản
- Thêm một cột IsSold vào bảng HopDong kiểu BIT (0 là chưa bán, 1 là đã thanh lý)
``` SQL
ALTER TABLE HopDong 
ADD IsSold BIT DEFAULT 0; -- 0: Chưa bán, 1: Đã bán thanh lý
```
- Viết Store Procedure:
``` SQL
CREATE PROCEDURE sp_XuLyHoanTra
    @MaHD VARCHAR(10),
    @MaNV VARCHAR(10),
    @SoTienKhachTra DECIMAL(14, 2)
AS
BEGIN
    SET NOCOUNT ON;
    DECLARE @Deadline1 DATE, @Deadline2 DATE, @IsSold BIT, @GocBanDau DECIMAL(14, 2);
    DECLARE @TongNoHienTai DECIMAL(14, 2), @TienLaiHienTai DECIMAL(14, 2);
    DECLARE @NgayHienTai DATE = GETDATE();
    DECLARE @MaKH VARCHAR(10);

    -- 1. Lấy thông tin từ Hợp đồng
    SELECT 
        @Deadline1 = NgayTra, 
        @IsSold = IsSold, 
        @GocBanDau = TienVay,
        @MaKH = MaKH 
    FROM HopDong WHERE MaHD = @MaHD;

    SET @Deadline2 = DATEADD(day, 60, @Deadline1);

    -- 2. Kiểm tra tài sản (Chặn nếu đã thanh lý)
    IF (@NgayHienTai > @Deadline2 AND @IsSold = 1)
    BEGIN
        PRINT N'Tài sản đã thanh lý. Không thu tiền, Không trả đồ!';
        RETURN;
    END

    -- 3. Tính toán nợ thực tế để so sánh
    IF (@NgayHienTai <= @Deadline1)
        SELECT @TongNoHienTai = TongPhaiTra, @TienLaiHienTai = TienLaiD1 FROM dbo.fn_TienPhaiTraTruocDeadline1(@MaHD);
    ELSE
        SELECT @TongNoHienTai = TongPhaiTra, @TienLaiHienTai = TongTatCaTienLai FROM dbo.fn_TienPhaiTraQuaHanD2(@MaHD, @NgayHienTai);

    -- 4. Ghi nhận Phiếu thu
    -- Logic: Thu Gốc trước, dư mới thu Lãi
    DECLARE @TienGocVuaThu DECIMAL(14,2) = CASE WHEN @SoTienKhachTra >= @GocBanDau THEN @GocBanDau ELSE @SoTienKhachTra END;
    DECLARE @TienLaiVuaThu DECIMAL(14,2) = CASE WHEN @SoTienKhachTra > @GocBanDau THEN @SoTienKhachTra - @GocBanDau ELSE 0 END;

    INSERT INTO PhieuThu (MaPhieu, MaHD, MaNV, NgayDong, TienGocThu, TienLaiThu, TrangThai)
    VALUES ('PT_' + @MaHD, @MaHD, @MaNV, @NgayHienTai, @TienGocVuaThu, @TienLaiVuaThu, N'Đã thu tiền');

    -- 5. PHÂN LUỒNG TRẠNG THÁI
    IF (@SoTienKhachTra >= @TongNoHienTai)
    BEGIN
        -- TRƯỜNG HỢP 1: TRẢ ĐỦ -> Tất toán
        UPDATE HopDong SET TrangThai = N'Đã thanh toán đủ' WHERE MaHD = @MaHD;
        PRINT N'Hợp đồng đã trả hết. Không cần lập kế hoạch trả góp.';
    END
    ELSE
    BEGIN
        -- TRƯỜNG HỢP 2: TRẢ THIẾU -> Chuyển sang "Đang trả góp" và TẠO KẾ HOẠCH
        UPDATE HopDong SET TrangThai = N'Đang trả góp' WHERE MaHD = @MaHD;

        -- Tính số tiền còn nợ để đưa vào kế hoạch trả tiếp
        DECLARE @GocConNo DECIMAL(14,2) = CASE WHEN @GocBanDau > @TienGocVuaThu THEN @GocBanDau - @TienGocVuaThu ELSE 0 END;
        DECLARE @LaiConNo DECIMAL(14,2) = CASE WHEN @TienLaiHienTai > @TienLaiVuaThu THEN @TienLaiHienTai - @TienLaiVuaThu ELSE 0 END;

        -- Chèn thông tin vào bảng KeHoachTraGop (Chỉ tạo khi đang trả góp)
        INSERT INTO KeHoachTraGop (MaKHG, MaHD, NgayHan, TienGocPTra, TienLaiPTra, TrangThai)
        VALUES (
            'KHG_'+@MaHD, 
            @MaHD, 
            DATEADD(day, 30, @NgayHienTai), -- Hẹn 30 ngày sau trả tiếp
            @GocConNo, 
            @LaiConNo, 
            N'Chưa trả'
        );

        PRINT N'Đã chuyển trạng thái sang Đang trả góp và tạo lịch hẹn trả nợ mới.';
    END
END
```
<br>  

- Kết quả:
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/474e282f-284b-45ca-96d1-77c46cb943d1" /><br>
- Thử nghiệm với KH003 và KH004 với KH003 sẽ trả hết và được nhận lại đồ, KH004 sẽ thực hiện trả góp
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/5c123f30-51a9-4c2e-8580-01d604d929d8" /><br>

# Phần 4: Truy vấn danh sách nợ xấu (khó đòi)
- Viết Function:
``` SQL
-- =============================================
-- Author:		<Hoàng Nhất Long>
-- Create date: <11-05-2026>
-- Description:	<Danh sách nợ xấu>
-- =============================================
CREATE FUNCTION fn_DanhSachNoXau(
    @NgayKiemTra DATE
)
RETURNS TABLE
AS
RETURN
(
    SELECT 
        kh.HoDem,
        kh.Ten,
        kh.SDT,
        hd.MaHD,
        hd.TienVay AS Tienvay,
        hd.NgayTra AS NgayTra,
        DATEDIFF(day, hd.NgayTra, @NgayKiemTra) AS SoNgayQuaHan,
        -- Sử dụng hàm tính lãi kép đã viết trước đó để tính tổng nợ
        (SELECT TongPhaiTra FROM dbo.fn_TienPhaiTraQuaHanD2(hd.MaHD, @NgayKiemTra)) AS TongNoHienTai,
        -- Dự báo nợ nếu để thêm 1 tháng nữa
        (SELECT TongPhaiTra FROM dbo.fn_TienPhaiTraQuaHanD2(hd.MaHD, DATEADD(month, 1, @NgayKiemTra))) AS TongNoSau1Thang
    FROM HopDong hd
    JOIN KhachHang kh ON hd.MaKH = kh.MaKH
    WHERE 
        hd.NgayTra < @NgayKiemTra              -- Điều kiện 1: Quá ngày hẹn trả
        AND hd.TrangThai <> N'Đã thanh toán đủ' -- Điều kiện 2: Chưa trả hết tiền
);
```
- Kết quả:
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/0971e471-38cf-4e7c-a56a-d04d42c73b0a" />
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/c61d8e82-e87c-46d8-b032-3571d499c2c0" />
<br>

# Phần 5: Quản lý thanh lý tài sản
- Thêm cột TrangThai vào bảng ChiTietTaiSan và điền thông tin (Sẵn sàng thanh lý/ Đã bán thanh lý)
``` SQL
ALTER TABLE TaiSanChiTiet
ADD TrangThai NVARCHAR(50)
```
- Trigger cập nhập trạng thái Quá hạn (nợ xấu) của trạng thái hợp đồng: (chạy sau khi thêm/sửa)
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/0718522c-bbd0-4c99-8e3a-d84c54e0999b" /> <br>
- Kiểm thử:
``` SQL
-- Thêm một hợp đồng thử nghiệm đã quá hạn
INSERT INTO HopDong (MaHD, MaKH, MaNV, TienVay, Lai, NgayVay, NgayTra, IsSold, TrangThai)
VALUES ('HD008', 'KH008', 'NV004', 50000000, 5, '2026-04-01 15:09:25', '2026-05-10', 0, N'Chưa trả');
```
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/2ae8f52d-1a6e-4305-b4fe-94d4fd07ce8c" /><br>  

- Viết Trigger chuyển TrangThai của bảng TaiSanChiTiet thành "Sẵn sàng thanh lý" khi HopDong ở TrangThai = "Quá hạn (Nợ xấu) và ngày vượt quá deadline2:
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/ef5455b1-df11-4b82-8617-dd67c61c7b71" /><br>
- Kiểm thử:
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/e346c04e-b92e-4c76-ab67-0ca97d6de137" /><br>


- Viết trigger chuyển TrangThai của bảng TaiSanChiTiet thành "Đã bán thanh lý" sau khi TrangThai của HopDong chuyển sang "Đã thanh lý"
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/93cc27b0-b384-44ae-b66a-ef6fdcb9cce4" /><br>

- Chạy thử: (Các trường NULL là do không thỏa mãn điều kiện)
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/f22c2288-77f3-4993-9f59-6f93d40ca62e" /><br>

# Phần 6: Sự kiện bổ sung: Gia hạn hợp đồng
- Viết Store Procedure thực hiện gia hạn hợp đồng khi khách đến trả hết lãi của hiện tại và cập nhập lại ngày vay và hạn trả. Đồng thời ghi vào phiếu thu thông tin về số tiền lãi đóng
``` SQL
CREATE PROCEDURE sp_GiaHanHopDong
    @MaHD VARCHAR(10),
    @MaNV VARCHAR(10),
    @SoThangGiaHan INT -- Số tháng muốn gia hạn thêm
AS
BEGIN
    SET NOCOUNT ON;
    
    DECLARE @TongLaiHienTai DECIMAL(14, 2);
    DECLARE @NgayHienTai DATE = GETDATE();
    DECLARE @NgayTraMoi DATE;

    -- 1. Tính toán số tiền lãi khách phải trả đến thời điểm hiện tại
    -- Sử dụng hàm tính lãi tổng hợp (bao gồm lãi đơn và lãi kép nếu có)
    IF (@NgayHienTai <= (SELECT NgayTra FROM HopDong WHERE MaHD = @MaHD))
    BEGIN
        SELECT @TongLaiHienTai = TienLaiD1 
        FROM dbo.fn_TienPhaiTraTruocDeadline1(@MaHD);
    END
    ELSE
    BEGIN
        SELECT @TongLaiHienTai = TongTatCaTienLai 
        FROM dbo.fn_TienPhaiTraQuaHanD2(@MaHD, @NgayHienTai);
    END

    -- 2. Ghi nhận vào bảng PhieuThu (Chỉ thu tiền lãi)
    INSERT INTO PhieuThu (MaPhieu, MaHD, MaNV, NgayDong, TienGocThu, TienLaiThu, TrangThai)
    VALUES (
        'PT_' + @MaHD,
        @MaHD,
        @MaNV,
        @NgayHienTai,
        0, -- Tiền gốc không đổi
        @TongLaiHienTai, -- Thu toàn bộ lãi
        N'Gia hạn - Thu lãi'
    );

    -- 3. Cập nhật Hợp đồng sang kỳ hạn mới
    -- Ngày vay mới tính từ hôm nay, Deadline 1 dời đi @SoThangGiaHan
    SET @NgayTraMoi = DATEADD(MONTH, @SoThangGiaHan, @NgayHienTai);

    UPDATE HopDong
    SET NgayVay = @NgayHienTai,
        NgayTra = @NgayTraMoi,
        TrangThai = N'Đang vay' 
    WHERE MaHD = @MaHD;

    PRINT N'Gia hạn thành công. Tổng lãi đã thu: ' + CAST(@TongLaiHienTai AS VARCHAR);
    PRINT N'Hạn trả mới (Deadline 1): ' + CONVERT(VARCHAR, @NgayTraMoi, 103);
END;
```
- Giả sử khách hàng KH007 đến trả lãi và có nhu cầu gia hạn thêm:
<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/2fc029cc-15f5-4a3b-92ea-0d9f7a7a0cde" />





























