# **BÁO CÁO: SO SÁNH KIẾN TRÚC CISC VÀ RISC**

---

## **1. Giới thiệu khái niệm cơ bản**

### **1.1. Kiến trúc CISC (Complex Instruction Set Computer)**
  
CISC là kiểu kiến trúc vi xử lý trong đó **một lệnh có thể thực hiện được nhiều thao tác phức tạp**, chẳng hạn như truy cập bộ nhớ, tính toán, và lưu kết quả chỉ trong một lệnh duy nhất.

Mục tiêu của CISC là **giảm số lượng dòng lệnh trong chương trình** bằng cách làm cho mỗi lệnh trở nên mạnh mẽ hơn.  
Điều này giúp lập trình viên (hoặc trình biên dịch) viết chương trình dễ hơn vì có thể mô tả các thao tác ở mức cao với ít lệnh hơn.

Ví dụ tiêu biểu cho CISC là các bộ vi xử lý **Intel x86, AMD64, VIA Nano**, v.v.

---

### **1.2. Kiến trúc RISC (Reduced Instruction Set Computer)**
  
Trong kiến trúc RISC, **mỗi lệnh được thiết kế đơn giản và thực thi trong một chu kỳ xung nhịp (clock cycle)**.  
Thay vì cung cấp nhiều lệnh phức tạp, RISC chỉ cung cấp **một tập nhỏ các lệnh cơ bản nhưng tối ưu**, cho phép phần cứng xử lý nhanh hơn.

Mục tiêu của RISC là **tăng tốc độ xử lý** thông qua việc tối giản tập lệnh và tối ưu hóa đường ống xử lý (pipeline).  
Các ví dụ tiêu biểu là **ARM, MIPS, SPARC, RISC-V**, v.v.

---

## **2. Ưu điểm và nhược điểm của từng kiến trúc**

| Kiến trúc | Ưu điểm | Nhược điểm |
|-----------|---------|------------|
| **CISC** | - Ít dòng lệnh hơn trong chương trình. <br> - Dễ dàng hơn cho lập trình viên ở mức hợp ngữ. <br> - Tương thích ngược mạnh mẽ (đặc biệt trong họ x86). | - Thiết kế phần cứng phức tạp. <br> - Khó tối ưu pipeline. <br> - Tốc độ thực thi lệnh thấp hơn do độ phức tạp. |
| **RISC** | - Lệnh thực thi nhanh (mỗi lệnh 1 chu kỳ). <br> - Dễ tối ưu pipeline, hỗ trợ song song hóa cao. <br> - Phần cứng đơn giản, tiêu thụ ít năng lượng. | - Chương trình dài hơn do cần nhiều lệnh để thực hiện cùng tác vụ. <br> - Cần bộ nhớ chương trình lớn hơn. <br> - Cần trình biên dịch thông minh để tối ưu mã máy. |

---

## **3. So sánh CISC và RISC theo các tiêu chí**

### **3.1. Cấu trúc tập lệnh**

- **CISC:**  
  Tập lệnh phức tạp, số lượng lệnh nhiều.  
  Một lệnh có thể thực hiện nhiều thao tác (tải, tính toán, lưu).  
  Kích thước lệnh không cố định.

- **RISC:**  
  Tập lệnh đơn giản, chỉ bao gồm các lệnh cơ bản như *load*, *store*, *add*, *sub*, *branch*.  
  Kích thước lệnh thường cố định (ví dụ: 32 bit).  
  Thiết kế tập trung vào hiệu năng hơn là sự đa dạng.

---

### **3.2. Tốc độ xử lý**

- **CISC:**  
  Mỗi lệnh có thể mất nhiều chu kỳ xung để thực thi.  
  Việc giải mã lệnh phức tạp làm giảm tốc độ tổng thể.

- **RISC:**  
  Mỗi lệnh thường chỉ cần 1 chu kỳ.  
  Hỗ trợ *pipelining* hiệu quả, giúp tốc độ xử lý cao hơn nhiều trong các ứng dụng thời gian thực.

---

### **3.3. Kích thước chương trình**

- **CISC:**  
  Do mỗi lệnh có khả năng thực hiện nhiều thao tác, nên tổng số lệnh trong chương trình **ít hơn**, dẫn đến **kích thước mã nhỏ hơn**.

- **RISC:**  
  Cần nhiều lệnh hơn để đạt cùng kết quả, nên **kích thước chương trình lớn hơn**.
---

### **3.4. Độ phức tạp phần cứng**

- **CISC:**  
  Bộ giải mã lệnh (instruction decoder) và vi điều khiển (microcode) phức tạp.  
  Cần nhiều bóng bán dẫn để thực hiện các lệnh đa dạng.

- **RISC:**  
  Phần cứng đơn giản hơn, ít transistor hơn.  
  Dễ mở rộng pipeline và tối ưu hiệu năng.

---

### **3.5. Ứng dụng thực tế**

| Kiến trúc | Ví dụ bộ xử lý | Ứng dụng phổ biến |
|------------|----------------|--------------------|
| **CISC** | Intel x86, AMD64 | Máy tính để bàn, laptop, máy chủ |
| **RISC** | ARM, MIPS, RISC-V | Hệ thống nhúng, thiết bị di động, IoT |

Hiện nay, **ARM (RISC)** chiếm ưu thế trong các thiết bị di động nhờ **hiệu năng/điện năng cao**, trong khi **Intel x86 (CISC)** vẫn thống trị thị trường máy tính cá nhân và máy chủ.

---

## **4. Quan điểm cá nhân**

Trong bối cảnh **phát triển hệ thống nhúng hiện nay**, **kiến trúc RISC** là lựa chọn phù hợp hơn.  
Lý do:

1. **Tiết kiệm năng lượng:** Các thiết bị nhúng (như điện thoại, cảm biến, IoT, robot, STM32, ESP32, Raspberry Pi) yêu cầu hoạt động lâu dài với pin. RISC có mức tiêu thụ năng lượng thấp nhờ phần cứng đơn giản và ít transistor hơn.
2. **Tốc độ xử lý cao:** Thiết kế pipeline hiệu quả giúp RISC đạt hiệu năng cao trên mỗi chu kỳ xung nhịp.
3. **Chi phí thấp:** Việc thiết kế chip RISC đơn giản hơn, tiết kiệm chi phí sản xuất.
4. **Tính mở rộng:** Các kiến trúc như **ARM và RISC-V** cho phép tùy biến, mở rộng phù hợp với từng ứng dụng cụ thể — rất quan trọng trong lĩnh vực nhúng.

Ngược lại, CISC (như Intel x86) vẫn có vị thế mạnh trong PC nhờ khả năng tương thích ngược và hiệu suất cao khi chạy các phần mềm truyền thống.  
Tuy nhiên, với xu hướng **thiết bị nhỏ gọn, tiết kiệm năng lượng, và trí tuệ nhân tạo nhúng (Edge AI)**, RISC đang ngày càng chứng tỏ ưu thế vượt trội.

---