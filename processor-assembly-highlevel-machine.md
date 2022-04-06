# High level language
High level language หรือภาษาระดับสูง เป็นภาษาที่ทำให้สามารถเขียนและอ่านโปรแกรมได้ง่ายขึ้น ตัวอย่างเช่น Fortran, Cobol, Pascal, ภาษา C ซึ่งภาษาที่กล่าวมานั้นจะสามารถทำงานได้ก็ต่อเมื่อมีการแปลงภาษาให้เป็นภาษาเครื่องก่อน สามารถแปลงโดยการใช้โปรแกรม compiler หรือ interpreter
# Processor, Microcontroller
Processor, Microcontroller คือหน่วยประมวลผลกลางหรืออุปกรณ์ควบคุมขนาดเล็กที่สามารถอ่านและแปรผลตามคำสั่งได้
# Low level language หรือภาษา Assembly
Assembly language คือภาษาในการเขียนโปรแกรมชนิดหนึ่งที่จะเข้าไปทำงานกับ processor โดยการใช้ assembly langusge ต้องผ่านการแปลภาษาโดย assembler ซึ่งจะมีความยุ่งยากในการใช้งานแต่ว่าจะได้การทำงานของโปรแกรมเร็วกว่า high level language และมีขนาดตัวโปรแกรมน้อยจึงจะใช้ภาษานี้เมื่อต้องการประหยัดเวลาการทำงานของคอมพิวเตอร์
# Machine Language
ภาษาเครื่องหรือ Machine language คือ ภาษาโปรแกรมระดับต่ำสุดเพราะว่าต้องใช้เลขฐานสองในการเก็บข้อมูล ซึ่งคอมพิวเตอร์สามารถเข้าใจไก้เลยโดยไม่ต้องมีการแปลภาษาแต่ว่าในการเขียนโปรแกรมจะยุ่งยากมากเพราะต้องแปลทุกอย่างให้เป็นเลขฐานสอง
## ความสัมพันธ์
ภาษาเครื่องหรือ Machine language จะพัฒนาไปเป็น Assembly language เพราะว่า Machine language จะมีความยุ่งยากมากเพราะต้องแปลเป็นเลขฐานสอง ซึ่ง Assembly language จะส่งผ่านข้อมูลไปที่ตัว processor แต่ว่า Assembly language จะมีการเขียนบรรทัดเยอะมากทำให้พัฒนาเป็น High level language ทำให้เขียนได้ง่ายขึ้นแต่ว่าการทำงานจะช้ากว่า Assembly language เล็กน้อยแต่การเขียนจะยุ่งยากน้อยกว่า
# godbolt.org
อย่างเช่นตัวโปรแกรม godbolt.org พอเข้าเว็บไปแล้วจะมีหน้าตาประมาณนี้

<img width="1440" alt="Screen Shot 2565-04-06 at 19 32 31" src="https://user-images.githubusercontent.com/98943436/161975275-5a560cc9-3666-4d0e-a094-538fde3d22dc.png">

จะเห็นว่าทางด้านซ้ายมือคือเป็นภาษาชั้นสูงหรือ high level language และทางด้านฝั่งขวามือจะเป็นภาษาชั้นต่ำหรือ assembly language และสามารถเลือภาษาที่ต้องการแปลได้และสามารถเลือกตัว processor ที่จะใช้ได้ด้วย

อย่างเช่นในรูป เราจะเลือกภาษาชั้นสูงคือภาษา C และตัว processor ที่เลือกแปลงเป็นภาษาชั้นต่ำคือ RISC-V rv32gc gcc 10.2.0 ซึ่งพอเราเลือกแล้วตัวโปรแกรมจะทำการแปลภาษาชั้นสูงที่เราเลือกเป็นภาษาชั้นต่ำได้ดังนี้ 
<img width="717" alt="Screen Shot 2565-04-06 at 19 39 45" src="https://user-images.githubusercontent.com/98943436/161976404-5f2e0f23-b28c-43de-9551-75d700fec8ff.png">

จากด้านฝั่ง assembly language หรือภาษาชั้นต่ำจะสามารถแปลงเป็นภาษาเครื่องได้อีกโดยจะคลิกไปที่ช่อง output และเลือก compile to binary ตามรูป
<img width="242" alt="Screen Shot 2565-04-06 at 19 45 57" src="https://user-images.githubusercontent.com/98943436/161977603-eb4eb8cf-4b74-448f-8629-3291febcd711.png">

เราจะได้ภาษาเครื่องตามในรูปนี้

<img width="717" alt="Screen Shot 2565-04-06 at 19 43 58" src="https://user-images.githubusercontent.com/98943436/161977212-eb2b5ed4-d51e-4f66-8ff5-5aa5d9b284bc.png">
