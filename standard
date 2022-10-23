#include <Wire.h> //Library which allows I2C communication.
#include <Adafruit_PWMServoDriver.h> //This library must be downloaded to run the code.
 
Adafruit_PWMServoDriver pwm = Adafruit_PWMServoDriver();//Instantiating objects with the Adafruit_PWMServoDriver class.
 
#define MIN_PULSE_WIDTH 650   //These are the minimum and maximum wavelength values which serve MG 995.
#define MAX_PULSE_WIDTH 2350
#define DEFAULT_PULSE_WIDTH 1500
#define FREQUENCY 60
 
int pulseWidth(int angle){ //This function calculates servo's motion angle.
int pulse_wide, analog_value;
pulse_wide = map(angle, 0, 180, MIN_PULSE_WIDTH, MAX_PULSE_WIDTH); //This function get angle from 0 to 180 degrees and map from length minimum value to maximum. 
analog_value = int(float(pulse_wide) / 1000000 * FREQUENCY * 4096);
Serial.println(analog_value);
return analog_value; //The value this function returns.
}
  
void setup(){
Serial.begin(9600);
//Serial.println("16 channel Servo test!");
pwm.begin();  //Initialize the library and send PWM signals.
pwm.setPWMFreq(FREQUENCY); //Servo's update frequency at 60 Hertz.
pwm.setPWM(0,0,pulseWidth(0)); //base_servo1 - left right
pwm.setPWM(1,0,pulseWidth(0)); //joint2_servo2 - up down
pwm.setPWM(2,0,pulseWidth(0)); ////joint3_servo3 up down
pwm.setPWM(3,0,pulseWidth(0)); ////joint4_servo4 up down
pwm.setPWM(4,0,pulseWidth(0)); //joint5_servo5 rotate 
pwm.setPWM(5,0,pulseWidth(0)); //joint6_servo6 open close claw
}
 
void loop(){ 
/*
insert code here
*/
}
 
//TESTING THE ARM.
//pwm.setPWM(5,0,pulseWidth(0)); //Open claw.
//pwm.setPWM(5,0,pulseWidth(120)); //Close claw.
//pwm.setPWM(4, 0, pulseWidth(90)); //Moving claw's position.
 
//pwm.setPWM(3,0,pulseWidth(20)); //Low number raise the hand.
//pwm.setPWM(3,0,pulseWidth(0)); //High number put down the hand.
 
//pwm.setPWM(2, 0, pulseWidth(180));//High number put down the elbow.
//pwm.setPWM(2, 0, pulseWidth(70));
