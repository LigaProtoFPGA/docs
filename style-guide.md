# Guia de Estilo - VHDL/Verilog e Repositório

> > Este guia é uma **sugestão** de como organizar os projetos no repositório. Não é obrigatório seguir à risca, mas ter um padrão comum deixa o repositório mais fácil de navegar para todo mundo.
> 

---

## 📁 Estrutura de pastas no repositório

- /tutorials → tutoriais introdutórios passo a passo
- /examples → projetos de exemplo prontos para rodar
- /templates → modelos padrão para novos projetos
- /docs → documentação geral da liga
- colocar pasta de recursos no github (drives e tals tipo ethernet, display etc..) - tem no repositório de hardware livre

O ideal é que cada pasta tenha um arquivo **README.md** explicando o que contém.

---

## 🗂️ Nomenclatura de arquivos e pastas

- Sugestão: use **snake_case** — letras minúsculas separadas por underline
- Evite espaços, acentos ou caracteres especiais

✅ `contador_binario`
✅ `somador_4bits`
✅ `tutorial_introducao_vhdl`

❌ `ContadorBinario`
❌ `somador 4 bits`
❌ `Tutorial-Introdução`

---

## 🗃️ Estrutura de cada projeto

Uma organização sugerida para cada projeto no repositório:

- /nome_do_projeto
    - README.md → descrição do projeto
    - src/ → arquivos fonte (.vhd ou .v)
    - sim/ → arquivos de simulação (testbenches)
    - constraints/ → arquivo de constraints (.xdc)

---

## 📝 Modelo de README para cada projeto

Sugestão de modelo para o README.md do seu projeto:

**# Nome do Projeto**

**## Descrição**
O que esse projeto faz em 2-3 linhas.

**## Placa utilizada**
Ex: Nexys A7 (Artix-7)

**## Linguagem**
VHDL / Verilog

**## Como simular**
Passos para rodar a simulação no Vivado.

**## Como sintetizar**
Passos para gerar o bitstream e programar a placa.

**## Autor**
Nome — data

---

## ✍️ Convenções de código

**Nomes de entidades e módulos**
Use snake_case, nomes descritivos em inglês ou português — escolha um e mantenha em todo o projeto.

✅ `entity contador_binario is`
✅ `module somador_4bits`

**Indentação**
Use 2 ou 4 espaços — escolha um e tente manter em todo o arquivo. Evite misturar espaços e tabs.

**Comentários**
Uma boa prática é adicionar um comentário no topo de cada arquivo explicando o que ele faz:

- `- Projeto: Contador binário de 4 bits- Autor: Seu Nome- Data: DD/MM/AAAA- Descrição: Contador síncrono com reset assíncrono`

**Sinais ativos em baixo**
Uma convenção comum é usar o sufixo `_n` para indicar sinal ativo em nível baixo.

✅ `reset_n`
✅ `clr_n`

---

## ✅ Checklist sugerido antes de subir qualquer coisa

> 💡 Uma referência rápida para não esquecer nada importante.
> 
- [ ]  A pasta do projeto tem uma organização clara
- [ ]  O arquivo README.md está preenchido
- [ ]  Nomes de arquivos e pastas sem espaços ou acentos
- [ ]  Comentário de cabeçalho no topo dos arquivos fonte
- [ ]  A mensagem do commit descreve o que foi feito
