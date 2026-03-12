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

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE

ORG 1000H

START:
    MOV SI, 1200H      ; Point to first number

    MOV AX, [SI]       ; Load first 16-bit number
    MOV BX, [SI+02H]   ; Load second 16-bit number

    MOV CL, 00H        ; Clear carry flag storage

    ADD AX, BX         ; AX = AX + BX
    JNC L1             ; Jump if no carry
    INC CL             ; Store carry = 1

L1:
    MOV [SI+04H], AX   ; Store sum
    MOV [SI+06H], CL   ; Store carry

    MOV AH, 4CH        ; Exit to DOS
    INT 21H

CODE ENDS
END START
```
#### Output Table

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/577a7b9c-574f-4ae3-938c-316af8dea721" />


#### Manual Calculations
<img width="822" height="795" alt="image" src="https://github.com/user-attachments/assets/5cc997d0-05f8-4daf-a962-224637702411" />

## OUTPUT IMAGE FROM MASM SOFTWARE

<img width="638" height="444" alt="image" src="https://github.com/user-attachments/assets/f1cdc964-d3a4-4a34-b0ea-273bec0547bf" />


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

```asm
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
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/1c4f64ef-1341-47b3-b380-2249e2060ba5" />



#### Manual Calculations
<img width="822" height="795" alt="image" src="https://github.com/user-attachments/assets/19563739-5913-4f62-bb74-161abc900193" />


## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="642" height="434" alt="image" src="https://github.com/user-attachments/assets/fb4e4fc3-03e6-4e04-80d7-09a5ffc4810b" />

## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
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

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/951c8a74-f6c1-48ec-8bfe-273a66524fa5" />

#### Manual Calculations

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/0d051be8-387d-41b8-a2ee-ed47bab22fde" />

## OUTPUT SCREEN FROM MASM SOFTWARE
![WhatsApp Image 2026-02-13 at 10 17 37 AM](https://github.com/user-attachments/assets/9b01b930-0e5c-47b4-9329-08b4fa44b98a)


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
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
<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/3d9b7f94-5a5e-42c5-9b1f-4238fdeac79f" />



#### Manual Calculations
<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/d5142e1c-1962-4ae4-afe7-992daf224fde" />

## OUTPUT FROM MASM SOFTWARE
<img width="696" height="471" alt="image" src="https://github.com/user-attachments/assets/a72cb47e-30b5-4af4-b943-f382868cb183" />



## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

