# OverTheWire CTF - Writeups 🇧🇷

Este repositório contém minhas resoluções dos desafios da plataforma (https://overthewire.org/wargames/), com foco inicial no **Bandit**, voltado para segurança ofensiva e aprendizado de Linux.

---

## 🎯 Objetivo
Documentar minha evolução como praticante de CTFs (Capture The Flag), aprofundando meus conhecimentos em:

- Shell scripting
- Linux CLI
- Segurança ofensiva
- Privilege escalation
- Reconhecimento e enumeração

---

## 🚧 Progresso no Bandit

### 🚀 Progresso no Bandit

| Nível       | Status          | Descrição                                 | Solução                                                                    |
|-------------|-----------------|-------------------------------------------|----------------------------------------------------------------------------|
| Bandit 0    | ✅ Concluído    | Acessando o servidor via SSH              | Conectar via SSH ao `bandit.labs.overthewire.org` na porta 22 com o usuário `bandit0` e a senha `bandit0`. |
| Bandit 1    | ✅ Concluído    | Lendo arquivos simples no Linux           | A senha está no arquivo `readme` no diretório home. Use `cat readme`.        |
| Bandit 2    | ✅ Concluído    | Permissões básicas e arquivos escondidos  | A senha está em um arquivo chamado `-` no diretório home. Use `cat ./-` ou `cat < ./-`. |
| Bandit 3    | ✅ Concluído    | Espaços em nomes de arquivos              | A senha está em um arquivo chamado `spaces in this filename`. Use `cat "spaces in this filename"` ou `cat spaces\ in\ this\ filename`. |
| Bandit 4    | ✅ Concluído    | Encontrando arquivos específicos          | A senha está no único arquivo legível por humanos no diretório `inhere`. Use `find . -type f -readable -size 33c`. |
| Bandit 5    | ✅ Concluído    | Encontrando arquivos legíveis, não-executáveis e com 1033 bytes | A senha está no único arquivo legível por humanos, com 1033 bytes e não executável no diretório `inhere`. Use `find inhere -type f -size 1033c ! -executable`. |
| Bandit 6    | ✅ Concluído    | Encontrando a senha em um arquivo em `/var/lib/dpkg/info/` | A senha está no arquivo `/var/lib/dpkg/info/bandit7.txt`. Use `cat /var/lib/dpkg/info/bandit7.txt`. |
| Bandit 7    | ✅ Concluído    | Filtrando resultados com `grep`           | A senha está no arquivo `data.txt` próxima à palavra `millionth`. Use `grep millionth data.txt`. |
| Bandit 8    | ✅ Concluído    | Encontrando a N-ésima linha               | A senha está na única linha que aparece apenas uma vez em `data.txt`. Use `sort data.txt | uniq -u`. |
| Bandit 9    | ✅ Concluído    | Lidando com caracteres nulos (`null bytes`) | A senha está no arquivo `data.txt` e é a única linha que contém um `null byte` (`\0`). Use `strings data.txt` ou `cat data.txt | grep -v "[^[:print:]]"`. |
| Bandit 10   | ✅ Concluído    | Base64 e `base64 -d`                      | A senha está em `data.txt` e foi codificada em Base64. Use `base64 -d data.txt`. |
| Bandit 11   | ✅ Concluído    | Rotação de caracteres (`ROT13`)           | A senha está em `data.txt` e foi codificada com ROT13. Use `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`. |
| Bandit 12   | ✅ Concluído    | Hex dump e `xxd -r`                       | A senha está em `data.txt` e é um hex dump. Use `xxd -r data.txt`.         |
| Bandit 13   | 🔄 Em andamento | SSH Keys para o próximo nível             | A senha do próximo nível está no arquivo `sshkey.private` no diretório home. Use `ssh -i sshkey.private bandit14@localhost`. |
| Bandit 14   | ⏳ Em breve     | ...                                       | ...                                                                        |

---
