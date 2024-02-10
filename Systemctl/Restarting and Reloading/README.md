## รีสตาร์ท Service
คำสั่งนี้หยุดบริการที่เลือกในเซสชันปัจจุบันและเริ่มต้นใหม่ทันที หากบริการที่เลือกไม่ได้ทำงาน คำสั่งนี้จะทําให้บริการทำงาน
```
systemctl restart SERVICE_NAME
```
> systemctl restart apache2

![restart](https://phoenixnap.com/kb/wp-content/uploads/2021/04/systemctl-restart-service-1.png)

## รีโหลด Service
การรีโหลดจะทำให้บริการนำเข้าการตั้งค่าใหม่โดยไม่ต้องหยุดการทำงานของบริการ
```
systemctl reload SERVICE_NAME
```
> systemctl reload apache2

![reload](https://phoenixnap.com/kb/wp-content/uploads/2021/04/systemctl-reload-service-1.png)
