# Quiz-7
Connect two (2) active high push button to PORTB. Connect two (2) active low LEDs on PORTD. If the first push button is pressed, the first LED on PORTD should light up. If the second button is pressed, the second LED should light up. Other than that, all LEDs should turn off. 
#include<pl8f4550.inc>

        org 0x00
	goto start
	org 0x08
	retfie
	org 0x18
        retfie
          
start  clrf TRISD,A
       setf TRISB,A
       setf PORTD,A
       
check  btfsc  PORTB,0,A
       bcf    PORTD,0,A
       btfsc  PORTB,1,A
       bcf    PORTD,1,A
       goto   check
       
       end
        
