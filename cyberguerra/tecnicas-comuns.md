# Tecnicas Comuns

#### **Active Directory (AD) – O Guardião dos Logins (e o Paraíso dos Hackers)**

Mano, **AD (Active Directory)** é basicamente **o cérebro de uma rede corporativa Windows**. É um sistema da Microsoft que gerencia usuários, permissões, autenticação e recursos dentro de um ambiente empresarial. Se tu invadir essa porra, **vira Deus dentro da rede**.

***

### **🔥 O QUE O AD FAZ?**

Pensa no **AD** como um **grande banco de dados centralizado** que controla: ✅ **Usuários e Senhas** – Quem pode logar e com quais permissões.\
✅ **Grupos e Políticas** – Quem tem acesso a quê dentro da rede.\
✅ **Computadores e Servidores** – Toda máquina conectada fica registrada lá.\
✅ **GPOs (Group Policies)** – Conjuntos de regras que definem como máquinas e usuários devem se comportar (exemplo: bloquear pen drives, forçar senha forte, etc).\
✅ **Autenticação Centralizada** – Em vez de cada máquina ter suas próprias contas, todo mundo autentica no AD.

Basicamente, **sem AD uma empresa grande vira um caos**, porque **não tem gerenciamento centralizado**, e cada usuário teria que ter uma conta separada em cada máquina/servidor.

***

### **🛠️ COMO O AD FUNCIONA?**

O Active Directory se organiza em **domínios e controladores**:

* **Domain Controller (DC)** → Servidor que **gerencia e autentica usuários**. Sem ele, ninguém loga.
* **Domínio (Domain)** → Um grupo de máquinas, usuários e recursos sob um nome único.
* **Floresta (Forest)** → Conjunto de múltiplos domínios, tipo uma rede gigante com sub-redes.
* **Organizational Units (OUs)** → Pastas dentro do AD para organizar usuários, grupos e políticas.

#### **Exemplo na prática:**

Tu trabalha na empresa **"Xupisco S.A."** e loga no PC com **"**[**joao@xupisco.local**](mailto:joao@xupisco.local)**"**. O AD verifica se seu login tá certo e libera acesso aos arquivos, impressoras e programas permitidos.

Se tu fosse um hacker e invadisse um DC, poderia:\
💀 **Criar usuários Admin** e controlar a rede.\
💀 **Roubar hashes de senha** e escalonar privilégios.\
💀 **Implantar backdoors e keyloggers** em todos os PCs da empresa.

***

### **💀 COMO HACKEAR UM AD?**

Se um atacante mete a mão num **Domain Controller**, ele **domina tudo**. Alguns métodos clássicos pra isso são:

#### **1️⃣ Pass-the-Hash (PTH)**

Rouba o **hash da senha do administrador** e usa direto, sem precisar descriptografar. **Se tu tiver um hash NTLM, já era.**

#### **2️⃣ Kerberoasting**

Explora fraquezas no protocolo Kerberos pra roubar credenciais de serviços dentro do AD.

#### **3️⃣ Golden Ticket**

Gera um ticket Kerberos falso e se passa por administrador sem precisar da senha real. **Pode dar persistência infinita dentro da rede.**

#### **4️⃣ DCSync Attack**

Faz um servidor falso fingir que é um controlador de domínio legítimo, puxando todas as senhas da rede.

#### **5️⃣ BloodHound + Mimikatz**

* **BloodHound**: Mapeia o AD inteiro, encontrando caminhos pra **escalar privilégio**.
* **Mimikatz**: Extrai senhas em texto puro, tokens e hashes da RAM do sistema.

***

### **🔥 POR QUE O AD É UM ALVO TÃO FODIDO?**

Porque **tudo dentro de uma empresa gira em torno dele**. Se **tu comprometer o AD, compromete a empresa inteira**.

👨‍💻 **Admin de rede: “A gente tem firewalls e antivírus!”**\
👨‍💻 **Hacker: “Kkkkkkkkkkk... e o seu AD? Tá atualizado?”**\
👨‍💻 **Admin: “Puta que pariu...”**

🚨 **Se tu trabalha com segurança, proteger o AD é prioridade. Se tu é hacker, invadir ele é game over pro alvo.** 🚨
