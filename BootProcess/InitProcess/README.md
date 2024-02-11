# Init Process
ในขั้น kernel stage ที่เตรียมใช้งานอุปกรณ์ ติดตั้ง root filesystem ที่ระบุโดย bootloader ให้เป็นแบบ read only และ
รัน Init (/sbin/init) ซึ่งถูกกำหนดให้เป็นกระบวนการแรกที่รันโดยระบบ(PID = 1) ข้อความจะถูกพิมพ์โดย kernel เมื่อติดตั้ง
file system และเมื่อเริ่ม Init process โดย Init

# Init System
หลังจาก kernel เสร็จสิ้นกระบวนการเริ่มต้น kernel จะส่งผ่านการควบคุมไปยังระบบ Initialization หรือ Init system ขั้นตอนสำคัญในกระบวนการบูต Linux 
Init system จะเริ่มต้น และเริ่มฟังก์ชันทั้งหมดของระบบ และ processes ที่จำเป็นสำหรับการดำเนินการระบบ
ในขั้นตอนการเริ่มของ Init จะเริ่มด้วยการตัดสินใจว่าควรจะใช้ระดับการทำงานใดเพื่อเริ่มระบบ ซึ่งจะกำหนดบริการของระบบและกระบวนการที่จะเริ่ม 
จากนั้น system services ทั้งหมดที่จำเป็นสำหรับระดับการทำงานจะถูกเตรียมใช้งาน เช่น network stack, logging และ authentication
จากนั้นสภาพแวดล้อมของ user จะถูกตั้งค่า และกระบวนการ daemon ทั้งหมดที่จำเป็นสำหรับระดับการทำงานที่เลือกจะถูกเริ่มต้น

ใน Linux จะมีระบบการเริ่มต้นหลัก 3 ระบบ ได้แก่ SysVinit, Upstart และ Systemd 
Init systems เหล่านี้ทำหน้าที่รับผิดชอบในการควบคุมการ startup และ shutdown ของระบบ

* ### SysVinit
* ### Upstart
* ### Systemd


# แหล่งอ้างอิง
- https://www.scaler.com/topics/booting-process-in-linux/
- https://en.wikipedia.org/wiki/Booting_process_of_Linux
