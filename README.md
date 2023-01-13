# เกี่ยวกับ Statefulset_PostgreSQL_Kubernetes Project

Statefulset PostgreSQL Kubernetes Project

## การเตรียมพร้อม

 ทำการรันไฟล์ statefulset-master.yml ก่อนเพื่อสร้าง Master Pod ขึ้นมาด้วยคำสั่ง

 `kubectl apply -f statefulset-master.yml`

 จากนั้นรอให้ Master Pod มีสถานะ "Running" จึงจะสามารถรัยไฟล์ service.yml ได้

 โดยสามารถตรวจสอบสถานะได้ด้วยคำสั่ง

 `kubectl get pods`