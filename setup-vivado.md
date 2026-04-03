# Instalação do Vivado + Vitis (Nexys A7 — Artix-7)

> ⚠️ Separe pelo menos **2 horas** e 85 **GB** de espaço em disco. A instalação é pesada mas só precisa ser feita uma vez.
> 

---

## 📦 1. Baixar o instalador

1. Acesse a página de downloads da AMD/Xilinx:
https://www.xilinx.com/support/download.html
2. Localize a seção **Vivado™ Edition — 2025.1**
3. Selecione **Self Extracting Web Installer** para o seu sistema operacional
4. Faça login ou crie uma conta gratuita para iniciar o download

---

## ⚙️ 2. Instalar o Vivado + Vitis

1. Execute o instalador baixado e clique em **Next**
2. Faça login com sua conta AMD e selecione **Download and Install Now** → **Next**
3. Na tela **Select Product to Install**, escolha **Vitis** *(isso instala o Vitis e o Vivado juntos — não escolha só o Vivado)*
4. Na tela **Select Extra Content**, deixe selecionado apenas:
    
    **Design Tools:**
    
    - ✅ Vitis
    - ✅ Vivado
    - ✅ Vitis HLS
    - ✅ DocNav
    
    **Devices — 7 Series:**
    
    - ✅ Artix-7 FPGAs
    
    > Desmarque tudo o que não está listado acima. Isso reduz bastante o tamanho da instalação.
    > 
    
    Clique em **Next**.
    
5. Aceite todos os termos de licença → **Next**
6. Escolha o diretório de instalação → **Next**
7. Revise o resumo e clique em **Install**

> 💡 A instalação pode levar de 20 minutos a 2 horas. Fique por perto no final — alguns prompts vão aparecer pedindo confirmação.
> 

---

## 🗂️ 3. Instalar os Board Files da Nexys A7

Os Board Files ensinam o Vivado a reconhecer sua placa automaticamente, facilitando a criação de projetos.

**Opção A — Direto pelo Vivado (mais fácil):**

1. Abra o Vivado pelo menu Iniciar
2. Clique em **Create Project** → **Next** → **Next**
3. Quando chegar na tela de seleção de placa, clique em **Refresh** para atualizar a lista
4. Pesquise por **Nexys A7** na barra de busca
5. Clique no ícone de download ao lado da placa → confirme

**Opção B — Pelo GitHub da Digilent (mais atualizado):**

1. Baixe e extraia os board files do repositório oficial: https://github.com/Digilent/vivado-boards
2. No Vivado, vá em **Tools → Settings**
3. Vá em **Vivado Store → Board Repository**
4. Clique no **+** e aponte para a pasta `vivado-boards/new/board_files`
5. Clique em **OK**, feche e reabra o Vivado

---

## 🔍 4. Selecionar o dispositivo correto da Nexys A7

Ao criar um novo projeto, quando chegar na tela de seleção de dispositivo, use os seguintes filtros:

- **Category:** General Purpose
- **Family:** Artix-7
- **Package:** csg324
- **Speed:** -1

Selecione o dispositivo que aparecer com essas especificações e clique em **Next**. Confira o resumo na janela **New Project Summary** e clique em **Finish**.

---

## ✅ 5. Tudo pronto!

O ambiente está configurado. Agora é só seguir os primeiros tutoriais no GitHub da liga para começar a trabalhar com a placa:

🔗 *Link do GitHub em breve*
