

# NeoCore — Arquitetura Von Neumann + RISC 8-bit

> 🇧🇷 Português | 🇺🇸 [English version below](#english-version)

---

## Visão Geral

O **NeoCore** é uma arquitetura de processador de 8 bits que combina o modelo **Von Neumann** — memória unificada para instruções e dados — com princípios **RISC** — conjunto de instruções reduzido e ciclo de máquina de quatro estágios fixos.

O objetivo foi projetar, documentar e apresentar um processador funcional do zero, cobrindo todos os componentes de uma CPU real: registradores, ALU, Unidade de Controle, hierarquia de memória e dispositivos de I/O.

---

## Diagrama da Arquitetura

![Diagrama NeoCore](https://github.com/Sponge1774/neocore-arquitetura/blob/main/NeoCore.drawio%20(3)%20(1).png)

> 🔗 [Abrir diagrama interativo no Draw.io](https://app.diagrams.net/#G1kzPLKlWRylspouDQqnxHkYC-c5_ukaLW#%7B%22pageId%22%3A%2274jmDBkqLj5kTu3bC8fV%22%7D)

---

## Arquitetura

### Blocos Principais

| Bloco | Componentes | Função |
|---|---|---|
| **CPU** | PC, MAR, MBR, IR, AC, UC, ALU, MUX 4:1 | Processamento e controle |
| **Memória** | Cache L1, RAM, ROM BIOS, MUX 3:1 | Armazenamento hierárquico |
| **I/O** | Displays HEX, Botões WE/OP0/OP1 | Entrada de controle e saída visual |

### Registradores da CPU

| Registrador | Nome completo | Função |
|---|---|---|
| **PC** | Program Counter | Endereço da próxima instrução |
| **MAR** | Memory Address Register | Envia endereço à memória |
| **MBR** | Memory Buffer Register | Carrega dado retornado pela memória |
| **IR** | Instruction Register | Armazena a instrução em execução |
| **AC** | Acumulador | Guarda o resultado da ALU |

### ALU — Operações Suportadas

| Opcode (IR[7:6]) | Operação |
|---|---|
| `00` | ADD |
| `01` | SUB |
| `10` | AND |
| `11` | OR |

### Hierarquia de Memória

| Nível | Endereços | Tipo |
|---|---|---|
| Cache L1 | `0x00 – 0x3F` | Acesso rápido |
| RAM | `0x40 – 0x7F` | Memória principal |
| ROM BIOS | `0x80 – 0xFF` | Programa de inicialização (somente leitura) |

---

## Ciclo de Máquina

```
[1] FETCH       PC → MAR → Memória → MBR → IR
[2] DECODE      UC lê IR[7:6] e define CTRL_OP
[3] EXECUTE     ALU(AC, MBR) com operação selecionada
[4] WRITEBACK   Resultado → MUX 4:1 → AC
      ↑_________________LOOP_____________________↑
```

> Frequência de clock: **4 Hz** — permite visualizar cada estágio em tempo real.

---

## Unidade de Controle

A UC é implementada como uma **FSM mod-4** (Finite State Machine de 4 estados), correspondendo aos quatro estágios do ciclo de máquina. O sinal `UC_STATE` indica o estado atual; o sinal `CTRL_OP` seleciona a operação da ALU.

---

## Arquivos do Repositório

| Arquivo | Descrição |
|---|---|
| [README.md](https://github.com/Sponge1774/neocore-arquitetura/blob/main/README.md) | Este arquivo |
| [LICENSE](https://github.com/Sponge1774/neocore-arquitetura/blob/main/LICENSE) | Licença MIT |
| [NeoCore_drawio(3).png](https://github.com/Sponge1774/neocore-arquitetura/blob/main/NeoCore.drawio%20(3)%20(1).png) | Imagem do diagrama |
| [NeoCore.drawio](https://github.com/Sponge1774/neocore-arquitetura/blob/main/NeoCore.drawio) | Arquivo editável do diagrama (Draw.io) |
| [NeoCore_Parte_Teorica_Final_08mar2026.pdf](https://github.com/Sponge1774/neocore-arquitetura/blob/main/NeoCore_Parte_Teorica_Final_08mar2026%20(1).pdf) | Relatório teórico completo |

---

## Ferramentas Utilizadas

| Ferramenta | Uso |
|---|---|
| [Draw.io](https://app.diagrams.net) | Modelagem do diagrama da arquitetura |
| ReportLab | Geração do relatório em PDF |

---

## Autor

**Eduardo Souza Mattos**
RA: 35984
Curso: Análise e Desenvolvimento de Sistemas
Instituição: UniFECAF — 2026

---

## Licença

Distribuído sob a licença **MIT**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---
---

# English Version

> 🇺🇸 English | 🇧🇷 [Versão em Português acima](#neocore--arquitetura-von-neumann--risc-8-bit)

---

## Overview

**NeoCore** is an 8-bit processor architecture that combines the **Von Neumann** model — unified memory for both instructions and data — with **RISC** principles — a reduced instruction set and a fixed four-stage machine cycle.

The goal was to design, document, and present a functional processor from scratch, covering all components of a real CPU: registers, ALU, Control Unit, memory hierarchy, and I/O devices.

---

## Architecture Diagram

![NeoCore Diagram](https://github.com/Sponge1774/neocore-arquitetura/blob/main/NeoCore.drawio%20(3)%20(1).png)

> 🔗 [Open interactive diagram on Draw.io](https://app.diagrams.net/#G1kzPLKlWRylspouDQqnxHkYC-c5_ukaLW#%7B%22pageId%22%3A%2274jmDBkqLj5kTu3bC8fV%22%7D)

---

## Architecture

### Main Blocks

| Block | Components | Function |
|---|---|---|
| **CPU** | PC, MAR, MBR, IR, AC, CU, ALU, MUX 4:1 | Processing and control |
| **Memory** | Cache L1, RAM, ROM BIOS, MUX 3:1 | Hierarchical storage |
| **I/O** | HEX Displays, Buttons WE/OP0/OP1 | Control input and visual output |

### CPU Registers

| Register | Full Name | Function |
|---|---|---|
| **PC** | Program Counter | Address of the next instruction |
| **MAR** | Memory Address Register | Sends address to memory |
| **MBR** | Memory Buffer Register | Holds data returned from memory |
| **IR** | Instruction Register | Stores the instruction being executed |
| **AC** | Accumulator | Holds the ALU operation result |

### ALU — Supported Operations

| Opcode (IR[7:6]) | Operation |
|---|---|
| `00` | ADD |
| `01` | SUB |
| `10` | AND |
| `11` | OR |

### Memory Hierarchy

| Level | Address Range | Type |
|---|---|---|
| Cache L1 | `0x00 – 0x3F` | Fast access |
| RAM | `0x40 – 0x7F` | Main memory |
| ROM BIOS | `0x80 – 0xFF` | Boot program (read-only) |

---

## Machine Cycle

```
[1] FETCH       PC → MAR → Memory → MBR → IR
[2] DECODE      CU reads IR[7:6] and sets CTRL_OP
[3] EXECUTE     ALU(AC, MBR) with selected operation
[4] WRITEBACK   Result → MUX 4:1 → AC
      ↑_________________LOOP_____________________↑
```

> Clock frequency: **4 Hz** — allows each stage to be observed in real time.

---

## Control Unit

The CU is implemented as a **mod-4 FSM** (Finite State Machine with 4 states), each corresponding to one stage of the machine cycle. The `UC_STATE` signal indicates the current state; the `CTRL_OP` signal selects the ALU operation.

---

## Repository Files

| File | Description |
|---|---|
| [README.md](https://github.com/Sponge1774/neocore-arquitetura/blob/main/README.md) | This file |
| [LICENSE](https://github.com/Sponge1774/neocore-arquitetura/blob/main/LICENSE) | MIT License |
| [NeoCore_drawio(3)(1).png](https://github.com/Sponge1774/neocore-arquitetura/blob/main/NeoCore.drawio%20(3)%20(1).png) | Architecture diagram image |
| [NeoCore.drawio](https://github.com/Sponge1774/neocore-arquitetura/blob/main/NeoCore.drawio) | Editable diagram file (Draw.io) |
| [NeoCore_Parte_Teorica_Final_08mar2026.pdf](https://github.com/Sponge1774/neocore-arquitetura/blob/main/NeoCore_Parte_Teorica_Final_08mar2026%20(1).pdf) | Full theoretical report |

---

## Tools Used

| Tool | Purpose |
|---|---|
| [Draw.io](https://app.diagrams.net) | Architecture diagram modeling |
| ReportLab | PDF report generation |

---

## Author

**Eduardo Souza Mattos**
Student ID: 35984
Degree: Systems Analysis and Development
Institution: UniFECAF — 2026

---

## License

Distributed under the **MIT License**. See [LICENSE](LICENSE) for more details.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
