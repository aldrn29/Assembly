## System calls

#### 방법
1. 시스템 호출 코드를 레지스터 $v0에 로드한다.
2. argument를 레지스터 $a0~$a3에 로드한다. 
3. 'syscall'과 함께 SPIM 명령어를 호출한다.
4. 이후, 레지스터 $v0에 리턴값이 있다.  

|Cord|기능|
|--|--|
|1|int형 출력|
|2|float형 출력|
|3|double형 출력|
|4|string형 출력|
|5|int형 읽기|
|6|float형 읽기|
|7|double형 읽기|
|8|string형 읽기|
|9|sbrk|
|10|끝내기|   

## MIPS 명령어
|카테고리|명령어|예시|뜻|
|--|--|--|--|
|Data transfer|lw|lw A, B| A <- B
||sw|sw A, B| A -> B
||li|li A, 10| A <- 10 (immediate)
||la|la A, B| A <- B (B's Address)
||move|move A,B| A <- B
||movn|movn A, B, C| if C != 0 then A <- B
|Arithmetic|add|add A, B, C| A = B + C
||sub|sub A, B, C| A = B - C
||addi|addi A, B, 10| A = B + 10 (immediate)
||addu|addu A, B, C| A = B + C (unsigned)
||subu|subu A, B, C| A = B - C (unsigned)
||addiu|addiu A, B, 10| A = B + 10 (immediate, unsigned)
||mult|mult A, B| Hi, Lo = A * B 
||multu|multu A, B| Hi, Lo = A * B (unsigned)
||div|div A, B| Lo = A / B, Hi = A % B  
||divu|divu A, B| Lo = A / B, Hi = A % B (unsigened)
||mfhi|mfhi A| A = Hi
||mflo|mflo A| A = Lo
|Logical|and|and A, B, C| A = B & C
||or|or A, B, C| A = B l C
||andi|andi A, B, 10| A = B & 10 (immediate)
||ori|ori A, B, 10| A = B l 10 (immediate)
||sll|sll A, B, 10| A = B << 10
||srl|srl A, B, 10| A = B >> 10
|Conditional Branch|beq|beq A, B, L| if (A==B) then L로 점프
||bne|ben A, B, L| if (A!=B) then L로 점프
||beqz|beqz R, L| if (R==0) then L로 점프
||bnez|benz R, L| if (R!=0) then L로 점프
||bal|bal function|함수 호출 = jalr
||slt|slt rd, rs, rt| rd <- (rs < rt)? 1:0
||slti||
||sltu||
||sltiu||
|Unconditional jump|j||
||jr||
||jal|jal A| 다음 명령어의 주소를 $ra에 저장하고 A로 점프
