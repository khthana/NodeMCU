# NodeMCU

Repository นี้ใช้เก็บ Source Code ของโปรแกรมที่พัฒนาโดยใช้ NodeMCU (ไม่ได้เขียนเองหมดหรอก)

1. Blink : โปรแกรม Blink ซึ่งเป็นโปรแกรมพิมพ์นิยม โดยโปรแกรมนี้จะสั่งให้ไฟบนบอร์ด NodeMCU กระพริบ<br>
   https://github.com/khthana/NodeMCU/blob/master/1.0_8266_1.0_Blink.ino

2. Push Button : โปรแกรมรับ Input ผ่าน Switch โดยโปรแกรมนี้จะต้องต่อ Push Button Switch กับขา D8 ของ NodeMCU ในรูปแบบ D10 -> SW -> GND (โดยไม่ต้องต่อ R Pull Up เนื่องจากใช้ Input Pullup ของบอร์ด) แต่ถ้าไม่อยากต่อ Switch ภายนอก สามารถใช้ Switch ปุ่ม Flash ได้ โดยแก้ไขโปรแกรมจาก D8 เป็น เป็น D1 และ Mapping กับขา 0 ของ ESP8266<br>
   https://github.com/khthana/NodeMCU/blob/master/2.0_8266_Switch_Input.ino
   
3. Interrupt : โปรแกรมรับ Input แบบใช้ Interrupt โดยโปรแกรมนี้จะใช้สวิตซ์บนบอร์ดซึ่งปกติเป็นสวิตซ์ที่ใช้ในการกดเพื่อ Flash โปรแกรม แต่ครั้งนี้จะใช้เป็นสวิตซ์ที่กดเพื่อให้เกิด Interrupt โดยในโปรแกรมจะสั่งให้ LED บนบอร์ดกระพริบ โดยการตรวจสอบ Interrupt จะใช้แบบ Change คือเปลี่ยน Level <br>
   https://github.com/khthana/NodeMCU/blob/master/3%2C0_8266_Switch_Interrupt.ino
   
4. ADC : โปรแกรมอ่านค่าจาก Analog Pin โดย ESP8266 จะให้ช่องทางการอ่านค่า Analog มาเพียงช่องทางเดียว (ต่อที่ขา A0) โดยจะอ่านค่าได้ตั้งแต่ 0-1.0 V ซึ่งน้อยมาก ดังนั้นผู้ผลิต NodeMCU จึงได้ทำวงจรแบ่งแรงดัน ทำให้สามารถรับแรงดันที่ขา A0 ได้ถึง 3.3 V ทั้งนี้ก็เพื่อไม่ให้เราต้องทำวงจรแบ่งแรงดันเอง โปรแกรมนี้จะเป็นโปรแกรมง่ายๆ ที่อ่านค่าและแปลงเป็น V ให้เท่านั้น <br>
    https://github.com/khthana/NodeMCU/blob/master/4.0_8266_ADC.ino
    
5. PWM : โปรแกรมแสดงการทำงานของ PWM ซึ่งจะเป็นการสร้างคลื่นสัญญาณ 4 เหลี่ยม ออกมาที่ขา โดยในโปรแกรมจะให้ออกมาที่ขา D0 ซึ่งต่อกับ LED ซึ่งจะเป็นผลให้ LED ได้รับค่าพลังงานเปลี่ยนไป ในการใช้งาน PWM สามารถควบคุมได้ 2 แบบ คือ ควบคุม Duty Cycle และ ควบคุมความถี่ สำหรับในโปรแกรม จะให้ค่า Duty Cycle คงที่ประมาณ 50 เปอร์เซนต์ และเปลี่ยนค่าความถี่ <br>
    https://github.com/khthana/NodeMCU/blob/master/5.0_8266_5.0_PWM.ino

6. DHT22 : โปรแกรมอ่านข้อมูลจาก DHT22 Sensor ซึ่งเป็นเซ็นเซอร์อ่านค่าอุณหภูมิกับความชื้นสัมพัทธ์ (จะใช้ DHT11 ก็ได้) โดย DHT22 จะมี 2 ขา คือ ขา Vcc Gnd และ Data โดยต่อขา Data เข้ากับขา D4 ของ NodeMCU<br>
   https://github.com/khthana/NodeMCU/blob/master/6.0_8266_DHT22.ino
    
    


