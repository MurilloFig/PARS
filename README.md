# PARS - Passive Recon Script

PARS é um script em Bash para enumeração simples de domínios e IPs a partir do `index.html` de um site alvo.

Ele:
- Faz download do `index.html` do alvo usando `wget`
- Extrai links com `grep` / `cut`
- Normaliza a lista de domínios
- Resolve o IP de cada domínio usando `host`
- Exibe tudo em uma tabela organizada (URL | IP)

---

## Requisitos

- `bash`
- `wget`
- `grep`
- `cut`
- `awk`
- `host` (pacote `bind9-dnsutils` ou similar)

No Kali, geralmente você já tem tudo. Se precisar:

```bash
sudo apt update
sudo apt install wget dnsutils -y

Como usar ?
1. Dar permissão de execução:
chmod +x pars.sh

2. Executar o script:
./pars.sh https://example.com.br/

Exemplo de saída
                    URL                     |          IP
-----------------------------------------------------------------------------
1. intranet.businesscorp.com.br             | 37.59.174.228
2. mail.businesscorp.com.br                 | 37.59.174.227
3. srvkey.businesscorp.com.br               | 37.59.174.235
