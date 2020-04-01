## MIPS?

#### MIPS?

MIPS(Microprocessor without Interlocked Pipeline Stages)란 MIPS Technologies에서 개발한 __RISC__ 기반의 명령어 집합 체계.

``` 
CISC vs RISC    
CISC(COMPLEX INSTRUCTION SET COMPUTER): 연산에 처리되는 복잡한 명령어들을 수백 개 이상 탑재하고 있는 프로세서이다.
CISC 아키텍처는 MCU의 성능을 향상시키기 위해 복합 명령어를 이용하는 것이 특징이다.

RISC(REDUCED INSTRUCTION SET COMPUTER): 하나의 명령어 실행으로 간단한 프로세스들을 매우 신속하게 수행한다.
RISC 아키텍처는 다수의 축소 명령어들을 신속하게 실행하여 전반적인 MCU 성능을 향상시키는 것이 특징이다.
```

| 구분 | CISC | RISC |
|------|------|------|
|명령어 형식|가변|고정|
|명령어 종류|많음|적음|
|명령어 길이|가변|고정|
|적재/저장 구조|미사용|사용|
|주소지정방식|복잡하고 다수|단순하고 소수|
|회로 구성|복잡|단순|
|장점|호환성 양호, 코드밀도 양호|구현용이, 파이프라이닝에 효율적 적용|
|예|Intel x86, DEC VAX 11/780|MIPS, ARM, PowerPC|

#### MIPS의 명령어 체계

3가지 종류의 명령어로 구성되어 있다.

- R type: c = a + b와 같은 연산을 할 때, 2개의 레지스터 값을 이용하여 연산을 한 다음, 다른 레지스터 하나에 연산한 값을 기록한다. 
이 때 연산을 하는데 사용되는 레지스터는 각각 rs(register source), rt(register target)이며, 
연산을 한 값을 rd(register direction)에 저장하게 된다.
- I type: R type과 비슷하게 두개의 값을 이용해 연산을 한 다음 다른 하나의 레지스터에 저장을 하지만, 
연산할 값을 하나는 레지스터에서 가져오고 다른 하나는 레지스터가 아니라 지정된 임의의 값을 사용한다. 
I type 명령어에서 c = a + b와 같은 연산을 수행한다 하면, 이 때 b는 레지스터에 없는 임의의 값이 된다.
R type 명령어에 있는 약자인 rs와 rt를 그대로 사용하며, 이때 사용되는 임의의 값은 immediate(즉시값)로 부른다. 
계산은 rt = rs + imm로 한다.
- J type: 무조건 분기 명령어로, 특정 메모리 주소로 바로 이동이 필요한 경우에 사용되는 명령어다. 이동할 메모리 주소를 연산에 사용한다.   
![](https://github.com/aldrn29/Assembly/blob/master/screenshot/MIPS%20Instruction.jpg?raw=true)

#### Spim Simulator
MIPS 프로세서의 시뮬레이터로, 어셈블리 코드를 실행하기 위해 설계된 소프트웨어.   
Code Edit 기능이 없어 별도의 Text Editor 사용 필요하다. ex) VScode, 메모장

