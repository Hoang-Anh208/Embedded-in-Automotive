<details><summary><b>Giao thức SPI</b></summary>
<p>

<details><summary><b>Lý thuyết</b></summary>
<p>

SPI (Serial Peripheral Interface) là một giao thức truyền thông nối tiếp thường được sử dụng trong các hệ thống nhúng để trao đổi dữ liệu giữa một vi điều khiển (master) và các thiết bị ngoại vi (slave) như cảm biến, bộ nhớ flash, màn hình LCD, và nhiều loại thiết bị khác.

<br>

SPI là một chuẩn giao tiếp đồng bộ truyền dữ liệu ở chế độ **song công (Full-Duplex)**, nghĩa là tại một thời điểm có thể xảy ra đồng thời quá trình truyền và nhận. Là giao tiếp đồng bộ, bất kỳ quá trình nào cũng đều được đồng bộ với xung clock sinh ra bởi thiết bị Master.

<br>

Tốc độ truyền thông cao: SPI cho phép truyền dữ liệu với tốc độ rất nhanh, thường đạt được tốc độ Mbps hoặc thậm chí hàng chục Mbps. Điều này rất hữu ích khi cần truyền dữ liệu nhanh và đáng tin cậy trong các ứng dụng như truyền thông không dây, điều khiển từ xa và truyền dữ liệu đa phương tiện.

</p>
</details>

<details><summary><b>Số dây giao tiếp</b></summary>
<p>

![image](https://github.com/user-attachments/assets/e6f8191b-7417-4586-847d-82a1075d00db)

SPI sử dụng 4 đường giao tiếp nên đôi khi còn được gọi là chuẩn truyền thông "4 dây":

- **SCK (Serial Clock)**: thiết bị Master tạo tín hiệu xung clock và cung cấp cho Slave. Xung này có chức năng giữ nhịp cho giao tiếp SPI. Mỗi nhịp trên chân SCK này sẽ báo 1 bit dữ liệu đến hoặc đi

<br>

- **MISO (Master in Slave out)**: tín hiệu tạo bởi thiết bị Slave và nhận bởi thiết bị Master. Đường MISO phải được kết nối giữa thiết bị Master và Slave.

<br>

- **MOSI (Master out Slave in)**: tín hiệu tạo bởi thiết bị Master và nhận bởi thiết bị Slave. Đường MOSI phải được kết nối giữa thiết bị Master và Slave.

<br>

- **SS (Slave Select) hay CS (Chip Select)**: chọn thiết bị Slave cụ thể để giao tiếp. Để chọn Slave giao tiếp thiết bị Master chủ động kéo đường SS tương ứng xuống mức 0 (Low). Chân SS (CS) của vi điều khiển (Master) có thể được người dùng tạo bằng cách cấu hình 1 chân GPIO bất kỳ chế độ Output.

</p>
</details>

<details><summary><b>Cách thức hoạt động</b></summary>
<p>

SPI cho phép 1 Master có thể giao tiếp với nhiều Slave, nghĩa là 1 MCU có thể giao tiếp với nhiều MCU, ngoại vi khác. 

<br>

Các Slave chỉ có thể có 1 chân SS (CS) để nhận tín hiệu chọn này. Tuy nhiên, Master thì sẽ có nhiều hơn 1 chân SS (CS) để chọn từng thiết bị muốn giao tiếp. 

![image](https://github.com/user-attachments/assets/433718c0-f51f-46f5-8d86-c0919250f72e)

Khung truyền SPI:

![image](https://github.com/user-attachments/assets/44def36f-d075-43ba-8a27-30eda1965dfa)

- Mỗi chip Master hay Slave đều có một thanh ghi dữ liệu 8 bits. Quá trình truyền/nhận giữa Master và Slave xảy ra đồng thời theo chu kỳ clock ở chân SCK, một byte dữ liệu được truyền theo cả 2 hướng.
- Quá trình trao đổi dữ liệu bắt đầu khi Master tạo 1 xung clock từ bộ tạo xung nhịp và kéo đường SS của Slave mà nó truyền dữ liệu xuống mức LOW (0).
- Mỗi xung clock, Master sẽ gửi đi 1 bit từ thanh ghi dịch (Shift Register) của nó đến thanh ghi dịch của Slave thông qua đường MISO. Như vậy, sau 8 chu kỳ clock thì hoàn tất việc truyền và nhận 1 byte dữ liệu.


</p>
</details>

<details><summary><b>Chế độ hoạt động</b></summary>
<p>

SPI có 4 chế độ hoạt động phụ thuộc vào cực của xung giữ (**Clock Polarity - CPOL**) và pha (**Phase - CPHA**).

<br>

**CPOL** dùng để chỉ trạng thái của chân SCK ở trạng thái nghỉ. Chân SCK giữ ở **mức cao** khi ``` CPOL = 1 ``` hoặc **mức thấp** khi ``` CPOL = 0```.

<br>

CPHA dùng để chỉ các mà dữ liệu được lấy mẫu theo xung. Dữ liệu sẽ được lấy ở **cạnh lên** của SCK khi ``` CPHA = 0 ``` hoặc **cạnh xuống** khi ``` CPHA = 1 ```.

![image](https://github.com/user-attachments/assets/36819112-5e39-4e84-8a11-ee04affe477a)

![image](https://github.com/user-attachments/assets/f2be3fa8-c80d-40de-b737-c7ffd12d07ab)


- **Mode 0 (mặc định)**: xung nhịp của đồng hồ ở mức thấp (CPOL = 0) và dữ liệu được lấy mẫu khi chuyển từ thấp sang cao (cạnh lên) (CPHA = 0).
- **Mode 1**: xung nhịp của đồng hồ ở mức thấp (CPOL = 0) và dữ liệu được lấy mẫu khi chuyển từ cao sang thấp (cạnh xuống) (CPHA = 1).
- **Mode 2**: xung nhịp của đồng hồ ở mức cao (CPOL = 1) và dữ liệu được lấy mẫu khi chuyển từ cao sang thấp (cạnh lên) (CPHA = 0).
- **Mode 3**: xung nhịp của đồng hồ ở mức cao (CPOL = 1) và dữ liệu được lấy mẫu khi chuyển từ thấp sang cao (cạnh xuông) (CPHA = 1).

<br>

</p>
</details>

</p>
</details>
