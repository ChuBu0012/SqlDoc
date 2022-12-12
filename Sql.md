_DATABASE จำลอง id | fname | lname | address | contact | salary_
<!-- สร้างตารางฐานข้อมูล -->

CREATE TABLE "ชื่อฐานข้อมูล" (
    "ชื่อcol" ชนิดข้อมูล,
    "ชื่อcol" ชนิดข้อมูล NOT NULL, //ห้ามเป็นค่าว่าง
    "ชื่อcol" ชนิดข้อมูล UNIQUE, //ข้อมูลห้ามซ้ำ
    "ชื่อcol" ชนิดข้อมูล CHECK(ชื่อcolนี้ >= 100), //กำหนดเงื่อนไข 
    "ชื่อcol" ชนิดข้อมูล DEFAULT 'ค่าเริ่มต้น', //ในกรณีไม่ได้ระบุค่า
    PRIMARY KEY("ชื่อcol" AUTOINCREMENT) // กำหนด col หนึ่งให้เป็น PRIMARY KEY
// AUTOINCREMENT คือ ตัวเลขที่จะสามารถเพิ่มค่าขึ้นโดยอัตโนมัติในทุกครั้งที่มีการ Insert ข้อมูล (ชนิดข้อมูลต้องเป็น INTEGER) 
)

ชนิดข้อมูล : 
    - INTEGER ตัวเลขจำนวนเต็ม
    - TEXT ข้อความ
    - REAL จำนวนทศนิยม 7 ตำแหน่ง
    - NUMERIC ตัวเลข
<!-- บันทึกข้อมูลลงในตาราง (INSERT) -->

**(แบบ_ระบุ_คอลัมน์)**
INSERT INTO databaseName (fname,lname,address,contact,salary)
VALUE ("บีเวอร์","เดฟ","กรุงเทพมหานคร","095-xxx-xxxx",30000)

**(แบบ_ระบุบาง_คอลัมน์)**
INSERT INTO databaseName (fname,lname,address,salary)
VALUE ("บีเวอร์","เดฟ","กรุงเทพมหานคร",30000)

**(แบบ_ไม่ระบุ_คอลัมน์)**
INSERT INTO databaseName
//ใส่ค่าตามตำแหน่ง column
VALUE (NULL,"บีเวอร์","เดฟ","กรุงเทพมหานคร",NULL,30000)

**(บันทึกข้อมูลหลายรายการ)**
INSERT INTO databaseName (fname,lname,address,contact,salary)
VALUE ("บีเวอร์","เดฟ","กรุงเทพมหานคร","095-xxx-xxxx",10000),
("จุ้บบุ","เลิฟ","พะเยา","067-xxx-xxxx",20000),
("สม","ชาย","พะเยา","064-xxx-xxxx",30000)

<!-- สอบถามข้อมูล (SELECT) -->

**(สอบถามข้อมูลทุกคอลัมน์)**
SELECT *
FROM databaseName

**(สอบถามข้อมูล แบบระบุคอลัมน์)**
SELECT lname,fname,salary,contact
FROM databaseName

**(เปลี่ยนชื่อคอลัมน์ ในการแสดงผล)**
SELECT fname AS "ชื่อจริง", lname AS "นามสกุล"
FROM databaseName

**แสดงข้อมูลที่ไม่ซ้ำ**
SELECT DISTINCT fname AS "ชื่อจริง"
FROM databaseName

--มักใช้ร่วมกับ COUNT and GROUP BY--

SELECT DISTINCT 
fname AS "ชื่อจริง"
COUNT(*) AS "จำนวน" //นับข้อมูล (ที่ไหน?)
FROM databaseName
GROUP BY fname //นับข้อมูลที่ fname





