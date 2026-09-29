# Tụ điện (C)

## 1. Phân loại & Ký hiệu sơ đồ

- **Tụ phân cực:**
  - Có phân biệt chiều âm/dương (Chân dài là cực dương `+`, chân ngắn là cực âm `-`).
  - **Ký hiệu:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='60' viewBox='0 0 100 60'%3E%3Cpath d='M 10 30 L 45 30 M 55 30 L 90 30 M 45 15 L 45 45' fill='none' stroke='%23333' stroke-width='3'/%3E%3Cpath d='M 60 15 Q 50 30 60 45' fill='none' stroke='%23333' stroke-width='3'/%3E%3Ctext x='25' y='20' font-family='sans-serif' font-size='14' font-weight='bold' fill='%23333'%3E+%3C/text%3E%3C/svg%3E" width="80"/>
- **Tụ không phân cực:**
  - Hai chân bằng nhau, không phân biệt cực `+` và `-` (cắm chiều nào cũng được).
  - **Ký hiệu:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='60' viewBox='0 0 100 60'%3E%3Cpath d='M 10 30 L 45 30 M 55 30 L 90 30 M 45 15 L 45 45 M 55 15 L 55 45' fill='none' stroke='%23333' stroke-width='3'/%3E%3C/svg%3E" width="80"/>

## 2. Thông số & Đặc tính cơ bản

- **Số Volt (V):** Mức điện áp chịu đựng tối đa của tụ. Nếu nạp vượt quá mức này, tụ sẽ bị đánh thủng (nổ, hỏng).
- **Điện dung (C):** Lượng điện năng mà tụ có thể tích trữ được. Đơn vị thường dùng trong mạch nhỏ là Microfarad ($\mu F$).
- **Đặc tính Tích/Xả:**
  - Có thể sạc và xả như pin. Tuy nhiên, năng lượng tích trữ của tụ ít hơn pin rất nhiều, nhưng tụ có khả năng xả cực nhanh.
  - Khi dùng đồng hồ đo điện áp hai đầu tụ hiển thị $0V$, đó là trạng thái tụ đã xả hết điện (xả tụ).
  - Khả năng nạp thụ động: Tụ $63V$ cắm vào nguồn pin $1.5V$ thì tụ chỉ tích được mức điện áp là $1.5V$.
  - Mức xả tỉ lệ nghịch với điện trở ($R$): Điện trở cản càng nhỏ thì tụ xả càng nhanh.

## 3. Công thức Tích/Xả tụ ($RC$)

> _Lưu ý: Hằng số Euler $e \approx 2.718$. Điện dung tính bằng Farad (VD: $10\mu F = 10 \times 10^{-6} F$)._

### Quá trình nạp tụ

- **Sơ đồ nạp:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='120' viewBox='0 0 200 120'%3E%3Cpath d='M 40 90 L 40 30 L 70 30 M 100 30 L 150 30 L 150 50 M 150 70 L 150 90 L 40 90' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Ccircle cx='40' cy='60' r='10' fill='none' stroke='%23333' stroke-width='2'/%3E%3Ctext x='40' y='65' font-family='sans-serif' font-size='13' text-anchor='middle' font-weight='bold'%3EVin%3C/text%3E%3Cpath d='M 70 30 L 73 22 L 79 38 L 85 22 L 91 38 L 97 22 L 100 30' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Cpath d='M 140 50 L 160 50 M 140 70 L 160 70' fill='none' stroke='%23333' stroke-width='3'/%3E%3Ctext x='82' y='18' font-family='sans-serif' font-size='13' font-weight='bold'%3ER%3C/text%3E%3Ctext x='165' y='65' font-family='sans-serif' font-size='13' font-weight='bold'%3EC%3C/text%3E%3C/svg%3E" width="160"/>
- **Công thức tính điện áp tại thời điểm $t$:** $V_a = V_0 \times \left(1 - e^{-\frac{t}{R \cdot C}}\right)$
- **Ví dụ tính toán:** Nguồn $V_0 = 12V$, Điện trở $R = 100k\Omega$ ($100,000\Omega$), Tụ $C = 10\mu F$ ($10 \times 10^{-6} F$)
  - Tại $t = 0s \Rightarrow V_a = 0V$
  - Tại $t = 1s \Rightarrow V_a = 12 \times \left(1 - 2.718^{-\frac{1}{1}}\right) = 7.5854V$
  - Tại $t = 5s \Rightarrow V_a = 11.9191V$
  - Tại $t = 10s \Rightarrow V_a = 11.9995V$
  - Tại $t = 20s \Rightarrow V_a \approx 12.0000V$ (Đầy tụ)

### Quá trình xả tụ

