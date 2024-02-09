# Crontab Commands

|Commands|Meaning|
|------------------------|------------------------------------------------------------|
|`crontab [filename]`|การนำเอาคำสั่ง crontab เข้ามาจาก ไฟล์อื่น|
|`crontab -e`|แก้ไข crontab ปัจจุบัน|
|`crontab -l`|ดูคำสั่ง crontab ทั้งหมดที่มีอยู่|
|`crontab -r`|ลบคำสั่ง crontab ที่มีทั้งหมด|
|`crontab -u [user_name]`|คำสั่งของผู้ดูแลระบบเท่านั้น เพื่อใช้ดู แก้ไข ลบ crontab ของ user แต่ละคน|

# Cron job syntax

![My Remote Image](https://vk9-sec.com/wp-content/uploads/2022/04/how-to-set-up-a-cron-job-in-linux-nil-tutorials.jpeg)

|*|ค่าตัวเลข|คำอธิบาย|
|------------|----|----------------------------------|
|นาที|0-59|คำสั่งเริ่มการทำงานตามเวลานาทีที่กำหนด|
|ชั่วโมง|0-23|คำสั่งเริ่มการทำงานตามวลาชั่วโมงที่กำหนด|
|วันที่ของเดือน|1-31|คำสั่งเริ่มการทำงานตามวันที่ที่กำหนด|
|เดือน|1-12|คำสั่งเริ่มการทำงานตามเดือนที่กำหนด|
|วันที่ของสัปดาห์|0-6|คำสั่งเริ่มการทำงานตามวันของสัปดาห์ที่กำหนด|

### Examples

|คำสั่ง|ความหมาย|
|----------------------------|----------------------------------------------|
|`5 0 * 8 * /path/to/script`|เริ่มทำงานเวลา 00:05 ในเดือน 8(สิงหาคม)|
|`5 4 * * 6 /path/to/script`|เริ่มทำงานเวลา 04:05 ในวันที่ 6 ของอาทิตย์(วันสาร์)|
|`0 22 * * 1-5 /path/to/script`|เริ่มทำงานเวลา 22:00 ในทุกๆที่ 1-5 (วันจันทร์-วันศุกร์)|

### แหล่งอ้างอิง
- https://www.freecodecamp.org/news/cron-jobs-in-linux/
- https://phoenixnap.com/kb/set-up-cron-job-linux#basic-crontab-syntax
- https://vk9-sec.com/exploiting-the-cron-jobs-misconfigurations-privilege-escalation/
