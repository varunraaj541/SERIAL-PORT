
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FDH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'B' 
 WAIT:JNB TI, WAIT
 CLR TI 
 END

```
### (ii) Serial Port to Transfer a Message

```
ORG 00H 
MOV DPTR, #4500H
MOV TMOD, #20H 
MOV TH1, #0FDH 
MOV SCON, #40H 
SETB TR1 
AGAIN: MOVX A,@DPTR
MOV SBUF, A
 WAIT:JNB TI, WAIT
 CLR TI 
 INC DPTR
 SJMP AGAIN
 END

```

### OUTPUT:
### (i) Serial Port Transfer a Single Character

![IMG-20251014-WA0197](https://github.com/user-attachments/assets/bb020d34-a8f5-4615-8241-256c20e57395)

### (ii) Serial Port to Transfer a Message

<img width="1919" height="1198" alt="Screenshot 2026-02-19 110446" src="https://github.com/user-attachments/assets/ce400cdf-a770-4856-acff-9f7a866bce9c" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
