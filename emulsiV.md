# หลักการทำงานของโปรแกรม emulsiV
การเปิดโปรแกรมนี้ขึ้นมาจะกดเข้าไปที่ riscv.org --> RISC-V Exchange --> Available Software เลื่อนลงมาหาคำว่า EmulsiV กด Working Instance 

แล้วเราจะได้หน้าตาโปรแกรมประมาณนี้
<img width="1440" alt="Screen Shot 2565-03-30 at 15 12 50" src="https://user-images.githubusercontent.com/98943436/160787306-038b542a-59a5-4d6b-ae37-8db5a9babd85.png">

โดยที่ฝั่งทางซ้ายมือคือส่วนที่เป็นหน่วยความจำ(memory)ซึ่งจะมีหน่วยความจำเยอะมาก คือส่วนตรงนี้

<img width="389" alt="Screen Shot 2565-03-30 at 15 33 19" src="https://user-images.githubusercontent.com/98943436/160788671-787512b9-0079-4da8-9ab2-0415c4c684ff.png">

ฝั่งทางขวามือก็จะเป็น resistor เก็บความจำซึ่งมีแค่เพียง 32 ตัวคือส่วนตรงนี้

<img width="137" alt="Screen Shot 2565-03-30 at 15 33 51" src="https://user-images.githubusercontent.com/98943436/160790835-45305399-dab6-400f-bc74-a1e376a99772.png">

ส่วนทางด้านล่างซ้ายมือจะเป็นส่วนของ input/output โดยเป็นตัวหนังสือคือ text I/O คือส่วนตรงนี้

<img width="413" alt="Screen Shot 2565-03-30 at 15 33 37" src="https://user-images.githubusercontent.com/98943436/160798020-228fdea2-b18f-4d28-a111-4c774d7874fe.png">

โดยใน address ที่ 20 จะเอาไว้กำหนดค่าที่ต้องการโดยค่าที่ใส่ไปเป็นค่าของ ascii ซึ่งเราจะกำหนดค่าเป็นตัว P และ B ซึ่งมีค่าคือ 50 และ 42 ตามลำดับ

เราจะได้รูปโปรแกรมประมาณนี้ <img width="374" alt="Screen Shot 2565-03-30 at 16 26 30" src="https://user-images.githubusercontent.com/98943436/160799132-4d756af8-e189-4d0b-a756-98450e614186.png">
