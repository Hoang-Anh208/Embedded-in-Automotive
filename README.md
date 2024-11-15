<details><summary><b>Bộ nhớ Flash & Bootloader/b></summary>
<p>

<details><summary><b>Các loại bộ nhớ</b></summary>
<p>

<details><summary><b>📚 RAM</b></summary>
<p>

RAM (Random Access Memory)** **là bộ nhớ **tạm thời** dùng để lưu dữ liệu trong quá trình chương trình chạy. Khi tắt nguồn, dữ liệu trong RAM sẽ mất.

**Ví dụ**: Khi vi điều khiển cần lưu các giá trị đang tính toán hoặc các biến dùng tạm, nó sẽ dùng RAM. Khi bạn tắt thiết bị, dữ liệu này sẽ bị xóa.

</p>
</details>

<details><summary><b>📚 Flash</b></summary>
<p>

**Flash** là bộ nhớ dùng để **lưu trữ chương trình** mà vi điều khiển sẽ chạy. Nó giống như ổ cứng của máy tính – dữ liệu vẫn còn đó ngay cả khi bạn tắt thiết bị. 

**Ví dụ**: Nếu bạn nạp chương trình vào vi điều khiển, chương trình sẽ nằm trong Flash để khi bật nguồn lại, nó có thể chạy tiếp.

</p>
</details>

<details><summary><b>📚 EEPROM</b></summary>
<p>

EEPROM (Electrically Erasable Programmable Read-Only Memory) là bộ nhớ có thể **lưu dữ liệu cần giữ lại** sau khi tắt thiết bị, nhưng dễ xóa và ghi lại. Nó rất thích hợp để lưu các cài đặt cần giữ lâu dài, nhưng không cần thay đổi thường xuyên.

**Ví dụ**: Nếu bạn có một cài đặt cần lưu (như độ sáng của màn hình), bạn có thể lưu nó vào EEPROM để khi bật lại, thiết bị nhớ được cài đặt của bạn.

</p>
</details>

<details><summary><b>📚 So sánh</b></summary>
<p>

## Giống nhau

- Flash và EEPROM đều là bộ nhớ không khả biến, giữ lại dữ liệu khi mất nguồn.
- Cả ba loại đều có vai trò quan trọng trong vi điều khiển, hỗ trợ các tác vụ khác nhau từ lưu chương trình, xử lý dữ liệu tạm thời đến lưu trữ các cài đặt hệ thống.

## Khác nhau

|                | **Flash**                                                                                      | **RAM**                                                                                | **EEPROM**                                                                                          |
|----------------------------|------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| **Khả biến (Volatile)**    | Không khả biến – dữ liệu vẫn còn khi mất nguồn                                                  | Khả biến – dữ liệu sẽ mất khi mất nguồn                                                 | Không khả biến – dữ liệu vẫn còn khi mất nguồn                                                      |
| **Chức năng chính**        | Lưu trữ chương trình (firmware)                                                                | Lưu trữ dữ liệu tạm thời, biến cục bộ trong quá trình chương trình chạy                 | Lưu trữ dữ liệu cần giữ lại khi tắt nguồn như cài đặt hoặc cấu hình                                 |
| **Tốc độ truy cập**        | Nhanh nhưng chậm hơn RAM                                                                       | Nhanh nhất                                                                              | Chậm hơn cả Flash và RAM                                                                            |
| **Khả năng ghi/xóa**       | Có giới hạn số lần ghi/xóa (thường vài ngàn đến vài chục ngàn lần)                             | Không có giới hạn, vì không ghi nhớ lâu dài                                             | Có giới hạn số lần ghi/xóa cao hơn Flash (thường từ 100,000 đến 1 triệu lần)                        |
| **Kích thước bộ nhớ**      | Thường lớn nhất trong vi điều khiển để chứa toàn bộ chương trình                               | Nhỏ hơn Flash, dùng để lưu trữ dữ liệu đang xử lý                                      | Thường rất nhỏ, chỉ đủ lưu một số cấu hình cần thiết                                                 |
| **Khả năng lưu trữ**       | Lưu được dữ liệu ngay cả khi tắt nguồn                                                         | Dữ liệu sẽ mất khi tắt nguồn                                                            | Lưu được dữ liệu ngay cả khi tắt nguồn                                                              |
| **Ứng dụng điển hình**     | Lưu trữ firmware (chương trình điều khiển)                                                     | Lưu trữ các biến tạm thời và dữ liệu trong quá trình thực thi                           | Lưu trữ các cài đặt cấu hình, dữ liệu cần giữ lại khi mất nguồn (ví dụ: cấu hình hệ thống, hiệu chuẩn) |

</p>
</details>

</p>
</details>

<details><summary><b></b></summary>
<p>

</p>
</details>

<details><summary><b></b></summary>
<p>

</p>
</details>

</p>
</details>

<br>

<details><summary><b>Giao thức UART</b></summary>
<p>

<details><summary><b>Khái niệm</b></summary>
<p>

UART (Universal Asynchronous Receiver-Transmitter – Bộ truyền nhận dữ liệu không đồng bộ) là một giao thức truyền thông phần cứng dùng giao tiếp nối tiếp không đồng bộ, bao gồm hai đường truyền dữ liệu độc lập là TX (truyền) và RX (nhận). Dữ liệu được truyền và nhận qua các đường truyền này dưới dạng các khung dữ liệu (data frame) có cấu trúc chuẩn, với một bit bắt đầu (start bit), một số bit dữ liệu (data bits), một bit kiểm tra chẵn lẻ (parity bit) và một hoặc nhiều bit dừng (stop bit).

