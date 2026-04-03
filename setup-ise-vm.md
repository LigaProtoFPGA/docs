# Instalação da ISE 14.7 VM (Nexys 1 e 2)

> ⚠️ Você vai precisar de pelo menos **20 GB** de espaço em disco e bastante paciência — alguns passos demoram muito.
> 

---

## 📦 1. Baixar os pacotes

- **Oracle VirtualBox 7.1.0** → [Download](https://download.virtualbox.org/virtualbox/7.1.0/VirtualBox-7.1.0-164728-Win.exe)
- **VirtualBox Extension Pack 7.1.0** → [Download](https://download.virtualbox.org/virtualbox/7.1.0/Oracle_VirtualBox_Extension_Pack-7.1.0.vbox-extpack)
- **ISE 14.7 VM (AMD/Xilinx)** — pode ser necessário criar conta gratuita na AMD → [Download](https://www.xilinx.com/downloadNav/vivado-design-tools/archive-ise.html) *(+15 GB, escolha a versão Windows 10)*

---

## 🔧 2. Pré-requisitos antes de instalar o VirtualBox

Se o instalador do VirtualBox reclamar de dependências, instale nesta ordem:

**2.1 — Microsoft Visual C++ 2019 Redistributable**
→ [Download vc_redist.x64.exe](https://aka.ms/vs/17/release/vc_redist.x64.exe)

**2.2 — Python**
→ [Download python-3.12.6-amd64.exe](https://www.python.org/ftp/python/3.12.6/python-3.12.6-amd64.exe)*(nesta versão o comando é `py`, não `python`)*

**2.3 — Win32 API (pywin32)**
Abra o Prompt de Comando e rode:

`py -m pip install --upgrade pywin32`

---

## ⚙️ 3. Instalar o VirtualBox

1. Instale o VirtualBox normalmente
2. Ao abrir pela primeira vez, aceite a instalação do **Extension Pack** (arquivo `.vbox-extpack` baixado no passo 1)

---

## 📂 4. Importar a VM do ISE 14.7

1. Descompacte o arquivo baixado da AMD *(demora bastante)*
2. Abra o VirtualBox → menu **File** → **Import Appliance**
3. Navegue até o arquivo `14.7_VM.ova` dentro da pasta `Xilinx_ISE_14.7_Win10_14.7_VM_0213_1\ova`
4. Confirme a importação *(demora bastante também)*

> 💡 Os arquivos também estão disponíveis em pendrive de 128 GB — fale com o professor Ney.
> 

---

## 🛠️ 5. Configurar a VM antes de rodar

Com a VM **desligada**, abra as configurações dela no VirtualBox:

**5.1 — Memória**
Em **Sistema**, reduza a memória para **1909 MB** (deve ficar abaixo da metade da RAM do seu PC)

**5.2 — Controladora gráfica**
Em **Tela**, mantenha a opção **VBoxSVGA**

**5.3 — Rede**
Em **Rede → Adaptador 1**, selecione **NAT** no menu "Conectado a:"

**5.4 — Pasta compartilhada** *(para acessar seus projetos dentro da VM)*
Em **Pastas Compartilhadas**, adicione uma nova pasta:

- Caminho: `C:\Xilinx\ise_projs` (ou onde você salvou)
- Nome: `ise_projs`
- Marque **Montar Automaticamente** → OK

Para criar um atalho no Desktop da VM, abra um terminal dentro dela e rode:

`cd /home/ise/Desktopln -s /home/ise/ise_projs ise_projs`

---

## 🔑 6. Configurar a licença

Abra um terminal dentro da VM e edite o arquivo `~/.bashrc`:

`nano /home/ise/.bashrc`

Adicione as duas linhas abaixo no final do arquivo:

`export LM_LICENSE_FILE=2100@172.65.212.135:8888export XILINXD_LICENSE_FILE=2100@paxos.inf.pucrs.br:8888`

Salve com `Ctrl+O` e feche com `Ctrl+X`.

Depois, edite o script de lançamento do ISE:

`cd /opt/Xilinx/14.7/ISE_DS/commonsudo nano app_launcher.sh`

Logo abaixo da primeira linha (`#!/bin/bash`), adicione:

`source /home/ise/.bashrc`

Salve e feche.

---

## ⚠️ 7. Erro de licença durante "Map"?

Se aparecer erro de licença no passo **Implement Design → Map**, siga estes passos:

1. Anote o `hostid` mencionado no erro
2. Feche a VM
3. No VirtualBox, vá em **Rede → Adaptador 1 → Configurações Avançadas**
4. Troque o **Endereço MAC** para: `08002768C935`
5. Clique OK e rode a VM novamente

---

## ✅ 8. Tudo pronto!

O ambiente está configurado. Agora é só seguir os primeiros tutoriais no GitHub da liga para começar a trabalhar com a placa:

🔗 *Link do GitHub em breve*
