## แสดงรายการ Service
ใช้คำสั่งต่อไปนี้
```
systemctl list-units --type=service
```
![list](https://www.tecmint.com/wp-content/uploads/2019/08/List-All-Services-Under-Systemd.png)

## แสดงรายการ Service ที่มีสถานะที่กําหนด
ใช้คำสั่งต่อไปนี้
```
systemctl list-units --type=service --state=STATE
```

> systemctl list-units --type=service --state=active

![active](https://www.tecmint.com/wp-content/uploads/2019/08/List-All-Active-Running-Services-in-Systemd.png)

> systemctl list-units --type=service --state=running

![running](https://www.tecmint.com/wp-content/uploads/2019/08/List-Running-Services-in-Systemd.png)

## หน่วยและสถานะของ systemd:

- **Unit (หน่วย):** หน่วยสามารถเป็นบริการ, โซเก็ต, อุปกรณ์, หรือตัวแทนอื่นๆ

- **Load (โหลด):** แสดงว่าหน่วยได้รับการโหลดหรือไม่. หน่วยสามารถถูกโหลดแต่ไม่จำเป็นต้องทำงาน

- **Active (ทำงาน):** แสดงว่าหน่วยทำงานอย่างมีประสิทธิภาพ หรือว่าพบปัญหาและอยู่ในสถานะที่ล้มเหลวหรือไม่ทำงาน

- **SUB (รายละเอียดย่อย):** ให้ข้อมูลเพิ่มเติมเกี่ยวกับสถานะที่เฉพาะเจาะจงของหน่วย. อาจแสดงว่าบริการกำลังทำงาน (running), หยุด (exited), หรือพบปัญหา (failed)

- **Description (คำอธิบาย):** ช่วยให้ผู้ใช้ระบุและเข้าใจวัตถุประสงค์ของหน่วย
