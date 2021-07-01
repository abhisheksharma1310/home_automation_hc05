# Control-the-Device-through-bluetooth
Home Automation using Bluetooth.
Control the Devices through Bluetooth.

Arduino Code

<pre>
<code>
int led = 3; // intialize pin 3 for led
void setup() 
{
  Serial.begin(9600); //baud rate 
  pinMode(led,OUTPUT); //set led pin as output
}

void loop()
{
  while(!Serial.available()); //it check continuously serial until it found 
  byte value = Serial.read(); //when data is found it will stored in variable 'value'
  switch(value)
  {
    case 'O':
      digitalWrite(led,HIGH); //when serial data is 'O' it will turn the On led
      Serial.print("Led is now turned On"); //it will print this message in Serial Monitor
      break;
    case 'F':
      digitalWrite(led,LOW); //when serial data is 'F' it will turn Off the led 
      Serial.print("Led is now turned Off"); //it will print this message in Serial Monitor
      break;      
  }
}
</code>
</pre>

<p>Shematic</p>

<img src = "https://github.com/abhisheksharma1310/Control-the-Device-through-bluetooth/blob/main/Schematic_bb.png">
