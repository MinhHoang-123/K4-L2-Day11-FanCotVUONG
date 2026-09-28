# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ (mô tả vị trí trong ảnh): Các vạch sơn ngắn, xiên nằm ở hàng đỗ xe phía dưới (tiền cảnh) và hàng giữa ảnh. Chúng đóng vai trò phân chia ranh giới giữa các ô đỗ với nhau.
- Một vạch/dấu sơn hoặc biên **không** vẽ, và vì sao: Vạch sơn trắng liền kéo dài ở sát mép dưới cùng của ảnh. Đây là vạch giới hạn mép đường/lối đi xe chạy, không phải là vạch chia các ô đỗ riêng biệt nên không phải là `parking_line`.
- Polygon `free_space` dừng ở đâu; có phần bị che nào không: Polygon bao quanh phần mặt đường nhựa trống ở lối đi chính giữa hai hàng đỗ xe. Nó dừng lại sát mép các ô đỗ (không cắt qua vạch ô đỗ) và kéo dài đến khoảng trống trước mặt chiếc xe màu đỏ ở xa. Vùng này không bị che khuất.
- Ca chưa chắc cần hỏi người soát (nếu không có, ghi “không có”): Không có.
