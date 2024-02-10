## เปิดใช้งาน Service
กำหนดค่าให้บริการเริ่มต้นโดยอัตโนมัติ ทุกครั้งที่ระบบเปิดใหม่
```
systemctl enable name.service
```
> systemctl enable ssh

![enable]()

## ปิดใช้งาน Service
เปิดใช้งานบริการ ป้องกันไม่ให้บริการเริ่มต้นโดยอัตโนมัติทุกครั้งที่ระบบเปิดใหม่
```
systemctl disable name.service
```
> systemctl disable ssh

![disable]()
