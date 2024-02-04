# Process-1

Computer Organization and Operating System Assignment (Chapter : Process, Sec : 1)

  

# บทคัดย่อ

# Boot Process

Boot Process ของ Linux เป็นส่วนสำคัญของฟังก์ชันการทำงาน เนื่องจากเป็นขั้นตอนเริ่มต้นของการเริ่มต้นระบบปฏิบัติการ การทำความเข้าใจกระบวนการบูท Linux ถือเป็นสิ่งสำคัญสำหรับผู้ดูแลระบบ นักพัฒนา และใครก็ตามที่ทำงานกับ Linux

### Boot Process คืออะไร ?
Boot Process เป็นลักษณะพื้นฐานของระบบปฏิบัติการใดๆ เป็นกระบวนการที่ทำการ โหลดระบบปฏิบัติ(OS)ลงในหน่วยความจำ(Memory)ของคอมพิวเตอร์, กำหนดค่าเริ่มต้นของส่วนประกอบต่างๆ และเตรียมที่จะดำเนินการ แอปพลิเคชันของผู้ใช้

Boot process ของ Linux ประกอบด้วยหลายขั้นตอนที่มีความสำคัญต่อการทำงานของระบบปฏิบัติการ ซึ่งขั้นตอนต่างๆ ของกระบวนการบูทใน Linux มีดังนี้
### ขั้นตอน Boot Process ของ Linux
1.  **System startup:**  เป็นขั้นตอนแรกที่เกิดขึ้นเมื่อทำการเปิดเครื่อง มันจ่ายไฟฟ้าให้กับส่วนประกอบหลักทำงาน เช่น BIOS,CMOS,UEFI
2.  **Bootloader stage:** หลังจากขั้นตอนที่ 1 และสถานะของเครื่องปกติ ตัว BIOS,UEFI จะทำการ boot ตัว 
 storage ต่างๆ เพื่อหา bootloader ซึ่งใน linux ก็จะมี bootloader หลักๆคือ 
> - LILO
> -   SYSILINUX
> -   GRUB2
3. **Kernel:** หลังจากหา bootloader เจอ ก็จะนำมา เพื่อเริ่มต้น Kernel ขณะนี้ระบบปฏิบัติการจะควบคุมการเข้าถึงทรัพยากรคอมพิวเตอร์ของเราได้แล้ว
4. **Init process:** Kernel จะเริ่มต้นกระบวนการ init ซึ่งจะเริ่มกระบวนการหลัก ในที่นี้ parent ของกระบวนการ Linux ทั้งหมดคือ Systemd ตามขั้นตอนการบูต Systemd จะดำเนินการต่างๆ
# Process Management

### ประเภทของ Processes

#### Foreground processes หรือ interactive processes

processes เหล่านี้จะไม่ได้ intitialize จากระบบต้องถูกดำเนินการโดยผู้ใช้หรือโปรแกรมเมอร์ processes เหล่านี้จะรับ input และส่ง output คืนกลับไป ในขณะที่ processes เหล่านี้กำลังทำงานอยู่เราจะไม่สามารถเริ่ม process ใหม่ได้ใน terminal เดียวกัน

#### Background processes หรือ non interactive processes

processes เหล่านี้จะถูกดำเนินการโดยจากระบบหรือผู้ใช้ก็ได้ processes เหล่านี้มี PID หรือ process เฉพาะและสามารถเริ่ม processes ใน terminal เดียวกันได้

#### สถานะของ process ใน Linux

- **Running :** process ที่กำลังดำเนินการอยู่ใน CPU

- **Sleeping :** process ที่กำลังรอให้ทรัพยากรที่จะใช้นั้นว่าง

-  **Stopped :** process ที่ถูกทำลายโดยผู้ใช้

-  **Zombie :** process ที่ดำเนินการเสร้๗เรียบร้อยแล้วแต่ยังไม่ได้ถูกล้างโดยระบบ

-  **Orphan :** process ปัจจุบันที่ parent process ถูกทำลายไปแล้ว

### Process Manaagement คืออะไร

Process Management คือ งานในการควบคุมและติดตาม processesที่ทำงานอยู่บนระบบ Linux โดยรวมไปถึงกระบวนการจัดการทรัพยากร, การจัดลำดับการทำงานบน CPU, และการยกเลิกกระบวนการเมื่อจำเป็น

