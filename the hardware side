double analogVotage;  //模拟电压值
double light;          //温度
unsigned int dutyCycle;  //占空比
unsigned int lightMin = 90;  //零速温度，设为串口观察到的环境光照
void setup() {
  Serial.begin(115200);      //设置串口波特率
  analogReference(INTERNAL);  //调用板载1.1V基准源
}
void loop() {
  analogVotage = 1.1*(float)analogRead(A3)/1024;   //把ADC读取值换算成电压
  light= 100*analogVotage;      //电压换算成温度
  if (light >lightMin){
      dutyCycle = 100;
      }

  else {
      dutyCycle = 0    ;                              ;
      }
  analogWrite(10,dutyCycle);  //产生PWM
  Serial.print("light: "); Serial.print(light);
  Serial.print(" Degrees    Duty cycle: ");
  Serial.println(dutyCycle);
  delay(100);    //等待0.1秒，控制刷新速度
}