![image](https://github.com/user-attachments/assets/8bb2fc6f-d865-49ce-93af-cfc82c58ab02)

</p>
</details>

<details><summary><b>Tốc độ truyền UART (Baud rate)</b></summary>
<p>

Thông thường, tốc độ truyền của UART được đặt ở một số chuẩn, chẳng hạn như 9600, 19200, 38400, 57600, 115200 baud và các tốc độ khác. Tốc độ truyền này định nghĩa số lượng bit được truyền qua mỗi giây. Các tốc độ truyền khác nhau thường được sử dụng tùy thuộc vào ứng dụng và hệ thống sử dụng.

</p>
</details>

<details><summary><b>Các chế độ truyền dữ liệu</b></summary>
<p>

UART truyền dữ liệu nối tiếp, theo 1 trong 3 chế độ:

- **Simplex**: Chỉ tiến hành giao tiếp một chiều
- **Half duplex**: Dữ liệu sẽ đi theo một hướng tại 1 thời điểm
- **Full duplex**: Thực hiện giao tiếp đồng thời đến và đi từ mỗi master và slave.

</p>
</details>

<details><summary><b>Cách thức hoạt động</b></summary>
<p>

Chân Tx (truyền) của một chip sẽ kết nối trực tiếp với chân Rx (nhận) của chip khác và ngược lại. Quá trình truyền dữ liệu thường sẽ diễn ra ở 3.3V hoặc 5V.

Khi tín hiệu gửi trên chân Tx (truyền), bộ giao tiếp Uart đầu tiên sẽ dịch thông tin song song này thành dạng nối tiếp và sau đó truyền tới thiết bị nhận. Chân Rx (nhận) của Uart thứ 2 sẽ biến đổi nó trở lại thành dạng song song để giao tiếp với các thiết bị điều khiển.

Dữ liệu truyền qua Uart sẽ đóng thành các gói (packet). Mỗi gói dữ liệu chứa 1 bit bắt đầu, 5 – 9 bit dữ liệu (tùy thuộc vào bộ Uart), 1 bit chẵn lẻ tùy chọn và 1 bit hoặc 2 bit dừng.

![image](https://github.com/user-attachments/assets/08a61cd1-45e6-4669-93e1-48fcced38435)
 
Quá trình truyền dữ liệu Uart sẽ diễn ra dưới dạng các gói dữ liệu này, bắt đầu bằng 1 bit bắt đầu, đường mức cao được kéo dần xuống thấp. Sau bit bắt đầu là 5 – 9 bit dữ liệu truyền trong khung dữ liệu của gói, theo sau là bit chẵn lẻ tùy chọn để nhằm xác minh việc truyền dữ liệu thích hợp. Sau cùng, 1 hoặc nhiều bit dừng sẽ được truyền ở nơi đường đặt tại mức cao. Vậy là sẽ kết thúc việc truyền đi một gói dữ liệu


</p>
</details>

</p>
</details>

<br>

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

<br>

<details><summary><b>Giao thức CAN</b></summary>
<p>

<details><summary><b>Lý thuyết</b></summary>
<p>

Giao thức CAN (Controller Area Network) là một giao thức truyền thông được sử dụng rộng rãi trong các hệ thống nhúng, đặc biệt là trong lĩnh vực ô tô và các ứng dụng công nghiệp. CAN cho phép các vi điều khiển và các thiết bị khác nhau giao tiếp với nhau mà không cần có máy tính chủ.

![image](https://github.com/user-attachments/assets/3d190f74-e296-402e-9e31-ac6c11be8b65)

</p>
</details>

<details><summary><b>Kiến trúc</b></summary>
<p>

<details><summary><b>📚 Bus topology</b></summary>
<p>

Mõi thiết bị trong hệ thống được gọi là node và CAN sử dụng tô-pô bus để kết nối các node với nhau, nghĩa là tất cả các thiết bị (node) đều được kết nối song song vào một cặp dây truyền thông chung được gọi là CAN bus. 

![image](https://github.com/user-attachments/assets/22f732a2-ec2f-4085-b38f-e312d596f919)

<br>

CAN bus gồm 2 dây tín hiệu chính:

- **CAN_H (CAN High)**: dây tín hiệu cao.
- **CAN_L (CAN Low)**: dây tín hiệu thấp.

<br>

**2 dây CAN_H và CAN_L sẽ được xoắn lại tạo thành đường dây xoắn đôi giúp**:

- **●	Giảm thiểu nhiễu từ môi trường bên ngoài**: sau khi xoắn đôi, nếu có nhiễu thì mỗi dây đều nhận nhiễu như nhau, cùng tăng hoặc cùng giảm một điện áp như nhau, điều này sẽ giúp chênh lệch điện áp giữa 2 dây không thay đổi khi có nhiễu.
- **Giảm thiểu nhiễu xuyên âm**: Việc xoắn đôi các dây giúp giảm hiện tượng này bằng cách phân tán nhiễu xuyên âm ra khắp chiều dài của cáp.

<br>

**Đặc điểm của tô-pô bus**:

- **Kết nối song song**: Tất cả các thiết bị trên bus CAN đều được kết nối song song với nhau. Mỗi thiết bị (node) có thể truy cập vào bus để truyền hoặc nhận dữ liệu bất cứ lúc nào, mà không cần một máy tính chủ (master) điều khiển.
- **Giảm số lượng dây dẫn**: Với tô-pô bus, tất cả các thiết bị chia sẻ chung một bus truyền dữ liệu, làm giảm đáng kể số lượng dây dẫn so với các mô hình khác. Điều này giúp giảm chi phí, tiết kiệm không gian và đơn giản hóa hệ thống dây dẫn trong các hệ thống nhúng.
- **Termination resistor (Điện trở kết cuối)**: Mỗi đầu của bus CAN cần một điện trở kết cuối với giá trị 120Ω để ngăn chặn hiện tượng phản xạ tín hiệu (hấp thụ phản xạ). Nếu không có điện trở này, tín hiệu có thể bị phản xạ lại từ các đầu – cuối mở, gây ra nhiễu và làm hỏng dữ liệu.


</p>
</details>

<details><summary><b>📚 Các thiết bị trên bus CAN</b></summary>
<p>

Mạng CAN hỗ trợ nhiều loại thiết bị khác nhau trên cùng 1 bus, mỗi thiết bị được gọi là một **node**. Mỗi node sẽ bao gồm:

- **Cảm biến (Sensors)**: Các cảm biến thu thập dữ liệu từ môi trường (như nhiệt độ, áp suất, tốc độ) và gửi dữ liệu này lên bus CAN để các thiết bị khác xử lý.
- **Actuator (Thiết bị kích động)**: Đây là các thiết bị đầu ra, nhận lệnh từ các vi điều khiển qua bus CAN để thực hiện các hành động vật lý, chẳng hạn như mở van, điều khiển động cơ hoặc bật đèn.
- **Bộ điều khiển CAN (CAN Controller)**: Đây là thành phần chính trong node CAN, có nhiệm vụ xử lý toàn bộ giao tiếp CAN.

    📚 Gửi và nhận thông điệp CAN.
  
    📚 Điều khiển truy cập vào bus CAN (arbitration).
  
    📚 Phát hiện và xử lý các lỗi truyền thông CAN.
  
    📚 Kiểm soát việc truyền lại thông điệp khi gặp lỗi.
  
    📚 Cung cấp giao diện giữa các **vi điều khiển** và bus CAN.

- **CAN Transceiver**:

    📚 Chuyển đổi tín hiệu số từ bộ điều khiển CAN thành tín hiệu điện áp dạng vi sai (CAN_H và CAN_L) để gửi lên bus CAN và ngược lại.

    📚 Đảm bảo tín hiệu truyền và nhận bus CAN có độ chính xác và tốc độ cao.

- **Vi điều khiển (Microcontroller)**: là thành phần trung tâm điều khiển hoạt động của node CAN.

    📚 Đọc và xử lý thông điệp CAN.

    📚 Tạo ra thông điệp CAN để truyền đi.

    📚 Quản lý các khung dữ liệu, bit arbitration và quá trình xử lý lỗi.

    📚 Điều khiển hành vi của node (ví dụ: bật/tắt node, reset node khi gặp lỗi bus-off).

</p>
</details>

<details><summary><b>📚 Đặc điểm giao tiếp của CAN</b></summary>
<p>

- **Không cần máy tính chủ (No Master-Slave Architecture)**: Mạng CAN không tuân theo kiến trúc master-slave. Tất cả các thiết bị trên bus đều có quyền bình đẳng trong việc truyền dữ liệu mà không cần phải có thiết bị chủ điều khiển. Điều này cho phép mạng hoạt động linh hoạt hơn, khi bất kỳ node nào cũng có thể truyền hoặc nhận thông tin bất cứ lúc nào.

<br>

- **Truyền thông quảng bá (Broadcast Communication)**: Khi một node gửi thông điệp, thông điệp đó sẽ được phát sóng đến tất cả các node khác trên bus. Tuy nhiên, không phải tất cả các node đều xử lý thông điệp này. Mỗi node sẽ sử dụng bộ lọc để kiểm tra xem thông điệp có phù hợp với mình hay không.

<br>

- **Tranh chấp quyền gửi (Arbitration)**: Nếu có nhiều node cùng muốn gửi dữ liệu lên bus cùng một lúc, CAN sẽ thực hiện cơ chế tranh chấp:

    📚 Mỗi thông điệp CAN có một ID ưu tiên. Node nào có thông điệp với ID ưu tiên thấp hơn (tức có độ ưu tiên cao hơn) sẽ chiếm quyền truy cập bus và gửi thông điệp trước.

    📚 Những node khác có ID ưu tiên cao hơn sẽ tự động dừng lại và chờ lượt tiếp theo để gửi thông điệp.

    📚 Quá trình arbitration diễn ra mà không gây mất dữ liệu hay làm gián đoạn các thiết bị khác, vì thế mạng CAN là một hệ thống non-destructive (không gây mất dữ liệu).

<br>

- **Giao tiếp song công (Full-duplex Communication)**: Mặc dù chỉ sử dụng một bus với hai dây tín hiệu, mạng CAN vẫn cho phép các node vừa gửi vừa nhận dữ liệu đồng thời. Điều này giúp mạng CAN hoạt động hiệu quả và không bị nghẽn khi có nhiều thiết bị cùng giao tiếp.

<br>

- **Phát hiện và xử lý lỗi tự động**: Một tính năng quan trọng khác của mạng CAN là khả năng tự động phát hiện và xử lý lỗi. Nếu một node phát hiện ra lỗi trong quá trình truyền hoặc nhận dữ liệu (do nhiễu, mất gói, hoặc lỗi tín hiệu), node đó sẽ gửi một Error Frame để thông báo cho các node khác rằng dữ liệu bị lỗi. Sau đó, thông điệp sẽ được truyền lại.


</p>
</details>

</p>
</details>

<details><summary><b>Khung dữ liệu CAN</b></summary>
<p>

<details><summary><b>1. Cấu trúc chung của một khung dữ liệu trong CAN</b></summary>
<p>

![image](https://github.com/user-attachments/assets/886378e1-fc4a-4014-8d30-c339d8493389)

<details><summary><b>📚 Start of Frame (SOF) </b></summary>
<p>

SOF là bit bắt đầu của khung dữ liệu, **chỉ có giá trị dominant (0)**. Nó báo hiệu rằng một khung dữ liệu mới đang bắt đầu. Tất cả các node trên mạng sẽ nhận biết rằng đây là thời điểm để bắt đầu đọc dữ liệu.

</p>
</details>

<details><summary><b>📚 Arbitration Field (Trường tranh chấp)</b></summary>
<p>

Trường này chứa ID của thông điệp và bit RTR (Remote Transmission Request).

- **ID**: Chứa định danh của thông điệp, ID này được sử dụng để xác định mức độ ưu tiên trong quá trình arbitration (tranh chấp quyền gửi).
- **RTR**: Đối với Data Frame, bit này sẽ có giá trị dominant (0). Đối với Remote Frame, bit này sẽ có giá trị recessive (1), báo hiệu rằng đây là một yêu cầu dữ liệu từ một node khác.

</p>
</details>

<details><summary><b>📚 Control Field (Trường điều khiển)</b></summary>
<p>

Control Field chứa các thông tin về kích thước của phần dữ liệu.

DLC (Data Length Code): Đây là trường quan trọng trong Control Field, xác định độ dài của dữ liệu (từ 0 đến 8 byte).

</p>
</details>

<details><summary><b>📚 Data Field (Trường dữ liệu)</b></summary>
<p>

Data Field là phần chứa dữ liệu chính của khung, có thể có từ 0 đến 8 byte dữ liệu. Trong Data Frame, đây là nơi chứa thông tin mà node gửi muốn truyền tải.

</p>
</details>

<details><summary><b>📚 CRC Field (Trường kiểm tra lỗi)</b></summary>
<p>

Đây là trường kiểm tra lỗi, giúp phát hiện các lỗi xảy ra trong quá trình truyền dữ liệu. Node nhận sẽ sử dụng CRC Field để kiểm tra xem dữ liệu đã được truyền chính xác hay chưa. Nếu phát hiện lỗi, một Error Frame sẽ được gửi đi.

</p>
</details>

<details><summary><b>📚 ACK Field (Trường xác nhận)</b></summary>
<p>

ACK Field được sử dụng để xác nhận rằng một thông điệp đã được nhận thành công. Khi một node nhận được dữ liệu mà không phát hiện lỗi, nó sẽ gửi bit ACK dominant (0) vào trường ACK để thông báo cho node gửi rằng dữ liệu đã được nhận chính xác.

Nếu không có node nào gửi ACK, điều này báo hiệu rằng có lỗi xảy ra hoặc thông điệp không được nhận đúng cách, và node gửi sẽ phải truyền lại thông điệp.

</p>
</details>

<details><summary><b>📚 End of Frame (EOF)</b></summary>
<p>

EOF là trường kết thúc của khung dữ liệu, chứa một chuỗi các bit recessive (1). Trường này báo hiệu rằng toàn bộ khung dữ liệu đã được truyền và quá trình truyền thông cho khung này đã kết thúc.

</p>
</details>

</p>
</details>

<details><summary><b>2. Các loại khung dữ liệu trong CAN</b></summary>
<p>

<details><summary><b>📚 Data Frame (Khung dữ liệu)</b></summary>
<p>

Data Frame là khung phổ biến nhất được sử dụng trong giao thức CAN và được sử dụng để truyền dữ liệu thực tế giữa các node trên mạng CAN.

Data Frame bao gồm các thông tin về địa chỉ của node gửi và nhận, kích thước dữ liệu, và chính dữ liệu cần truyền. Frame này giúp đảm bảo rằng dữ liệu sẽ được truyền đúng cách và bảo vệ khỏi lỗi bằng cách sử dụng mã kiểm tra CRC.

<br>

**Cấu trúc của Data Frame**:

![image](https://github.com/user-attachments/assets/ecbe004b-98e1-44fd-8015-4cf8761c659b)

![image](https://github.com/user-attachments/assets/43169b4f-e71f-4df5-ab94-1071659b839c)

- **1. Start of Frame (SOF)**: 1 bit để báo hiệu bắt đầu của khung truyền và **luôn là một bit dominant (0)**.
- **2. Arbitration Field**: Chứa địa chỉ của node gửi hoặc node nhận. Có thể là **11-bit ID (Identifier chuẩn)** hoặc **29-bit ID (Identifier mở rộng)**, giúp phân biệt giữa các node. Trường này cũng chứa 1 bit RTR để xác định kiểu khung là Data Frame (RTR = 0) hay Remote Frame (RTR = 1).
- **3. Control Field**: Chứa DLC (Data Length Code), chỉ ra số byte dữ liệu trong khung, từ 0 đến 8 byte.
- **4. Data Field**: Chứa dữ liệu thực tế cần truyền. Độ dài từ 0 đến 8 byte tùy thuộc vào giá trị của DLC.
- **5. CRC Field**: Dùng để phát hiện lỗi trong quá trình truyền thông qua mạng.
- **6. ACK Field**: Node nhận sẽ gửi tín hiệu ACK để xác nhận rằng dữ liệu đã được nhận thành công.
- **7. End of Frame (EOF)**: gồm 7 bit Recessive, dùng để thông báo kết thúc một Data Frame hay Remote Frame.

<br>

Data Frame **xảy ra** khi một node cần truyền dữ liệu đến các node khác trên mạng CAN. Các ứng dụng phổ biến của Data Frame bao gồm giao tiếp giữa các vi điều khiển, cảm biến, hoặc thiết bị điều khiển trong các hệ thống nhúng.

<br>

**Tình huống sử dụng**:

- Data Frame này có thể được dùng trong một mạng CAN của xe hơi, nơi mà bộ điều khiển trung tâm (ECU) gửi lệnh điều khiển các mô-tơ hoặc cảm biến trong hệ thống. Ví dụ, nếu đây là một hệ thống điều khiển ghế xe, lệnh điều khiển có thể yêu cầu mô-tơ di chuyển ghế đến vị trí mới.
- Trong ứng dụng công nghiệp, Data Frame có thể được sử dụng để một cảm biến gửi dữ liệu về nhiệt độ hoặc áp suất tới bộ điều khiển chính để thực hiện các hành động điều chỉnh.

</p>
</details>

<details><summary><b>📚 Remote Frame (Khung yêu cầu)</b></summary>
<p>

Remote Frame là một loại khung trong giao thức CAN được sử dụng để yêu cầu một node khác gửi dữ liệu qua Data Frame. Khác với Data Frame, Remote Frame không chứa dữ liệu thực tế trong trường Data Field, mà chỉ yêu cầu node khác gửi lại một Data Frame có cùng định danh (Identifier). Một trong những đặc điểm quan trọng của Remote Frame là nó thiết lập bit RTR (Remote Transmission Request) để phân biệt với Data Frame.

<br>

**Cấu trúc của Remote Frame**

![image](https://github.com/user-attachments/assets/94e44523-7435-4bcd-bb7f-5d015a0b1eb5)

- **1. Start of Frame (SOF)**: 1 bit để báo hiệu bắt đầu của khung truyền và **luôn là một bit dominant (0)**.
- **2. Arbitration Field**: Bao gồm định danh (11-bit hoặc 29-bit Identifier) và bit RTR được đặt thành 1 để báo đây là Remote Frame.
- **3. Control Field**: Chứa DLC (Data Length Code), chỉ ra số byte dữ liệu trong khung, từ 0 đến 8 byte.
- **4. CRC Field**: Dùng để phát hiện lỗi trong quá trình truyền thông qua mạng.
- **5. ACK Field**: Sử dụng để xác nhận rằng khung đã được nhận.
- **6. End of Frame (EOF)**: gồm 7 bit Recessive, dùng để thông báo kết thúc một Data Frame hay Remote Frame.

<br>

Remote Frame **xảy ra** khi một node muốn yêu cầu dữ liệu từ một node khác trên mạng CAN mà không tự động nhận dữ liệu. Node gửi sẽ phát Remote Frame, sau đó node nhận sẽ trả lời bằng một Data Frame chứa dữ liệu được yêu cầu.

<br>

**Tình huống sử dụng**

- Remote Frame này có thể được sử dụng trong một mạng CAN công nghiệp để yêu cầu cảm biến gửi dữ liệu khi cần thiết. Ví dụ, một bộ điều khiển trung tâm có thể gửi Remote Frame với định danh của cảm biến nhiệt độ, yêu cầu nó gửi lại Data Frame chứa thông tin nhiệt độ hiện tại.
- Trong một hệ thống xe hơi, Remote Frame có thể được gửi bởi ECU để yêu cầu cảm biến vị trí của bánh xe gửi lại thông tin vị trí hiện tại, từ đó giúp điều khiển hệ thống phanh ABS hoặc điều chỉnh các thông số khác trong xe.


</p>
</details>

<details><summary><b>📚 Error Frame (Khung lỗi)</b></summary>
<p>

**Error Frame** là khung được tự động phát ra bởi một node CAN khi nó phát hiện lỗi trong quá trình giao tiếp. Khung này có mục đích thông báo cho các node khác trong mạng về việc phát hiện lỗi và yêu cầu quá trình truyền thông được khởi động lại. Error Frame không được người dùng gửi trực tiếp, mà phần cứng CAN sẽ tự động phát hiện và phát ra khi có lỗi.

Trong giao thức CAN, có hai loại Error Frame:

- **Active Error Frame**: Được phát ra bởi một node đang trong trạng thái Active Error, có thể can thiệp để sửa lỗi. Node này sẽ phát ra 6 bit Error Flag (6 bit liên tiếp có giá trị 0 - dominant bit).
- **Passive Error Frame**: Được phát ra bởi một node trong trạng thái Passive Error, khi nó đã gặp nhiều lỗi nhưng không thể sửa lỗi. 12 bit Error Flag được gửi (thay vì 6 bit trong **Active Error Frame**), bao gồm 6 bit dominant và 6 bit recessive. Điều này nhằm thông báo rằng node đó đã vượt qua giới hạn lỗi và không còn khả năng sửa lỗi chủ động.

<br>

**Chuyển đổi giữa các trạng thái Active và Passive**

Error Counter: Các node CAN quản lý một Error Counter để theo dõi số lượng lỗi mà chúng gặp phải. Mỗi khi một lỗi được phát hiện, giá trị của Error Counter sẽ tăng lên.

- Khi Error Counter **vượt qua ngưỡng 127**, node sẽ chuyển từ trạng thái Active Error sang Passive Error. Trong trạng thái này, node sẽ phát ra Passive Error Frame nếu phát hiện lỗi.
- Nếu Error Counter tiếp tục tăng và vượt ngưỡng 255, node sẽ chuyển sang trạng thái Bus Off, tức là node sẽ bị loại khỏi mạng CAN và không thể giao tiếp thêm cho đến khi được reset lại.

<br>

**Cấu trúc của Error Frame**:

![image](https://github.com/user-attachments/assets/f44e22cd-3990-4702-bdc3-f26c47171335)

- **1. Error Flag**: 6 hoặc 12 bit, phụ thuộc vào trạng thái lỗi (Active hoặc Passive).
- **2. Error Delimiter**: 8 bit để phân tách Error Frame với các khung khác.

<br>

Error Frame xảy ra khi một node phát hiện một trong các lỗi sau trong quá trình truyền dữ liệu:

- **Bit Error**: Xảy ra khi một node phát hiện bit truyền ra không giống với bit nhận được.
- **CRC Error**: Xảy ra khi có lỗi trong quá trình kiểm tra mã CRC.
- **ACK Error**: Xảy ra khi node không nhận được tín hiệu ACK từ các node khác.
- **Form Error**: Xảy ra khi một trường trong khung không tuân theo định dạng đúng của giao thức CAN.
- **Stuff Error**: Xảy ra khi có nhiều hơn 5 bit giống nhau liên tiếp trong một khung (CAN sử dụng Bit stuffing để tránh điều này).

Khi bất kỳ lỗi nào được phát hiện, node phát ra Error Frame và các node khác trên mạng CAN sẽ tạm dừng quá trình giao tiếp và xử lý lại khung


</p>
</details>

<details><summary><b>📚 Overload Frame (Khung quá tải)</b></summary>
<p>

Overload Frame là một loại khung đặc biệt trong giao thức CAN được sử dụng để trì hoãn việc truyền dữ liệu khi một node trong mạng CAN cần thêm thời gian để xử lý. Khung này không chứa dữ liệu, mà chỉ báo hiệu rằng một node đang quá tải và cần thời gian trước khi tiếp tục giao tiếp. Mục tiêu của Overload Frame là ngăn không cho các khung khác được truyền quá nhanh, giúp node bị quá tải có đủ thời gian để xử lý các khung trước đó.

Overload Frame không phải do người dùng phát ra, mà được tự động phát ra bởi phần cứng CAN khi cần thiết. Node CAN sẽ phát ra Overload Frame khi một trong các điều kiện sau xảy ra:

- Node không thể xử lý tiếp dữ liệu do buffer đã đầy hoặc cần thêm thời gian xử lý dữ liệu.
- Node không thể nhận khung mới do có quá trình xử lý nội bộ cần hoàn thành trước.

<br>

**Cấu trúc của Overload Frame**:

![image](https://github.com/user-attachments/assets/6b9c4e01-f31f-4f32-b386-62b506d73b1a)

- **1. Overload Flag**: 6 bit dominant (bit 0) để báo hiệu trạng thái quá tải.
- **2. Overload Delimiter**: 8 bit recessive (bit 1), để phân tách khung quá tải với các khung khác và báo hiệu kết thúc Overload Frame.

Các điều kiện có thể gây ra Overload Frame:

- FIFO (First-In-First-Out) buffer trong node nhận đầy và node cần thêm thời gian để xử lý dữ liệu đã nhận.
- Tạm dừng nội bộ trong node để hoàn tất việc xử lý một sự kiện trước khi nhận thêm khung dữ liệu mới.
- Node cần xử lý một yêu cầu cao cấp khác (như một yêu cầu từ phần mềm ứng dụng).

<br>

Overload Frame **xảy ra** khi một node cần thêm thời gian để xử lý khung dữ liệu đã nhận trước đó. Điều này ngăn các node khác truyền khung mới quá sớm, gây ra quá tải xử lý cho node đã phát ra Overload Frame.

Overload Frame có thể được phát ra ngay sau Intermission Field (khoảng trống giữa các khung) hoặc ngay sau khi một khung dữ liệu đã được truyền hoàn tất, nếu node nhận không thể xử lý kịp thời. Trong thực tế, điều này thường xảy ra khi một node đang nhận nhiều dữ liệu từ nhiều nguồn khác nhau trên mạng CAN và cần tạm dừng để xử lý trước khi tiếp tục nhận thêm dữ liệu.


</p>
</details>

</p>
</details>

</p>
</details>

<details><summary><b>Arbitration trong CAN</b></summary>
<p>

<details><summary><b>📚 Cơ chế ưu tiên</b></summary>
<p>

Trong mạng CAN, ID của thông điệp đóng vai trò quan trọng trong việc xác định mức độ ưu tiên. Mỗi thông điệp CAN đều có một ID định danh (identifier), và giá trị của ID này quyết định mức độ ưu tiên khi có nhiều node cố gắng gửi dữ liệu cùng một lúc.

ID thấp hơn tương ứng với mức độ ưu tiên cao hơn. Nghĩa là, khi nhiều node cùng muốn truyền dữ liệu, node có ID nhỏ hơn (giá trị nhị phân thấp hơn) sẽ được ưu tiên và thắng quá trình arbitration.

Mỗi bit trong ID của thông điệp có thể ở trạng thái dominant (trạng thái ưu tiên – giá trị 0) hoặc recessive (trạng thái không ưu tiên – giá trị 1). Khi hai node hoặc nhiều node cùng gửi dữ liệu, CAN sử dụng quy tắc wire – AND logic để quyết định node nào được ưu tiên.

![image](https://github.com/user-attachments/assets/ac963fd6-6fb1-449e-bb60-87949bcc9d6f)

<br>

![image](https://github.com/user-attachments/assets/d70014b9-1a0f-4b5f-8c8e-6f5ef5845e9f)

<br>

**Nguyên lý hoạt động**:

- Khi nhiều node muốn truyền dữ liệu, chúng đều bắt đầu gửi thông điệp của mình lên bus. Tín hiệu được gửi đồng thời và mỗi node sẽ kiểm tra từng bit của dữ liệu trên bus.
- Mỗi bit trong ID sẽ được truyền từng cái một (từ bit MSB - Most Significant Bit). Nếu một node gửi bit recessive (1) nhưng nhận thấy trên bus có bit dominant (0), nghĩa là có một node khác có ưu tiên cao hơn đang chiếm quyền truyền dữ liệu. Lúc này, node này sẽ ngừng truyền và chuyển sang chế độ nghe (listen).
- Node có ID thấp hơn (tức là có nhiều bit dominant hơn ở đầu) sẽ tiếp tục quá trình truyền cho đến khi toàn bộ ID được gửi đi, trong khi các node khác ngừng gửi và chuyển sang chế độ chờ.
- Các node không thắng quá trình arbitrage sẽ không bị mất dữ liệu mà chỉ đơn giản là đợi lượt tiếp theo để cố gắng truyền lại thông điệp của mình.


</p>
</details>

<details><summary><b>📚 Non-destructive Arbitration (Tranh chấp không phá hủy)</b></summary>
<p>

Cơ chế non-destructive arbitration có nghĩa là quá trình arbitrage diễn ra mà không làm mất dữ liệu của các node thua. Điều này có được nhờ vào tính năng multi-master và cơ chế wire-AND logic của CAN.

Khi một node thua trong quá trình arbitration, nó sẽ tạm dừng việc truyền nhưng không xóa dữ liệu của mình.

Node thua sẽ chuyển sang trạng thái chờ và lắng nghe bus. Khi bus không còn bận (tức là node thắng đã gửi xong thông điệp), node thua sẽ thử lại và tham gia tranh chấp quyền gửi ở lần tiếp theo.

Quá trình này đảm bảo rằng không có dữ liệu bị mất trong quá trình tranh chấp, vì các node thua sẽ tiếp tục gửi thông điệp của mình vào thời điểm thích hợp.


</p>
</details>

</p>
</details>

<details><summary><b>Lỗi trong giao thức CAN</b></summary>
<p>

<details><summary><b>1. Các loại lỗi trong CAN</b></summary>
<p>

<details><summary><b>📚 Bit Error</b></summary>
<p>

Bit Error xảy ra khi một node gửi một bit (dominant hoặc recessive) lên bus và nhận lại một bit khác với giá trị mong đợi. Trong mạng CAN, mỗi node không chỉ gửi dữ liệu mà còn tự lắng nghe các tín hiệu trên bus để kiểm tra sự đồng bộ.

- Bit dominant (0): Tín hiệu ưu tiên trên bus.
- Bit recessive (1): Tín hiệu không ưu tiên trên bus.

Nguyên nhân:

- Nếu một node gửi một bit recessive (1) nhưng nhận lại bit dominant (0) từ bus, node này sẽ phát hiện ra lỗi.
- Điều này có thể xảy ra khi một node khác có ưu tiên cao hơn trên bus đang truyền dữ liệu, hoặc do tín hiệu bị nhiễu.

</p>
</details>

<details><summary><b>📚 Stuff Error</b></summary>
<p>

Stuff Error xảy ra khi có hơn 5 bit liên tiếp cùng giá trị (tất cả đều là 0 hoặc tất cả đều là 1) trên bus CAN. Điều này vi phạm quy tắc bit stuffing của giao thức CAN.

**Quy tắc bit stuffing**: Trong mạng CAN, sau mỗi chuỗi 5 bit giống nhau liên tiếp, một bit ngược giá trị (ngược với giá trị của các bit trước đó) phải được thêm vào để đảm bảo tính đồng bộ và tránh nhiễu tín hiệu. Nếu quy tắc này bị vi phạm, lỗi sẽ xảy ra.

Nguyên nhân: Vi phạm quy tắc bit stuffing có thể do lỗi trong quá trình truyền tín hiệu hoặc do thiết bị không tuân theo quy chuẩn CAN.

</p>
</details>

<details><summary><b>📚 CRC Error</b></summary>
<p>

CRC Error xảy ra khi có sai lệch trong quá trình kiểm tra CRC (Cyclic Redundancy Check), được sử dụng để phát hiện lỗi trong dữ liệu truyền qua bus.

Cơ chế CRC:

- Trong mỗi khung dữ liệu CAN, có một CRC Field được sử dụng để kiểm tra tính toàn vẹn của dữ liệu. Trường này chứa giá trị CRC, được tính toán dựa trên nội dung của thông điệp.
- Node nhận sẽ tính toán lại giá trị CRC của dữ liệu nhận được và so sánh với CRC trong trường CRC Field. Nếu hai giá trị này không khớp, một CRC error sẽ được phát hiện.

Nguyên nhân: Lỗi CRC có thể xảy ra do nhiễu tín hiệu trong quá trình truyền dữ liệu hoặc do lỗi phần cứng trong node gửi hoặc nhận.


</p>
</details>

<details><summary><b>📚 Form Error</b></summary>
<p>

Form Error xảy ra khi cấu trúc khung dữ liệu không tuân theo quy chuẩn của giao thức CAN. Mỗi khung dữ liệu trong CAN phải tuân theo một cấu trúc định sẵn, bao gồm Start of Frame (SOF), Arbitration Field, Control Field, Data Field, CRC Field, ACK Field, và End of Frame (EOF).

Nguyên nhân: Nếu một node nhận thấy có lỗi trong định dạng của bất kỳ trường nào trong khung dữ liệu, đặc biệt là các bit trong EOF hoặc ACK Field, nó sẽ phát hiện Form Error.

</p>
</details>

<details><summary><b>📚 Acknowledgment Error</b></summary>
<p>

Acknowledgment Error (ACK Error) xảy ra khi node gửi thông điệp lên bus mà không nhận được bit ACK từ bất kỳ node nào trên mạng.

Cơ chế ACK trong CAN:

- Khi một node gửi thành công một khung dữ liệu, các node nhận phải gửi một bit ACK dominant (0) để xác nhận rằng dữ liệu đã được nhận chính xác.
- Nếu không có node nào gửi bit ACK, node gửi sẽ phát hiện ACK Error và phải truyền lại thông điệp.

Nguyên nhân:

- Thiết bị nhận có thể không hoạt động đúng cách hoặc không kết nối đúng vào bus CAN.
- Tín hiệu ACK có thể bị nhiễu hoặc lỗi phần cứng.

</p>
</details>

<details><summary><b>📚 </b></summary>
<p>

</p>
</details>

</p>
</details>

<details><summary><b>2. Cơ chế phát hiện lỗi trong mạng CAN</b></summary>
<p>

Mạng CAN sử dụng nhiều cơ chế để phát hiện lỗi, giúp duy trì tính ổn định và tin cậy của dữ liệu truyền tải trên bus. Các cơ chế này bao gồm:

- **Kiểm tra bit**: Mỗi node gửi sẽ tự lắng nghe dữ liệu mà nó vừa gửi để đảm bảo rằng dữ liệu đó đã được truyền đúng cách. Nếu có sự khác biệt giữa bit gửi đi và bit nhận lại, node sẽ phát hiện bit error.
- **Kiểm tra CRC**: Mỗi thông điệp CAN chứa một giá trị CRC được tính toán dựa trên dữ liệu. Node nhận sẽ tính toán lại giá trị CRC và so sánh với CRC của thông điệp để phát hiện lỗi.
- **Kiểm tra định dạng (Form Check)**: Các bit trong EOF và ACK Field phải tuân theo một định dạng chuẩn. Nếu không, node nhận sẽ phát hiện form error.
- **Xác nhận (Acknowledgment)**: Node gửi sẽ kiểm tra xem có bất kỳ node nào trên bus gửi bit ACK để xác nhận rằng dữ liệu đã được nhận thành công. Nếu không, ACK error sẽ được phát hiện.


</p>
</details>

<details><summary><b>3. Cơ chế sửa lỗi tự động trong mạng CAN</b></summary>
<p>

Khi lỗi được phát hiện, mạng CAN có khả năng sửa lỗi một cách tự động thông qua quá trình phát Error Frame và truyền lại thông điệp.

Cơ chế sửa lỗi trong CAN:

- **Error Frame**: Khi một node phát hiện lỗi (bit error, CRC error, form error, stuff error, hoặc ACK error), nó sẽ gửi một Error Frame để thông báo cho tất cả các node khác trên bus rằng có lỗi đã xảy ra.
- **Truyền lại thông điệp**: Sau khi Error Frame được phát, các node sẽ dừng giao tiếp và node gửi ban đầu sẽ cố gắng truyền lại thông điệp bị lỗi. Việc này sẽ tiếp tục cho đến khi thông điệp được truyền đi thành công hoặc node gửi bị đưa vào trạng thái bus off nếu lỗi quá nhiều.

</p>
</details>

<details><summary><b>4. Các trạng thái lỗi của node</b></summary>
<p>

Khi phát hiện lỗi, các node trong mạng CAN sẽ tự động chuyển đổi giữa ba trạng thái lỗi để đảm bảo hệ thống hoạt động ổn định và không gây gián đoạn cho bus.

<details><summary><b>📚 Error Active</b></summary>
<p>

Trong trạng thái Error Active, node vẫn có khả năng tham gia đầy đủ vào quá trình truyền thông và có thể phát hiện lỗi. Nếu node phát hiện lỗi, nó sẽ gửi một Error Frame để thông báo cho các node khác trên bus rằng đã xảy ra lỗi.

</p>
</details>

<details><summary><b>📚 Error Passive</b></summary>
<p>
    
Nếu một node phát hiện quá nhiều lỗi, nó sẽ chuyển sang trạng thái Error Passive. Trong trạng thái này, node vẫn có thể tham gia truyền thông, nhưng nếu phát hiện lỗi, nó sẽ không gửi Error Frame mạnh mẽ như trong trạng thái Error Active. Điều này giúp tránh gây gián đoạn lớn cho bus khi node gặp sự cố thường xuyên.

Trong trạng thái Error Passive, node vẫn có thể nhận và gửi thông điệp nhưng sẽ hạn chế việc can thiệp vào quá trình truyền thông của các node khác. Node chỉ gửi Error Frame yếu hơn để thông báo lỗi, và không ảnh hưởng đến quá trình truyền thông của các node khác.


</p>
</details>

<details><summary><b>📚 Bus Off</b></summary>
<p>

Khi một node gặp quá nhiều lỗi nghiêm trọng, nó sẽ chuyển sang trạng thái Bus Off. Trong trạng thái này, node sẽ hoàn toàn ngắt kết nối khỏi bus CAN và không thể tham gia vào quá trình truyền hay nhận dữ liệu. Node chỉ có thể được kết nối lại vào bus sau khi được khởi động lại (restart) hoặc reset bởi phần mềm.

Bus Off là trạng thái an toàn, ngăn chặn một node bị lỗi nặng gây ra sự cố nghiêm trọng cho toàn bộ hệ thống CAN.

</p>
</details>

</p>
</details>

</p>
</details>

<details><summary><b>Tốc độ truyền và giới hạn vật lý của CAN</b></summary>
<p>

<details><summary><b>📚 Tốc độ baud của CAN</b></summary>
<p>

Tốc độ baud là tốc độ truyền dữ liệu trên bus CAN, thường được đo bằng kbps (kilobits per second) hoặc Mbps (megabits per second). Tốc độ baud quyết định tốc độ truyền thông giữa các thiết bị trên mạng và phụ thuộc vào khả năng xử lý của hệ thống cũng như chiều dài của bus.

**Dải tốc độ baud của CAN**: 

Mạng CAN hỗ trợ dải tốc độ baud từ 10 kbps đến 1 Mbps.

- 10 kbps: Tốc độ thấp nhất, thường được sử dụng cho các hệ thống có yêu cầu truyền thông chậm, nhưng cần truyền xa.
- 1 Mbps: Tốc độ cao nhất, thường được sử dụng trong các ứng dụng yêu cầu truyền thông nhanh, chẳng hạn như trong hệ thống ô tô hoặc robot.

**Ảnh hưởng của tốc độ baud**:

- **Chiều dài tối đa của bus**: Tốc độ truyền càng cao, chiều dài tối đa của bus càng ngắn do ảnh hưởng của thời gian lan truyền tín hiệu trên bus. Điều này có nghĩa là khi cần truyền dữ liệu với tốc độ cao, hệ thống phải chấp nhận giảm chiều dài của bus để đảm bảo tín hiệu truyền chính xác và đồng bộ.
- **Độ trễ**: Tốc độ baud càng cao, độ trễ của việc truyền thông tin trên mạng càng giảm, giúp cải thiện khả năng đáp ứng của hệ thống.


</p>
</details>

<details><summary><b>📚 Chiều dài tối đa của bus trong CAN</b></summary>
<p>

Chiều dài của bus trong mạng CAN bị giới hạn bởi tốc độ baud và chất lượng của dây dẫn (bus). Sự kết hợp giữa tốc độ truyền và chiều dài của bus quyết định khả năng truyền tín hiệu đúng cách và độ tin cậy của mạng.

**Tốc độ truyền càng cao, chiều dài bus càng ngắn**: Điều này do thời gian lan truyền tín hiệu trên dây dẫn cần phải nhỏ hơn một khoảng thời gian nhất định để đảm bảo tất cả các node trên bus có thể nhận được tín hiệu đồng bộ.

Khi tốc độ baud tăng lên, thời gian bit ngắn lại, nghĩa là tín hiệu phải đến các node nhận nhanh hơn. Do đó, chiều dài tối đa của bus phải giảm để đảm bảo thời gian lan truyền tín hiệu phù hợp với tốc độ baud.

</p>
</details>

</p>
</details>

</p>
</details>

<br>

📚📚📚
