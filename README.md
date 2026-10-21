# Apuração IFÁ — publicação

Hospedagem do painel de apuração financeira da dissolução societária da IFÁ Sounds Ltda.
O painel é estático e **todo o conteúdo é criptografado** (AES-256-GCM): sem uma senha
válida, os arquivos deste repositório não revelam nenhum dado.

## Estrutura

| Caminho | O que é |
|---|---|
| `apuracao-82bedc0733/index.html` | Tela de senha + código do painel + dados criptografados. Gerado pelo gerador de senhas. |
| `apuracao-82bedc0733/r/*.bin` | Comprovantes criptografados (abertos só depois da senha). |
| `index.html`, `404.html` | Redirecionam para o site institucional. Nenhum link aponta para o painel. |
| `robots.txt` | Pede aos buscadores para não indexar nada. |

O endereço do painel fica: `https://dissolucao.ifarecords.com.br/apuracao-82bedc0733/`

## Cadastrar ou trocar senhas

1. Abra o `gerador-de-senhas.html` **no seu computador** (ele não fica neste repositório).
2. Uma senha por pessoa → **Gerar index.html**.
3. No GitHub: entre na pasta `apuracao-82bedc0733` → *Add file* → *Upload files* → envie o `index.html` → *Commit*.
4. Em 1–2 minutos o GitHub Pages publica a nova versão.

Para tirar o acesso de alguém: apague a pessoa no gerador, gere de novo e suba o arquivo.

## Atualizar os números

Quando a apuração muda, o pacote é regerado por inteiro (novos `.bin` + novo gerador).
Substitua a pasta `apuracao-82bedc0733/r` e use o gerador novo — o antigo não abre o pacote novo.

## Publicação (GitHub Pages + domínio IFÁ)

1. *Settings → Pages*: Source = **Deploy from a branch**, Branch = `main`, pasta `/ (root)`.
2. Em *Custom domain*, informe o subdomínio (ex.: `dissolucao.ifarecords.com.br`) e salve.
   Isso cria o arquivo `CNAME` na raiz.
3. No DNS do domínio `ifarecords.com.br`, crie um registro **CNAME**:
   `dissolucao` → `techifarecords.github.io`
4. Depois que o certificado sair, marque **Enforce HTTPS**.

## Segurança

- **Nunca** suba o gerador de senhas, planilhas, JSON ou scripts com dados (o `.gitignore` bloqueia).
- Os arquivos publicados são públicos, mesmo com o repositório privado; a proteção é a criptografia.
  Por isso as senhas devem ser longas (use o botão *Sugerir* do gerador: 12 caracteres aleatórios).
- Envie o link e a senha por canais diferentes.
