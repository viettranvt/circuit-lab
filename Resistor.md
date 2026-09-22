# Điện trở (R)

## 1. Khái niệm & Tác dụng

- Hạn chế cường độ dòng điện ($I$) trong mạch
- Điện trở tỉ lệ nghịch với cường độ dòng điện: $R \uparrow \Rightarrow I \downarrow$
- **Ký hiệu sơ đồ:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='40' viewBox='0 0 120 40'%3E%3Cpath d='M 0 20 L 20 20 L 25 5 L 35 35 L 45 5 L 55 35 L 65 5 L 75 35 L 85 5 L 95 35 L 100 20 L 120 20' fill='none' stroke='%23333' stroke-width='3'/%3E%3C/svg%3E" width="100"/>

## 2. Công thức cơ bản (Định luật Ohm)

- Công thức: $I = \frac{U}{R}$
- **Ví dụ:** $U = 9V, R = 3\Omega \Rightarrow I = \frac{9}{3} = 3A$

## 3. Các cách ghép điện trở (Tính $R_{td}$)

> _Mục đích: Thay thế nhiều điện trở bằng 1 điện trở duy nhất_

### Mắc nối tiếp (Tăng điện trở tổng)

- **Công thức:** $R_{td} = R_1 + R_2 + ... + R_n$
- **Ví dụ:** Ghép 2 điện trở $30\Omega \Rightarrow R_{td} = 30 + 30 = 60\Omega$
- **Sơ đồ mạch:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='50' viewBox='0 0 200 50'%3E%3Cpath d='M 10 30 L 30 30 L 34 18 L 42 42 L 50 18 L 58 42 L 66 18 L 74 42 L 78 30 L 110 30 L 114 18 L 122 42 L 130 18 L 138 42 L 146 18 L 154 42 L 158 30 L 190 30' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Ccircle cx='10' cy='30' r='3' fill='%23333'/%3E%3Ccircle cx='190' cy='30' r='3' fill='%23333'/%3E%3Ctext x='56' y='12' font-family='sans-serif' font-size='13' font-weight='bold' fill='%23333' text-anchor='middle'%3ER1%3C/text%3E%3Ctext x='136' y='12' font-family='sans-serif' font-size='13' font-weight='bold' fill='%23333' text-anchor='middle'%3ER2%3C/text%3E%3C/svg%3E" width="160"/>

### Mắc song song (Giảm điện trở tổng)

- **Công thức:** $\frac{1}{R_{td}} = \frac{1}{R_1} + \frac{1}{R_2} + ... + \frac{1}{R_n} \Rightarrow R_{td} = \frac{1}{\frac{1}{R_1} + \frac{1}{R_2} + ...}$
- **Ví dụ:** Ghép 2 điện trở $30\Omega \Rightarrow R_{td} = \frac{1}{\frac{1}{30} + \frac{1}{30}} = 15\Omega$
- **Sơ đồ mạch:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='160' height='110' viewBox='0 0 160 110'%3E%3Cpath d='M 10 55 L 30 55 M 30 25 L 30 85 M 130 25 L 130 85 M 130 55 L 150 55 M 30 25 L 50 25 L 54 13 L 62 37 L 70 13 L 78 37 L 86 13 L 94 37 L 98 25 L 130 25 M 30 85 L 50 85 L 54 73 L 62 97 L 70 73 L 78 97 L 86 73 L 94 97 L 98 85 L 130 85' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Ccircle cx='10' cy='55' r='3' fill='%23333'/%3E%3Ccircle cx='150' cy='55' r='3' fill='%23333'/%3E%3Ctext x='74' y='11' font-family='sans-serif' font-size='13' font-weight='bold' fill='%23333' text-anchor='middle'%3ER1%3C/text%3E%3Ctext x='74' y='71' font-family='sans-serif' font-size='13' font-weight='bold' fill='%23333' text-anchor='middle'%3ER2%3C/text%3E%3C/svg%3E" width="140"/>

## 4. Ứng dụng thực tế

### Mạch chia áp (Voltage Divider)

