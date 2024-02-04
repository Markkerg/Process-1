# คำสั่ง`ps`
เป็นคำสั่งที่แสดงข้อมูลเกี่ยวกับ processes ที่กำลังทำงานอยู่ในระบบ
|อาร์กิวเมนต์|คำอธิบาย|ตัวอย่าง|
|---|-----------|-----|
|`-A` หรือ `-e`|แสดงข้อมูลเกี่ยวกับ processes ทั้งหมด|`ps -A` หรือ `ps -e`|
|`-f`|แสดงข้อมูลแบบ full-format|`ps -f`|
|`-l`|แสดงข้อมูลแบบ long format|`ps -l`|
|`-j`|แสดงข้อมูลแบบ jobs format.|`ps -j`|
|`-o`|แสดงข้อมูลแบบ User-defined format|`ps -o pid,comm`|
|`-p`|แสดงข้อมูลที่เลือกโดย PID|`ps -p 1234`|
|`-t`|แสดงข้อมูลที่เลือกโดย TTY|`ps -t pts/1`|
|`-u`|แสดงข้อมูลที่เลือกโดย effective user ID (EUID).|`ps -u root`|
|`-x`|แสดงข้อมูลโดยไม่ต้องควบคุม terminal (เหมือน daemons)|`ps -x`|
|`-C`|แสดงข้อมูลที่เลือกโดย command name|`ps -C bash`|
|`-L`|แสดงข้อมูล threads โดยอาจมีคอลัมท์ LWP and NLWP|`ps -L`|
## ตัวอย่างการนำไปใช้
- แสดง process ที่ทำงานอยู่ในปัจจุบัน
> ps
[imageps](Process-1/Assets/ps.png)
- แสดงทุก process ที่ทำงานอยู่ในระบบ
> ps -A หรือ ps -e
<img src="Process-1/Assets/ps-A.png" width="150" height="auto">
- แสดงทุก process ที่ทำงานอยู่ในระบบและแสดงแบบ full-format
> ps -ef หรือ ps -eF
<img src="Process-1/Assets/ps-ef.png" width="150" height="auto">
- แสดงข้อมูลแบบที่ผู้ใช้เป็นคนกำหนด output format เอง เช่นอยากเห็น PID, user, และคำสั่งในแต่ละ process
> ps -e -o pid,user,comm
<img src="Process-1/Assets/ps-e-o.png" width="150" height="auto">
- แสดงข้อมูลที่เลือก processes จาก PID เช่นอยากเห็นรายละเอียดของ process ที่มี PID 410 หรือแสดงแบบหลายๆ PID ได้
> ps -fp 410
<img src="Process-1/Assets/ps-fp410.png" width="150" height="auto">
> ps -fp 369,577,616 
<img src="Process-1/Assets/ps-fp369.png" width="150" height="auto">
- แสดง process แบบ tree จะเห็นการเชื่อมโยงของ process ที่ทำงานร่วมกัน
> ps -e --forest
<img src="Process-1/Assets/ps-e--forest.png" width="150" height="auto">
***
# แหล่งอ้างอิง
- https://ioflood.com/blog/ps-linux-command/
- https://www.hostpacific.com/ps-command-for-linux-process-monitoring-1/