- **Sơ đồ xả:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='160' height='120' viewBox='0 0 160 120'%3E%3Cpath d='M 50 50 L 50 30 L 110 30 L 110 45' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Cpath d='M 50 70 L 50 90 L 110 90 L 110 75' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Cpath d='M 40 50 L 60 50 M 40 70 L 60 70' fill='none' stroke='%23333' stroke-width='3'/%3E%3Cpath d='M 110 45 L 102 48 L 118 54 L 102 60 L 118 66 L 102 72 L 110 75' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Ctext x='25' y='65' font-family='sans-serif' font-size='13' font-weight='bold'%3EC%3C/text%3E%3Ctext x='125' y='65' font-family='sans-serif' font-size='13' font-weight='bold'%3ER%3C/text%3E%3C/svg%3E" width="130"/>
- **Công thức tính điện áp còn lại:** $V_a = V_0 \times e^{-\frac{t}{R \cdot C}}$
- **Ví dụ tính toán:** Tụ đang đầy mức $V_0 = 12V$, xả qua trở $R = 100k\Omega$. Sau $t = 2s$, điện áp còn:
  - $V_a = 12 \times 2.718^{-\frac{2}{100,000 \times 10^{-5}}} = 12 \times 2.718^{-2} = 1.62V$

## 4. Ứng dụng thực tế (Mạch tạo trễ / Timer)

- Dùng cho mạch rót rượu tự động (nhấn nút rót 3 giây rồi ngắt mạch).
- **Mạch đèn lóe sáng/duy trì sau khi tắt công tắc:**
  - Nhờ năng lượng tích trữ trong tụ điện, khi ngắt công tắc nguồn, tụ bắt đầu xả điện qua bóng đèn giúp đèn duy trì ánh sáng thêm 3 giây trước khi tắt hẳn.
  - **Cấu tạo mạch:**
  - Công tắc nối nguồn $12V$.
  - Tụ điện ghép song song với trở xả $20k\Omega$ xuống Mass (GND).
  - Tín hiệu xả qua trở hạn dòng $10k\Omega$ kích vào chân **B** Transistor NPN.
  - Bóng đèn $12V$ nối vào cực **C**, cực **E** nối Mass (GND).
- **Sơ đồ:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='260' height='180' viewBox='0 0 260 180'%3E%3Cpath d='M 30 20 L 30 35 M 30 55 L 30 65 L 120 65 M 30 65 L 30 85 M 20 85 L 40 85 M 20 100 L 40 100 M 30 100 L 30 150 L 80 150 M 80 65 L 80 85 L 72 89 L 88 95 L 72 101 L 88 107 L 80 111 L 80 150 M 120 65 L 130 65 L 134 57 L 142 73 L 150 57 L 158 73 L 166 57 L 174 73 L 178 65 L 190 65 L 190 85 M 190 70 L 190 100 M 190 75 L 210 55 M 210 55 L 210 35 L 210 20 M 190 95 L 210 115 M 202 107 L 210 115 L 200 117 fill=%23333 M 210 115 L 210 150' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Ccircle cx='210' cy='35' r='12' fill='none' stroke='%23333' stroke-width='2'/%3E%3Cline x1='202' y1='27' x2='218' y2='43' stroke='%23333' stroke-width='2'/%3E%3Cline x1='218' y1='27' x2='202' y2='43' stroke='%23333' stroke-width='2'/%3E%3Cpath d='M 25 35 L 35 50' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Ccircle cx='30' cy='35' r='2' fill='%23333'/%3E%3Ccircle cx='30' cy='55' r='2' fill='%23333'/%3E%3Cpath d='M 20 150 L 40 150 M 23 154 L 37 154 M 27 158 L 33 158 M 200 150 L 220 150 M 203 154 L 217 154 M 207 158 L 213 158' fill='none' stroke='%23333' stroke-width='2'/%3E%3Ctext x='25' y='12' font-family='sans-serif' font-size='11' font-weight='bold'%3E12V%3C/text%3E%3Ctext x='205' y='12' font-family='sans-serif' font-size='11' font-weight='bold'%3E12V%3C/text%3E%3Ctext x='5' y='97' font-family='sans-serif' font-size='12' font-weight='bold'%3EC%3C/text%3E%3Ctext x='88' y='100' font-family='sans-serif' font-size='12' font-weight='bold'%3E20k%3C/text%3E%3Ctext x='145' y='52' font-family='sans-serif' font-size='12' font-weight='bold'%3E10k%3C/text%3E%3Ctext x='180' y='90' font-family='sans-serif' font-size='11' font-weight='bold'%3Eb%3C/text%3E%3Ctext x='216' y='60' font-family='sans-serif' font-size='11' font-weight='bold'%3EC%3C/text%3E%3Ctext x='216' y='110' font-family='sans-serif' font-size='11' font-weight='bold'%3EE%3C/text%3E%3C/svg%3E" width="220"/>
