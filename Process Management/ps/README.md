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

![ps.png](../../Assets/ps.png)
- แสดงทุก process ที่ทำงานอยู่ในระบบ
> ps -A หรือ ps -e

![ps-A.png](../../Assets/ps-A.png)
- แสดงทุก process ที่ทำงานอยู่ในระบบและแสดงแบบ full-format
> ps -ef หรือ ps -eF

![ps-ef.png](../../Assets/ps-ef.png)
- แสดงข้อมูลแบบที่ผู้ใช้เป็นคนกำหนด output format เอง เช่นอยากเห็น PID, user, และคำสั่งในแต่ละ process
> ps -e -o pid,user,comm

![ps-e-o.png](../../Assets/ps-e-o.png)
- แสดงข้อมูลที่เลือก processes จาก PID เช่นอยากเห็นรายละเอียดของ process ที่มี PID 410 หรือแสดงแบบหลายๆ PID ได้
> ps -fp 410

![ps-fp410.png](../../Assets/ps-fp410.png)
> ps -fp 369,577,616

![ps-fp369.png](../../Assets/ps-fp369.png)
- แสดง process แบบ tree จะเห็นการเชื่อมโยงของ process ที่ทำงานร่วมกัน
> ps -e --forest

![ps-e--forest.png](../../Assets/ps-e--forest.png)
***
# แหล่งอ้างอิง
- https://ioflood.com/blog/ps-linux-command/
- https://www.hostpacific.com/ps-command-for-linux-process-monitoring-1/