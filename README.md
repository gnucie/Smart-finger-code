# Smart-finger-code

```
#include <Servo.h>

Servo servo1, servo2, servo3;



int j=0;
int i=0;

 


void setup() {

  Serial.begin(9600);

  servo1.attach(3);
  servo2.attach(4);
  servo3.attach(5);
  j=servo1.read();
  for(i=j; i>=0; i--)
  {
    servo1.write(i);
    servo2.write(i);
    servo3.write(i);
    delay(15);
  }
}



void loop() {

  
  for(i=0; i<=120; i++)
  {
    servo1.write(i);
    servo2.write(i);
    servo3.write(i);
    double value1=analogRead(A0);
    double value2=analogRead(A1);
    double value3=analogRead(A2);
    double amp1 = (value1-508)*5/1.024;
    double amp2 = (value2-508)*5/1.024;
    double amp3 = (value2-508)*5/1.024;
    Serial.print("servo1 amp : ");Serial.print(amp1);
    Serial.print("\tservo2 amp : ");Serial.print(amp2);
    Serial.print("\tservo3 amp : ");Serial.println(amp3);
    
    
    delay(10);
  }
  delay(1000);
  for(i=120; i>=0; i--)
  {
    servo1.write(i);
    servo2.write(i);
    servo3.write(i);
    double value1=analogRead(A0);
    double value2=analogRead(A1);
    double value3=analogRead(A2);
    double amp1 = (value1-508)*5/1.024;
    double amp2 = (value2-508)*5/1.024;
    double amp3 = (value2-508)*5/1.024;
    Serial.print("servo1 amp : ");Serial.print(amp1);
    Serial.print("\tservo2 amp : ");Serial.print(amp2);
    Serial.print("\tservo3 amp : ");Serial.println(amp3);
    delay(10);
  }
  delay(1000);
}


```