- **Mục đích:** Hạ điện áp nguồn $V_{in}$ xuống mức $V_{out}$ mong muốn (dùng 2 điện trở nối tiếp)
- **Công thức:** $V_{out} = \left(\frac{R_2}{R_1 + R_2}\right) \times V_{in}$
- **Ví dụ:** $V_{in} = 12V$, muốn $V_{out} = 6V$
  - $6 = \left(\frac{R_2}{R_1 + R_2}\right) \times 12$
  - $\Rightarrow R_1 = R_2$ (Chọn $R_1 = R_2 = 5k\Omega$)
- **Sơ đồ mạch:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='160' height='160' viewBox='0 0 160 160'%3E%3Cpath d='M 40 20 L 40 36 L 28 41 L 52 47 L 28 53 L 52 59 L 40 64 L 40 80 L 40 86 L 28 91 L 52 97 L 28 103 L 52 109 L 40 114 L 40 130 M 40 80 L 110 80 M 25 130 L 55 130 M 30 136 L 50 136 M 35 142 L 45 142' fill='none' stroke='%23333' stroke-width='2.5'/%3E%3Ccircle cx='40' cy='20' r='3' fill='%23333'/%3E%3Ccircle cx='40' cy='80' r='3' fill='%23333'/%3E%3Ccircle cx='110' cy='80' r='3' fill='%23333'/%3E%3Ctext x='55' y='24' font-family='sans-serif' font-size='13' font-weight='bold' fill='%23333'%3EVin%3C/text%3E%3Ctext x='118' y='84' font-family='sans-serif' font-size='13' font-weight='bold' fill='%23333'%3EVout%3C/text%3E%3Ctext x='18' y='53' font-family='sans-serif' font-size='13' font-weight='bold' fill='%23333'%3ER1%3C/text%3E%3Ctext x='18' y='103' font-family='sans-serif' font-size='13' font-weight='bold' fill='%23333'%3ER2%3C/text%3E%3C/svg%3E" width="130"/>

### Biến trở (Variable Resistor)

- Thay đổi giá trị điện trở linh hoạt/linh động (thay vì cố định)
- **Đặc điểm:** Tổng điện trở không đổi (Ví dụ: Biến trở $10k\Omega \Rightarrow R_1 + R_2 = 10k\Omega$)
- **Ký hiệu sơ đồ:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='60' viewBox='0 0 120 60'%3E%3Cpath d='M 0 35 L 20 35 L 25 20 L 35 50 L 45 20 L 55 50 L 65 20 L 75 50 L 85 20 L 95 50 L 100 35 L 120 35' fill='none' stroke='%23333' stroke-width='3'/%3E%3Cpath d='M 25 55 L 88 12' fill='none' stroke='%23333' stroke-width='3'/%3E%3Cpolygon points='88,12 75,16 82,25' fill='%23333'/%3E%3C/svg%3E" width="100"/>

### Điện trở hạn dòng cho LED

- **Đặc tính Đèn LED:**
  - Dòng điện tối đa ($I_{max}$): $\le 20mA = 0.02A$
  - Sụt áp cố định trên LED ($V_{LED}$): $\approx 2V$
- **Ký hiệu sơ đồ LED:** <br/><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='60' viewBox='0 0 120 60'%3E%3Cpath d='M 0 30 L 40 30 M 70 30 L 110 30 M 70 15 L 70 45' fill='none' stroke='%23333' stroke-width='3'/%3E%3Cpolygon points='40,15 40,45 70,30' fill='%23333'/%3E%3Cpath d='M 50 12 L 65 2 M 60 18 L 75 8' fill='none' stroke='%23333' stroke-width='2'/%3E%3Cpolygon points='65,2 58,4 62,8' fill='%23333'/%3E%3Cpolygon points='75,8 68,10 72,14' fill='%23333'/%3E%3C/svg%3E" width="100"/>
- **Cách tính điện trở ($R_{LED}$):**
  - Điện áp còn lại trên điện trở: $V_R = V_{in} - V_{LED}$
  - Công thức: $R = \frac{V_{in} - V_{LED}}{I_{LED}}$
- **Ví dụ:** Nguồn $V_{in} = 12V$, LED $2V - 20mA$
  - $V_R = 12V - 2V = 10V$
  - $R = \frac{10V}{20mA} = \frac{10}{0.02} = 500\Omega$
