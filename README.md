# EphexActiveAudit - Auditoria de Active Directory

![Uploading image.png…]()

## 🔖 Visão Geral
O **EphexActiveAudit** é um pacote de auditoria do Active Directory criado para MSPs e consultores que assumem um ambiente novo e precisam obter uma visão completa da saúde e conformidade do AD antes de qualquer intervenção.

Desenvolvido por **Michael Oliveira**, o pacote é modular, simples de executar e gera um **relatório HTML consolidado** com os principais pontos de risco e desorganização do AD.

---

## ⚖️ Requisitos
- PowerShell 5.1 ou superior
- Execução como **Administrador**
- Módulo `ActiveDirectory` instalado (AD RSAT)

---

## 🚀 Como Executar
1. Extraia o arquivo `.zip` em uma pasta local, ex: `C:\MCHActiveAudit`
2. Abra o PowerShell como Administrador
3. Execute o script principal:

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force
cd "C:\MCHActiveAudit"
.\MCH_ActiveAudit.ps1
```

4. Aguarde a execução. Ao final, os arquivos serão gerados na pasta de saída (`C:\MCHAudit` por padrão).

---

## 📚 Relatório Gerado
O script principal gera um arquivo `relatorio_auditoria.html` com um resumo e links para os seguintes arquivos `.csv`:

| Categoria                              | Descrição                                                  |
|----------------------------------------|-------------------------------------------------------------|
| Usuários inativos ha 90+ dias         | Contas que não logam há mais de 90 dias                    |
| Contas desativadas                    | Contas de usuário com status inativo                       |
| Senhas que nunca expiram              | Contas sem política de expiração de senha                  |
| Usuários que nunca logaram            | Contas criadas, mas nunca autenticadas                     |
| Usuários administrativos              | Membros de grupos administrativos como Domain Admins, etc |
| Usuários com senha antiga (180+ dias) | Contas com senhas muito antigas                            |
| Computadores inativos                 | Objetos de computador que não autenticam há meses          |
| Grupos vazios                         | Grupos que não possuem membros                             |
| Usuários mal documentados            | Contas sem campos essenciais preenchidos                   |
| OUs e objetos                         | Quantidade de OUs e objetos por unidade organizacional     |

---

## 🔧 Personalização
Todos os módulos estão localizados na pasta `modules/` e podem ser editados, duplicados ou removidos conforme a necessidade do ambiente.

---

## 💬 Suporte e Contato
Para sugestões, suporte ou consultoria:

- ✉ **Email:** michael-745@hotmail.com
- 👤 **LinkedIn:** [Michael Oliveira](https://www.linkedin.com/in/michaell-oliveira/)

---

📆 **Versão:** 1.0  
🗓 **Atualizado em:** Março/2025  
👤 **Autor:** Michael Oliveira | Ephex Tecnologia
