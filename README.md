# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program
```
CODE SEGMENT
ASSUME CS:CODE, DS:CODE

ORG 1000H

START:
    MOV AX, CODE
    MOV DS, AX

    MOV SI,2000H
    MOV DX,0000H

    MOV AX,[SI]
    MOV BX,[SI+02H]

    ADD AX,BX

    MOV [SI+04H],AX
    MOV [SI+06H],DX

    MOV AH,4CH
    INT 21H

CODE ENDS
END START
```



#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      1200 : 12          |        1204 : 24         |
|      1201 : 34          |        1205 : 68         |  
|      1202 : 12          |        1206 : 00         |
|      1203 : 34          |                          |  

#### Manual Calculations

 ![WhatsApp Image 2026-02-06 at 8 06 01 PM](https://github.com/user-attachments/assets/7afafc92-65e5-472b-b5fc-db361185480c)
---


## OUTPUT IMAGE FROM MASM SOFTWARE
![WhatsApp Image 2026-02-13 at 10 14 37 AM](https://github.com/user-attachments/assets/a3dcdf18-bd7b-407a-b50f-ec847bb978ee)



## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```
CODE SEGMENT
ASSUME CS:CODE, DS:CODE

ORG 1000H

START:
    MOV AX, CODE
    MOV DS, AX

    MOV SI,2000H
    MOV DX,0000H

    MOV AX,[SI]
    MOV BX,[SI+02H]

    SUB AX,BX

    MOV [SI+04H],AX
    MOV [SI+06H],DX

    MOV AH,4CH
    INT 21H

CODE ENDS
END START
```




#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|  1200:12                | 1204:00                  |
|  1201:34                | 1205 : 00                |
|  1202:12                |                          |
|1203:34                  |                          |

#### Manual Calculations

 ![WhatsApp Image 2026-02-06 at 8 06 33 PM](https://github.com/user-attachments/assets/72667867-8f3b-4401-add4-b2001f068213)
---


## OUTPUT SCREEN FROM MASM SOFTWARE

![WhatsApp Image 2026-02-13 at 10 15 23 AM](https://github.com/user-attachments/assets/42d2e926-bb8c-4384-8bb1-71982c9d0091)

## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />

#### Program
```
CODE SEGMENT
ASSUME CS:CODE, DS:CODE

ORG 1000H

START:
    MOV AX, CODE
    MOV DS, AX

    MOV SI,2000H
    MOV DX,0000H

    MOV AX,[SI]
    MOV BX,[SI+02H]

    MUL BX

    MOV [SI+04H],AX
    MOV [SI+06H],DX

    MOV AH,4CH
    INT 21H

CODE ENDS
END START

```
#### Output Table

 | MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      1200 : 12          |        1204 : 90         |
|      1201 : 34          |        1205 : 5A         |  
|      1202 : 12          |        1206 : 4B         |
|      1203 : 34          |        1207 : 01         | 

#### Manual Calculations

 ![WhatsApp Image 2026-02-06 at 8 07 25 PM](https://github.com/user-attachments/assets/d2864d03-321a-45cf-ae69-3a9207d78766)

---


## OUTPUT SCREEN FROM MASM SOFTWARE
![WhatsApp Image 2026-02-13 at 10 20 57 AM](https://github.com/user-attachments/assets/f5adfb34-94fe-41fe-b235-ff4df65f86f3)


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```
CODE SEGMENT
ASSUME CS:CODE, DS:CODE

ORG 1000H

START:
    MOV AX, CODE
    MOV DS, AX

    MOV SI,2000H
    MOV DX,0000H        ; IMPORTANT: clear DX before DIV

    MOV AX,[SI]         ; Dividend (16-bit)
    MOV BX,[SI+02H]     ; Divisor (16-bit)

    DIV BX              ; DX:AX / BX
                        ; Quotient -> AX
                        ; Remainder -> DX

    MOV [SI+04H],AX     ; Store quotient
    MOV [SI+06H],DX     ; Store remainder

    INT 3               ; <-- stop here for DEBUG

CODE ENDS
END START
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      1200 : 12          |        1204 : 01         |
|      1201 : 34          |        1205 : 00         |  
|      1202 : 12          |        1206 : 00         |
|      1203 : 34          |        1207 : 00         | 

#### Manual Calculations

 ![WhatsApp Image 2026-02-06 at 8 07 25 PM (1)](https://github.com/user-attachments/assets/ce2f426f-5c21-4e66-a1b3-b168d73f19fd)
---
## OUTPUT FROM MASM SOFTWARE
![WhatsApp Image 2026-02-13 at 10 20 57 AM](https://github.com/user-attachments/assets/a1484423-c1b4-441c-a7a1-c909459f6d86)




## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

