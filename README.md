# ds = []

while True:
    print("\n1. Thêm sinh viên mới | 2. Xem thông tin sinh viên | 3. Xóa sinh viên | 4. Bảng xếp hạng | 0. Thoát")
    chon = input("Chọn: ")

    if chon == "1":
        mssv = input("MSSV: ")
        ten = input("Tên: ")
        tuoi = input("Tuổi: ")
        t = float(input("Điểm Toán: "))
        l = float(input("Điểm Lý: "))
        h = float(input("Điểm Hóa: "))
        tong = t + l + h         
        loai = "Giỏi" if tong / 3 >= 8 else ("Khá" if tong / 3 >= 6.5 else "TB")
        ds.append([mssv, ten, tuoi, t, l, h, loai, tong])
        print("Đã thêm!")

    elif chon == "2":
        for sv in ds:
            print("MSSV:", sv[0], "| Tên:", sv[1], "| Tuổi:", sv[2], "| Toán:", sv[3], "| Lý:", sv[4], "| Hóa:", sv[5], "| Loại:", sv[6])

    elif chon == "3":
        ma = input("Nhập MSSV cần xóa: ")
        for sv in ds:
            if sv[0] == ma:
                ds.remove(sv)
                print("Đã xóa!")
                break

    elif chon == "4":
        # Cách viết dài bằng def:
        def sap_xep(ds):
            return sorted(ds, key=lambda x: x[7], reverse=True)
        ds = sap_xep(ds)
        for sv in ds:
            print("Tên:", sv[1], "| Tổng điểm:", sv[7])

    elif chon == "0":
        print("Xin chào, và hẹn gặp lại.")
        break
    elif chon == "4":
        ds.sort(key=lambda x: x[7], reverse=True)
        for sv in ds:
            print(sv[1], "- Tổng điểm:", sv[7])

    elif chon == "0":
        print("Xin chào, và hẹn gặp lại.")
        break
