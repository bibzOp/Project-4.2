# Project-4.2
Fill.Asm

(RESTART)
@SCREEN
D=A
@0
M=D	//PUT SCREEN START LOCATION IN RAM0

///////////////////////////
(KBDCHECK)

@KBD
D=M
@BLACK
D;JGT	//JUMP IF ANY KBD KEYS ARE PRESSED
@WHITE
D;JEQ	//ELSE JUMP TO WHITEN

@KBDCHECK
0;JMP
///////////////////////////
(BLACK)
@1
M=-1	//WHAT TO FILL SCREEN WITH (-1=11111111111111)
@CHANGE
0;JMP

(WHITE)
@1
M=0	//WHAT TO FILL SCREEN WITH
@CHANGE
0;JMP
//////////////////////////
(CHANGE)
@1	//CHECK WHAT TO FILL SCREEN WITH
D=M	//D CONTAINS BLACK OR WHITE

@0
A=M	//GET ADRESS OF SCREEN PIXEL TO FILL
M=D	//FILL IT

@0
D=M+1	//INC TO NEXT PIXEL
@KBD
D=A-D	//KBD-SCREEN=A

@0
M=M+1	//INC TO NEXT PIXEL
A=M

@CHANGE
D;JGT	//IF A=0 EXIT AS THE WHOLE SCREEN IS BLACK
/////////////////////////
@RESTART
0;JMP

![image](https://github.com/user-attachments/assets/af73b740-3370-4cf3-a917-2ea2c5c0ff93)


![image](https://github.com/user-attachments/assets/a0ba9273-977a-4b76-9f17-2b3ab28c20ab)


![image](https://github.com/user-attachments/assets/e8293d9f-63c7-413d-aaf7-84bc9f47b967)


![image](https://github.com/user-attachments/assets/b6e5bf76-5d60-4e6b-a49b-de8b8059fa6c)


![image](https://github.com/user-attachments/assets/6027f777-421d-48f7-b740-dfd721ddac85)
