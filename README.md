# NeoCore — Arquitetura Von Neumann + RISC 8-bit

> Projeto acadêmico desenvolvido para a disciplina **Computer Architecture and Organization** — UniFECAF, 2026.

---

## Visão Geral

O **NeoCore** é uma arquitetura de processador de 8 bits que combina o modelo **Von Neumann** — memória unificada para instruções e dados — com princípios **RISC** — conjunto de instruções reduzido e ciclo de máquina de quatro estágios fixos.

O objetivo foi projetar, documentar e apresentar um processador funcional do zero, cobrindo todos os componentes de uma CPU real: registradores, ALU, Unidade de Controle, hierarquia de memória e dispositivos de I/O.

---

## Diagrama da Arquitetura

![Diagrama NeoCore](NeoCore_drawio.png)

> 🔗 [Abrir diagrama interativo no Draw.io](https://app.diagrams.net/?title=NeoCore#RzZndbuJGFIDv8xQuK1XbCxT%2FghEhEhh2FzU0ESHavavG42Ow1mbo2E5Ir%2FYVqvYBut2Lqhe92kfgTfZJOv5ljEPiGColihRjj2N%2F35w5Z2Y489ZvKVotJsQC9%2FyMEhKcn5x5awNcV3CsXkNsnJ7zn6WGsEIUlkFy6eTk7LtmU5ht%2Fg1ClwjNZvHugDW%2FRW4IvcZPQAxCQfj26Q%2BhT38JnQCCkCJhOr42BL1pOkFD8IN7lzUNYB10F4Hn9qSuH1DyEQziEtpbkiV0bcd1uY%2FIdebLHmYvBLR7CzRwMHL78UnPsSwXuncL9qjrFcLQu2OoXUrCpQVWT%2BzaZBlcO79CT9KT4%2FjxUnycPOKVpLU0Q%2BwyCvavYV3glxqRmbdAPAjovcAuyqLYEO6jvw3hzrGCRa%2BhRacW4MwX7A6VHSO%2F15in90RuTxNdmUnj6qZkEa%2FCXCO7nnvy7xzPRUyCHyCakCgiJ%2BiVhUC3ccFhRrTLm3hQ67OrCbq%2BRVd0Dl0Rn2a%2FMUroIc7Jb5aOhSwQ2K%2FBXpISF4TXN8YPuY6sY6VSl6exxJlJ2QpmREtto0Lv2%2FFPwdWDNqIOKsdC7EPb%2BpBanI%2FW0zr6F%2BVQYCpyIez696%2FWqPv6YvN1zsJeADawnMDb%2FBMNgpfr5WAxU5g77A2RxfKJX1JEYe7njgpNHxs4ssZrAMWWbWv%2FwIkHi3xQYEgqN1JkToCkPGaAJ11tB8eVEYfCFSVzijw2QMIoIdYKAdO0wDafYN%2FDG7vfBZYSYEXbdrjC8WpVcR2a446nMe54yd4yxIFDlmlQvBhm%2FUjQaNvH%2FaSP%2Bzj0QjeK6BfVvZ1DST1z27%2BTQdLBE%2FAIe8ogtO2X1rO1eJP8xag2X6mDSqnLAy9X8M4BiqJ5EooqXnZL9doPkqVBuwjeNiUbyVVqf9qyYu3XxFLxl%2BXKxb8w1UF4AdvJTvRJuJCSMieKi2%2BfflfeLOqVthSpIERFkqrjOqUt6qoKJV%2BvWtkKFQxtw2DanyT0akzfrkvfwXLbFPeGw%2FHo48FwGD7h8C8nwmB8eZ040GMHb%2Bo6wNBRLP0pB1xM1HUgS3UcJMlhfHpZygsOyYUMHX9FfCdwbokfJYbR6XX1nGCd0NnNCdBiwJ0qOSFtWTEn6OWcIOm1csIC1lKB30X3wrvRhyQmrmquAFKaggvTVlpirXTAeqhUKLSYX%2BXqhMavBbXq%2BPJ%2B%2FP4Lx5dE8XB%2BZT%2F%2FePrC%2BbVD%2B%2F%2BjaeX4M8DRzC9FX67CoB69beuope1NBEejLyTCyvTpToiDXRKlOG%2FzmU2DluXpEr7HLjdZyNpP0vbPWO7ptgY7wSBD21L2zZUUXlPa8nn7JCq3R9RROTN61bRoQ4AXOf233%2F4U3oxmxrs4Ngahj5HgxMujzd%2BbL6RWlKRgxbmzqYEs7kRJhYVw3FV7lg7SdojIYp2lgwWYWMC5%2BCwMR8blcBTLGEZXHdvBqJYFRddBwXuD43ALsnYkDbAGHAa8h7%2BE0YeRcTNLREQbSitKMPh%2BPRWqgkR1Z%2F6Q6jmOimwhcbCKO8pYTIQ%2FcjK%2BCO%2Bn49lo0Dd%2BjHW8pegWCRT80A1YUq1lpNUyzRbaWVQklo5jpK0cYCRJpANE2YqCPYOkm2Xx5uJwOP15cHMdbTg3zyejSXmr0dzOuqLWQtT6dbxTvy06YM0hoSI0WJA5WSJ3lJ3bHTMYt7MN%2FfcxSjGNthG09m1MR9vQ0bNiYz4JKeuSeP%2BLZfQ5BPnCcU%2FepeAiNmVObt8fQJGYYX%2FWj8UwJ83zh7bjLU5M1PpQMYra0S3zETEdXTQ7zxGTysjcRHtIh4uJA2X80OJkq8OYTS8iHXU0QFvFeZ5NNBQyLBaVjmw%2BRwPi4iOZRR%2FBQjzLKM1EpHojgquvGfEDHGmlz1CyavdI4qgIxBPI%2FydB9soZQl6pjsug%2FJ8M%2BTtnEFyNORjj5Ow0%2Fu41OsN9Ifsf)

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

### ALU — Operações suportadas

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

```
neocore/
├── README.md                        # Este arquivo
├── NeoCore_drawio.png               # Imagem do diagrama
├── NeoCore_Arquitetura.drawio       # Arquivo editável do diagrama (Draw.io)
└── NeoCore_Parte_Teorica_Final.pdf  # Relatório teórico completo
```

---

## Ferramentas Utilizadas

| Ferramenta | Uso |
|---|---|
| [Draw.io](https://app.diagrams.net) | Modelagem do diagrama da arquitetura |
| LaTeX / ReportLab | Geração do relatório em PDF |

---

## Autor

**Eduardo Souza Mattos**  
RA: 35984  
Curso: Análise e Desenvolvimento de Sistemas  
Instituição: UniFECAF — 2026

---

## Licença

Este projeto foi desenvolvido para fins acadêmicos.  
Sinta-se livre para estudar, referenciar e adaptar com os devidos créditos.
