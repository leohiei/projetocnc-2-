# 🛠️ Projeto CNC – Desbaste Interno com G71
**Autor:** Leonardo N. Duarte  
📧 nevesduartel@gmail.com 

---

## 🎯 Objetivo

Demonstra a usinagem de uma peça com **desbaste interno** utilizando o **ciclo G71** em um torno CNC. O projeto tem como objetivo demonstrar o uso de ciclos fixos, compensações e controle de avanço com base em um desenho técnico mecânico.

---

## 📐 Desenho Técnico da Peça

A peça apresenta:

* Diâmetro externo: **Ø100 mm**
* Diâmetros internos escalonados: **Ø80 mm**, **Ø50 mm**, **Ø30 mm**
* Chanfrados:

  * Interno: **1x45°**
  * Externo: **1.5x45°**
* Comprimento total: **70 mm**
* Região de usinagem: **50 mm**

![Desenho Técnico](./Captura%20de%20tela%202025-07-29%20145955.png)

---

## 🧾 G-Code Utilizado

O programa foi desenvolvido com os seguintes recursos:

* Seleção de ferramenta com **T0101**
* Controle de velocidade de corte com **G96**
* Ciclo de desbaste longitudinal com **G71**
* Ciclo de acabamento com **G70**
* Compensação de ferramenta (**G41/G40**)
* Limite de rotação (**G92**)

### Trecho principal – Desbaste com G71

```gcode
N70 G71 U2 R2
N80 G71 P90 Q160 U-1 W0.2 F0.2
```

* `U2`: sobremetal lateral de 2 mm
* `R2`: recuo de aproximação
* `P90 Q160`: bloco de início e fim do perfil
* `U-1 W0.2`: sobremetal para acabamento
* `F0.2`: avanço

---

## 💡 Objetivos do Projeto

* Simular e validar o ciclo G71 para perfis internos
* Usar comandos de compensação e limites de rotação
* Aplicar boas práticas de programação CNC
* Incluir projeto no portfólio DevOps/SecOps com foco em automação de manufatura

---

## ⚙️ Pré-requisitos

* Torno CNC com controle **Fanuc** ou compatível
* Suporte a ciclos fixos como **G71** e **G70**
* Ferramenta de desbaste interno (ex: T0101)
* Simulador CNC (ex: NC Viewer, Swansoft, etc.)

---

## 🗂 Estrutura do Código

| Linha     | Descrição                           |
| --------- | ----------------------------------- |
| N10–N50   | Preparação da máquina e rotação     |
| N60–N160  | Definição do perfil da peça         |
| N170–N210 | Acabamento com G70                  |
| N220–N240 | Finalização e retorno ao ponto zero |

---
