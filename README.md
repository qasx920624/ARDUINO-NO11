# ARDUINO-NO11
這次的題目是<p>
操控風扇(馬達)的轉速<p>
初始轉速以及最低轉速為80<p>
最高轉速為255<p>
並可用按鈕控制<p>
左方按鈕按一次轉速加35<p>
右方按鈕按一次則減慢35<p>
並且可以用序列阜監控視窗監控轉速<p>
程式如下<p>
c++```
  int kk;
void setup() {
  // put your setup code here, to run once:
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(2,INPUT);
  digitalWrite(2,1);
  Serial.begin(9600); 
  kk =80;
}

void motor(int xx)
{
   analogWrite(5,xx);
   analogWrite(6,0);
}
void loop() {
  // put your main code here, to run repeatedly:
 // digitalWrite(5,1);
 if(kk>=255)kk=255;
 if (kk<=80) kk=80;
  while(digitalRead(2)==0)
  {
    while(digitalRead(2)==0) delay(20);
    kk = kk + 35;
    
    
  }
  while(digitalRead(3)==0)
  {
    while(digitalRead(3)==0) delay(20);
    kk = kk - 35;
    
    
  }
  motor(kk);

Serial.println(kk);
}
```
