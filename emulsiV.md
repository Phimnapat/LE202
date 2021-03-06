# โปรแกรม EmulsiV
การเปิดโปรแกรมนี้ขึ้นมาจะกดเข้าไปที่ riscv.org --> RISC-V Exchange --> Available Software เลื่อนลงมาหาคำว่า EmulsiV กด Working Instance 

แล้วเราจะได้หน้าตาโปรแกรมประมาณนี้
<img width="1440" alt="Screen Shot 2565-03-30 at 15 12 50" src="https://user-images.githubusercontent.com/98943436/160787306-038b542a-59a5-4d6b-ae37-8db5a9babd85.png">

โดยที่ฝั่งทางซ้ายมือคือส่วนที่เป็นหน่วยความจำ(memory)ซึ่งจะมีหน่วยความจำเยอะมาก คือส่วนตรงนี้

<img width="389" alt="Screen Shot 2565-03-30 at 15 33 19" src="https://user-images.githubusercontent.com/98943436/160788671-787512b9-0079-4da8-9ab2-0415c4c684ff.png">

ฝั่งทางขวามือก็จะเป็น resistor เก็บความจำซึ่งมีแค่เพียง 32 ตัวคือส่วนตรงนี้

<img width="137" alt="Screen Shot 2565-03-30 at 15 33 51" src="https://user-images.githubusercontent.com/98943436/160790835-45305399-dab6-400f-bc74-a1e376a99772.png">

ส่วนทางด้านล่างซ้ายมือจะเป็นส่วนของ input/output โดยเป็นตัวหนังสือคือ text I/O คือส่วนตรงนี้

<img width="413" alt="Screen Shot 2565-03-30 at 15 33 37" src="https://user-images.githubusercontent.com/98943436/160798020-228fdea2-b18f-4d28-a111-4c774d7874fe.png">

## การทำงานของโปรแกรม EmulsiV
โดยใน address ที่ 20 จะเอาไว้กำหนดค่าที่ต้องการโดยค่าที่ใส่ไปเป็นค่าของ ascii ซึ่งเราจะกำหนดค่าเป็นตัว P และ B ซึ่งมีค่าคือ 50 และ 42 ตามลำดับ

เราจะได้รูปโปรแกรมประมาณนี้ <img width="374" alt="Screen Shot 2565-03-30 at 16 26 30" src="https://user-images.githubusercontent.com/98943436/160799132-4d756af8-e189-4d0b-a756-98450e614186.png">
เมื่อเรากำหนดค่าเรียบร้อยแล้วก็จะกดปุ่ม run ที่แถบด้านบนด้านขวามือเพื่อแสดงการทำงานของโปรแกรมและจะนำคำสั่งจากกล่อง list box ทางด้านซ้ามมือเข้าไปทำงาน ซึ่งคือส้วนตรงนี้

<img width="206" alt="Screen Shot 2565-03-30 at 16 32 27" src="https://user-images.githubusercontent.com/98943436/160800208-f8640ce6-2f85-4064-855d-878256fb98e0.png">

โปรแกรมจะเริ่มรันคำสั่งที่ละบรรทัดของ list box จากคำสั่งแรกจาก list box จะถูกเข้ามาป้อนที่ BUS และนำมาแปลที่ instruction reg. ตามลูกศร ซึ่งค่าคำสั่งแรกเป็นคำสั่งบวก คือ นำ 32 บวกกับ x0 แล้วนำไปใส่ที่ x1 เมื่อเรากดรันเสร็จทางด้านตารางทางขวามือค่า x1 จะเปลี่ยนเป็น 000020 เมื่อรันเสร็จแล้วจะเริ่มรันคำสั่งของ list box ต่อไปเลย

โดยคำสั่งที่สองคือการนำคำ c0000000 ไปใส่ใน x2 แต่ใส่เพียง 20 bits แรกเท่านั้น

คำสั่งที่สามคือการนำค่าความจำของ x1 ไปใส่ใน x3

คำสั่งที่สี่คือการเช็คว่าค่าของ x3 และ x0 มีค่าเท่ากันหรือไม่

คำสั่งที่ห้าคือการนำ x3 ไปใส่ในหน่วยเก็บความจำ x2 และจะแสดงค่าในช่อง output มีค่า 50 ซึ่งก็คือ P 
<img width="398" alt="Screen Shot 2565-03-30 at 17 25 13" src="https://user-images.githubusercontent.com/98943436/160811089-3bf5176b-cff3-4c14-a66a-e82e26300599.png">

คำสั่งที่หกคือการนำ 1 ไปบวกกับ x1 ซึ่งจะได้ค่าเป็น 000021

คำสั่งที่เจ็ดคือจะทำการกระโดดไป -16 ช่อง

คำสี่งที่แปดจะหระโดดไปที่ 0 

หลังจากนั้นจะทำการกระโดดวนลูปไปเรื่อยๆจนกว่าจะมีค่าเท่ากัน และค่า output ที่ได้จะแสดงค่า PB
<img width="408" alt="Screen Shot 2565-03-30 at 17 29 01" src="https://user-images.githubusercontent.com/98943436/160811421-2347131f-3d00-469d-a76e-3caac839ddce.png">
