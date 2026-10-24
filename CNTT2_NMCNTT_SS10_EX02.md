# Bài 2 : Khắc phục sự cố dữ liệu trong kho thiết bị IoT

## **4. Yêu cầu đầu ra**

- **Phần 1 (Phân tích):** Liệt kê ít nhất 3 quy tắc vàng mà bảng tính hiện tại đang vi phạm. 
    + 1. Quy tắc cấu trúc liên tục: Một bảng dữ liệu chuẩn không được phép chứa các hàng hoặc cột trống hoàn toàn ở giữa.
    + 2. Quy tắc tính đồng nhất và toàn vẹn dữ liệu: Mỗi giá trị đại diện cho một đối tượng phải được viết chuẩn hóa, đồng nhất 100%
    + 3. Quy tắc "Một ô, một giá trị" - Không trộn ô: Mỗi ô trong bảng tính chỉ chứa đúng một giá trị duy nhất và không được gộp ô.
- **Phần 2 (Hoàn thiện):** Sử dụng hàm TRIM để làm sạch cột "Trạng thái". Xóa bỏ các hàng trống và gỡ bỏ Merge Cell để Filter hoạt động chính xác trên toàn bộ vùng dữ liệu.
```
Sử dụng hàm TRIM đối với:
- Vi phạm 1 (khoảng trống):  =COUNTA(TRIM(An),TRIM(Bn),TRIM(Cn),...) (An = cột A dòng thứ n *Bn, Cn,... đều như vậy)
- Vi phạm 2 (xoá dữ liệu thừa như khoảng trống trong ô dữ liệu): =TRIM(X) (X là ô dữ liệu cần xoá)
- Vi phạm 3 (xoá trộn ô, ô nhó:m): =IF(TRIM(A1="","Nhập_tên_tiêu_đề_mới",TRIM(A1)))
```