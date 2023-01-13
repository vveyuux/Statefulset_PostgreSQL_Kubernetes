# เกี่ยวกับ Statefulset_PostgreSQL_Kubernetes Project

**Statefulset PostgreSQL Kubernetes Project**

## การเตรียมพร้อม

 ทำการรันไฟล์ **statefulset-master.yml** ก่อนเพื่อสร้าง **Master Pod** ขึ้นมาด้วยคำสั่ง

 `kubectl apply -f statefulset-master.yml`

 จากนั้นรอให้ **Master Pod** มีสถานะ **"Running"** จึงจะสามารถรัยไฟล์ **service.yml** ได้

 โดยสามารถตรวจสอบสถานะได้ด้วยคำสั่ง

 `kubectl get pods`
 
 ถ้า **Master Pod** หรือ **postgres-0** มีสถานะ **"Running"** แล้วให้ทำการรันไฟล์ **service.yml** ได้ด้วยคำสั่ง
 
 `kubectl apply -f service.yml`

 เมื่อทำการรันไฟล์ **service.yml** แล้วให้ทำการรันไฟล์ **statefulset-replica.yml** เพื่อทำการสร้าง **Replica Pod** ขึ้นมาด้วยคำสั่ง

 `kubectl apply -f statefulset-replica.yml
 
 จากนั้นรอให้ **Replica Pod** มีสถานะ **"Running"**

## การเพิ่ม Replica Pod

การเพิ่ม Replica Pod สามารถเพิ่มได้ด้วยการเข้าไปแก้ไขไฟล์ที่ส่วนของ **"replica"** ในไฟล์ **statefulset-replica.yml** ซึ่งโดยปกติแล้วจะถูกตั้งค่าไว้ที่ 2 ดังนี้

`replica: 2`

โดยสามารถเปลี่ยนจำนวนได้ตรงเลขของ **replica**