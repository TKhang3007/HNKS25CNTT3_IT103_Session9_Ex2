1. Phân tích lỗi
Lỗi	                        Code sai	                                        Nguyên nhân	                                                        Cách sửa
1. Lấy giá phòng            bookingReservation.priceKey                         JavaScript tìm thuộc tính "priceKey" thay vì                        bookingReservation[priceKey]
                                                                                giá trị "roomPrice" của biến priceKey

2. Xóa voucher              bookingReservation.discountCode = undefined         Chỉ thay giá trị thành undefined, key                               delete bookingReservation.
                                                                                discountCode vẫn còn trong object                                   discountCode

3. Duyệt object             bookingReservation.key                              JavaScript tìm thuộc tính có tên "key"                              bookingReservation[key]


2. Test Cases
Trường hợp kiểm thử	                    Dữ liệu đầu vào	                                Kết quả sai thực tế	                                    Kết quả đúng mong đợi
Nhận phòng trước 12 giờ,                roomPrice = 1500000, checkInHour = 9,           Giá phòng là undefined, phụ thu và tổng tiền là NaN;    Giá phòng 1500000, phụ thu 450000, tổng 
voucher không hợp lệ                    isVoucherValid = false                          discountCode vẫn tồn tại với giá trị undefined;         tiền 1950000; discountCode bị xóa hoàn 
                                                                                        vòng lặp in các giá trị undefined                       toàn

Nhận phòng từ 12 giờ trở đi,            roomPrice = 1500000, checkInHour = 14,          Giá phòng là undefined, tổng tiền là NaN; discountCode  Giá phòng 1500000, phụ thu 0, tổng tiền 
voucher không hợp lệ                    isVoucherValid = false                          vẫn tồn tại; vòng lặp hiển thị sai giá trị              1500000; discountCode bị xóa hoàn toàn