### คำสั่งของ Process Management ใน Linux

|คำสั่ง|คำอธิบาย|

|----|--------------|
|ps|แสดงข้อมูลเกี่ยวกับ processes ที่ทำงานอยู่|
|top|ให้ข้อมูลแบบ real-time เกี่ยวกับ processes ระบบและทรัพยากรที่ถูกใช้งาน|
|kill|ทำลาย process นั้นโดยการส่งสัญญาณไปยัง process นั้น|
|nice|ปรับลำดับความสำคัญของ process|
|renice|เปลี่ยนลำดับความสำคัญของ process ที่กำลังทำงานอยู่|
|ps PID|แสดงสถานะของ process ที่มีความแน่ชัด|
|pidof|แสดงหมายเลข ID ของ process|
|df|แสดง Disk Management ในระบบ|
|free|แสดงสถานะของ RAM|
|bg|สำหรับการส่ง process ที่กำลังทำงานไป background|
|fg|สำหรับการส่ง process ที่กำลังทำงานไป foreground|

### Process Management ในทางปฏิบัติ

#### การระบุและการยุติ processes ใน Linux

การระบุและการยุติ processes สามารถทำได้โดยใช้คำสั่งเหล่านี้ใน Linux
คำสั่ง`PS`ใช้ในการหา process ID (PID) ของ process ที่ต้องการจัดการ ตัวอย่างเช่น ถ้าหากจำเป็นที่ต้องปิด process นั้นก็ต้องรู้ process ID (PID) ของตัวนั้นที่แน่ชัดก่อน
คำสั่ง`kill`ใช้เพื่อทำลาย processes ด้วย process ID (PID)
คำสั่ง`killall`ใน Linux ใช้เพื่อทำลาย processes ด้วยชื่อ เป็นการทำลาย process วิธีที่มีประสิทธิภาพโดยมันจะทำการส่งสัญญาณไปยัง processes ตามชื่อที่ได้มีการระบุไว้

#### การจัดลำดับความสำคัญของ Processes ใน Linux
การจัดลำดับความสำคัญของ process ที่กำลังทำงานอยู่สามารถทำได้โดยใช้คำสั่ง `nice`  `renice` ใน Linux
คำสั่ง`nice`ใน Linux ใช้เพื่อปรับลำดับความสำคัญของ process โดยจะกำหนดลำคัญความสำคัญที่ต่ำกว่าให้กับ process เพื่อลดการใช้ทรัพยากร
คำสั่ง`renice`ใน Linux ใช้เพื่อปรับลำดับความสำคัญของ process ที่เริ่มการทำงานไปแล้ว โดยสามารรถปรับเพ่ิ่มหรือลดลำดับความสำคัญของ process ได้ขึ้นอยู่กับค่าที่ระบุ
#### การวิเคราะห์ทรัพยากรที่ใช้ใน Linux

คำสั่ง`top`ใน Linux ใช้เพื่อการแสดงข้อมูลเกี่ยวกับ process แบบ real-time ที่ทำงานอยู่บนระบบรวมไปถึงการใช้ CPU และ memory โดยจะมี interface ที่ช่วยให้ผู้ใช้ตรวจสอบและจัดการ processes ได้

  

# Service Management

# Task Scheduler

  

# สมาชิก

|รหัสนักศึกษา|ชื่อ-นามสกุล|ส่วนที่รับผิดชอบ|
|----------|---------------|-----------|
|65070110 |นาย นครินทร์ ทิพย์รัตน์| |
|65070175 |นาย ภาณุวิชญ์ คล้ายอุบล| |
|65070183 |นาย ภูวเดช อนันต์คูศรี| |
|65070204 |นาย วรพล สาดฟัก|Process Management|
|65070226 |นาย ศุภวิชญ์ ปัทมภาสสกุล|Boot Process|
|65070230 |นาย สมิทธิพงศ์ จูปรางค์| |
|65070231 |นาย สรพณ เนตรนันต์| |

  

# แหล่งอ้างอิง
### Boot Process
- https://www.scaler.com/topics/booting-process-in-linux/
- https://www.baeldung.com/linux/boot-process
- https://en.wikipedia.org/wiki/Booting_process_of_Linux
### Process Management

- https://www.scaler.com/topics/process-management-in-linux/

- https://www.geeksforgeeks.org/process-management-in-linux/