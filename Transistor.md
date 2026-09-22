# Transistor NPN (Chế độ công tắc)

## 1. Khái niệm & Cấu tạo

- Công tắc khóa điện tử: Đóng ngắt bằng tín hiệu điện (thay cho công tắc cơ)
- **3 Chân:**
  - **C** (Collector): Cực thu
  - **B** (Base): Cực nền
  - **E** (Emitter): Cực phát
  - _Lưu ý:_ C, B, E chỉ là tên gọi quy ước
- **Nhận biết NPN:** Có ký hiệu dòng điện chạy từ cực **B** về cực **E**
- **Ký hiệu sơ đồ:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120' viewBox='0 0 120 120'%3E%3Ccircle cx='60' cy='60' r='40' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Cline x1='10' y1='60' x2='40' y2='60' stroke='%23333' stroke-width='2.5'/%3E%3Cline x1='40' y1='35' x2='40' y2='85' stroke='%23333' stroke-width='3.5'/%3E%3Cline x1='40' y1='45' x2='75' y2='10' stroke='%23333' stroke-width='2.5'/%3E%3Cline x1='75' y1='10' x2='75' y2='0' stroke='%23333' stroke-width='2.5'/%3E%3Cline x1='40' y1='75' x2='75' y2='110' stroke='%23333' stroke-width='2.5'/%3E%3Cline x1='75' y1='110' x2='75' y2='120' stroke='%23333' stroke-width='2.5'/%3E%3Cpolygon points='75,110 62,107 70,95' fill='%23333'/%3E%3Ctext x='5' y='55' font-family='sans-serif' font-size='14' font-weight='bold' fill='%23333'%3EB%3C/text%3E%3Ctext x='85' y='15' font-family='sans-serif' font-size='14' font-weight='bold' fill='%23333'%3EC%3C/text%3E%3Ctext x='85' y='115' font-family='sans-serif' font-size='14' font-weight='bold' fill='%23333'%3EE%3C/text%3E%3C/svg%3E" width="100"/>

## 2. Nguyên lý hoạt động & Giải thích hiện tượng

### Điều kiện thông mạch & Sụt áp $U_{BE}$

- Muốn hoạt động phải tạo 1 dòng điện đi từ **B** về **E** $\Rightarrow$ Transistor sẽ thông mạch.
- **Sụt áp chân BE:** Điện áp $V_{BE}$ thường sẽ là **$0.7V$**.
  - _Giải thích:_ Cơ chế của Transistor giống hệt đèn LED (đèn LED khi dẫn điện sẽ bị sụt áp cụ thể là $2V$).

### Lý do phải gắn điện trở $R_B$

- Để tạo dòng điện kích hoạt, người ta gắn $1$ điện trở $R_B$ nối với nguồn điều khiển (VD: $5V$).
- _Giải thích bản chất:_ Trong Transistor luôn có $1$ con trở nhỏ nối từ **C** qua **E** $\Rightarrow$ Luôn tồn tại điện áp $U_{CE}$.
- Do đó cần tính toán gắn $R_B$ để sao cho $U_{CE}$ là nhỏ nhất (đạt trạng thái bão hòa) $\Rightarrow$ Giúp Transistor thông hoàn toàn, không bị rò điện hay nóng.

### Tính chất khuếch đại ($\beta$)

- Transistor là linh kiện điện tử khuếch đại.
- Dòng $I_B$ dù cực nhỏ khi qua Transistor có thể khuếch đại lên $100$ lần.
  - _Ví dụ:_ Dòng tải đang là $100mA$ thì lúc này $I_B$ chỉ cần $1mA$ là có thể điều khiển.
- Hệ số khuếch đại này được gọi là **Beta ($\beta$)**, tra cứu trên Datasheet của linh kiện.

## 3. Công thức tính toán chi tiết

### Các công thức thành phần

- **Dòng $I_B$:** $I_B = \frac{U}{R_B} = \frac{U_{dieukien} - 0.7}{R_B}$
- **Dòng tổng:** $I_{tong} = \beta \times I_B$
- **Công suất đèn:** $P_{den} = U \times I_{tong} \Rightarrow I_{tong} = \frac{P_{den}}{U}$

### Chuỗi biến đổi tìm công thức $R_B$

- Bắt đầu từ: $\beta \times I_B = \frac{P_{den}}{U}$
- Thế $I_B$ vào: $\beta \times \left(\frac{U_{dieukien} - 0.7}{R_B}\right) = \frac{P_{den}}{U}$
- Rút gọn: $\frac{\beta \times (U_{dieukien} - 0.7)}{R_B} = \frac{P_{den}}{U}$
- **Công thức suy ra $R_B$:** $R_B = \frac{U \times (U_{dieukien} - 0.7) \times \beta}{P_{den}}$

## 4. Ví dụ tính toán $R_B$ thực tế

- **Đề bài:** Bóng đèn $12VDC / 10W$, Điện điều khiển $5V$, $\beta = 100$. Tính điện trở $R_B$?
- **Phép tính:** $R_B = \frac{12 \times (5 - 0.7) \times 100}{10} = 516\Omega$
- **Chọn thực tế:** Do không có điện trở $516\Omega$ nên chọn loại tiêu chuẩn gần nhất là **$510\Omega$**.

## 5. Kinh nghiệm chọn $R_B$ & Lý do bảo vệ cảm biến

- **Mẹo chọn nhanh:** Do cách tính phức tạp phụ thuộc vào hệ số $\beta$ nên thực tế người ta thường chọn thẳng điện trở $R_B$ từ **$500\Omega \rightarrow 1000\Omega$**.
- **Giải thích lý do bảo vệ mạch:**
  - Sau nguồn $5V$ điều khiển có thể sẽ lắp $1$ con cảm biến hoặc thiết bị khác chỉ ăn dòng cực nhỏ (VD: $20mA$).
  - Nếu lắp $R_B$ quá nhỏ $\Rightarrow$ Cường độ dòng điện rút ra sẽ tăng cao $\Rightarrow$ Các cảm biến sẽ không chịu được và dễ bị hỏng/cháy.

## 6. Lưu ý: Dòng khuếch đại tối đa vs Dòng thực tế

- **Nguyên lý:** $I_{khuech\_dai}$ là mức khuếch đại tối đa, nó phụ thuộc vào công suất thực tế của thiết bị.

### Ví dụ phân tích so sánh

- **Giả định:** $U_{dieukien} = 5V$, $R_B = 100\Omega$, $U = 12V$, $P_{den} = 10W$, $\beta = 100$
- **Tính dòng khuếch đại tối đa:**
  - $I_{khuech\_dai} = \beta \times I_B = 100 \times \left(\frac{5 - 0.7}{100}\right) = 4.3A$
- **Tính dòng thực tế của bóng đèn:**
  - $I_{thuc\_te} = \frac{P_{den}}{U} = \frac{10}{12} = 0.83A$
- **Kết luận:** Lúc này cường độ dòng điện tối đa thực tế chạy qua mạch chỉ là **$0.83A$** (phụ thuộc vào công suất bóng đèn).
