---
layout: post
title: "[CSE] Computer Architecture: 9 Control Signals"
date: 2025-06-10
category: [CSE]
---

# ⭐ 9 Control Signals

|  제어 신호   | 기능 설명                                                                | 설정 값 및 역할                                                                            |
| :----------: | :----------------------------------------------------------------------- | :----------------------------------------------------------------------------------------- |
|  **RegDst**  | 레지스터 파일에 쓸 목적지 레지스터 번호 선택 <br> rd가 있는가?           | **0**: I-타입(rt) <br> **1**: R-타입(rd)                                                   |
|  **Branch**  | 분기(beq, bne) 명령어일 때 1로 세팅, Zero와 AND 후 실제 분기(PCSrc) 결정 | **1**: 분기 조건 활성                                                                      |
| **MemRead**  | Data Memory에서 읽을지 여부                                              | **1**: lw 명령 시 메모리에서 데이터 읽기 <br> ➡️ 메모리에서 데이터를 읽어 Read Data로 출력 |
| **MemWrite** | Data Memory에 쓸지 여부                                                  | **1**: sw 명령 시 계산된 주소에 데이터 <br> ➡️ Write Data를 계산된 주소에 저장쓰기         |
| **MemtoReg** | 레지스터 파일에 쓸 데이터를 선택                                         | **0**: ALU 결과 <br> **1**: Data Memory `Read Data` <br> ➡️ Data Memory를 사용하는 lw, sw  |
|  **ALUOp**   | ALU 연산 종류 대략 지정 (2비트)                                          | **00**: 덧셈(lw/sw) <br> **01**: 뺄셈(beq) <br> **10**: R-타입(funct 해석)                 |
|  **ALUSrc**  | ALU 두 번째 입력 선택                                                    | **0**: 레지스터 `Read Data2` <br> **1**: Sign-extend 즉시값(imm)                           |
| **RegWrite** | 레지스터 파일에 쓰기 동작 여부                                           | **1**: R-타입, lw, addi 등 결과를 레지스터에 저장                                          |
