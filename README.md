# Dissolução societária IFÁ — painel de apuração

Painel estático publicado em **https://dissolucao.ifarecords.com.br/apuracao-82bedc0733/** (GitHub Pages).
Todo o conteúdo é **criptografado** (AES-256-GCM). Sem uma senha válida, os arquivos
deste repositório não revelam nenhum dado.

## Perfis

Cada senha pertence a uma pessoa e a um perfil. Cada tipo de conteúdo tem a sua própria chave,
então um perfil não consegue abrir o que não é dele, nem baixando os arquivos.

| Perfil | Vê |
|---|---|
| Administrador | Tudo + relatório de acessos (sessões e visualizações por pessoa) |
| Advogado | Dívida pessoal, investimento IFÁ, carreira da Dhara, contratos e planilha completa |
| Ana Carolina | Só a dívida pessoal, com comprovantes e a planilha da dívida |
| Dhara | Só o investimento na carreira dela, com comprovantes |

## Estrutura

| Caminho | O que é |
|---|---|
| `apuracao-82bedc0733/index.html` | Tela de senha + painel + dados criptografados. Gerado pelo gerador de acessos. |
| `apuracao-82bedc0733/r/*.bin` | Comprovantes, contratos e planilhas criptografados. |
| `index.html`, `404.html` | Redirecionam para o site institucional. Nenhum link aponta para o painel. |
| `robots.txt` | Pede aos buscadores para não indexar nada. |
| `CNAME` | Domínio `dissolucao.ifarecords.com.br`. |

## Cadastrar ou trocar senhas

1. Abra o `gerador-de-senhas.html` **no seu computador** (ele não fica neste repositório).
2. Uma linha por pessoa: nome, perfil e senha → **Gerar index.html**.
3. No GitHub: pasta `apuracao-82bedc0733` → *Add file* → *Upload files* → `index.html` → *Commit*.

## Registro de acessos

Os acessos são gravados numa Planilha Google da Priscila por um Apps Script (`Code.gs`, entregue
fora do repositório porque contém os tokens). A URL do App da Web vai no gerador de acessos.

## Atualizar os números

Os dados ficam em `r/d_*.bin`, fora do `index.html`. Atualizações de números não exigem gerar as senhas de novo; só mudanças no código do painel exigem.

Quando a apuração muda, o pacote é regerado por inteiro (novos `.bin` + novo gerador).
O gerador antigo não abre o pacote novo: gere e suba um `index.html` novo.

## Segurança

- **Nunca** suba o gerador, o `Code.gs`, planilhas, JSON ou scripts com dados (o `.gitignore` bloqueia).
- Os arquivos publicados são públicos; a proteção é a criptografia. Use senhas longas
  (botão *Sugerir* do gerador).
- Envie o link e a senha por canais diferentes.
