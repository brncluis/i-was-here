
# Guia Geral de Contribuição – Git & GitHub

Este documento reúne instruções essenciais para colaborar em repositórios utilizando Git e GitHub, incluindo:

- Como criar branches
- Como fazer commits e enviar alterações
- Como abrir Pull Requests (PRs)
- Como resolver conflitos de merge
- Como manter seu fork atualizado

---

## 1. Criando seu Fork e Clonando o Repositório

### 1.1 Fork

No GitHub:

1. Acesse o repositório original.
2. Clique em **Fork** para criar uma cópia na sua conta.

### 1.2 Clone do fork

No terminal:

```bash
git clone https://github.com/<seu-usuario>/<nome-do-repo>.git
cd <nome-do-repo>
```

---

## 2. Criando e Trabalhando em Branches

Sempre trabalhe em uma branch separada da `main`.

### 2.1 Criar uma branch

```bash
git checkout -b nome-da-branch
```

Exemplos:

- `ex01-joao-silva`
- `feature-adiciona-lista`
- `fix-ajusta-markdown`

### 2.2 Ver suas branches

```bash
git branch
```

### 2.3 Trocar de branch

```bash
git checkout nome-da-branch
```

---

## 3. Fazendo Commits

### 3.1 Preparando arquivos (git add)

```bash
git add caminho/do/arquivo
```

Para adicionar tudo (_evite usar isso_):

```bash
git add .
```

### 3.2 Commit com mensagem clara

```bash
git commit -m "mensagem objetiva sobre a mudança"
```

Boas mensagens:

- `"adiciona item na lista de IDEs"`
- `"cria arquivo do grupo 03"`
- `"corrige formatação do markdown"`

Evite mensagens vagas como `"update"`, `"teste"`, `"ajustes"`.

---

## 4. Enviando a Branch Para o GitHub (git push)

```bash
git push origin nome-da-branch
```

---

## 5. Criando Pull Requests (PR)

Após enviar sua branch:

1. Acesse **seu fork** no GitHub.
2. Clique em **Compare & Pull Request**.
3. Confirme que:
   - "base repository" = repositório do professor
   - "base branch" = `main`
   - "compare" = sua branch
4. Preencha título e descrição.
5. Envie o PR.

---

## 6. Mantendo Seu Fork Atualizado

Às vezes o repositório do professor recebe novas alterações.  
Você pode sincronizar usando o “upstream”.

## 6.1 Adicionar o repositório original como upstream

```bash
git remote add upstream https://github.com/<professor>/<nome-do-repo>.git
```

## 6.2 Atualizar sua branch main

```bash
git checkout main
git pull upstream main
git push origin main
```

---

## 7. Resolvendos Conflitos de Merge

Conflitos acontecem quando duas pessoas alteram a mesma parte do arquivo.

### 7.1 Quando o conflito aparecer

Você verá mensagens como:

```txt
<<<<<<< HEAD
conteúdo da sua branch
=======
conteúdo da branch remota
>>>>>>> outra-branch
```

### 7.2 Como resolver

1. Abra o arquivo com conflito.
2. Escolha o conteúdo correto (ou combine os dois).
3. Remova **todas** as marcações (mantendo o conteúdo desejado):
   - `<<<<<<<`
   - `=======`
   - `>>>>>>>`
4. Salve o arquivo.

### 7.3 Após resolver

```bash
git add .
git commit -m "resolve conflito no arquivo X"
git push
```

Se o conflito aconteceu num Pull Request, o GitHub atualizará automaticamente.

---

## 8. Boas Práticas de Colaboração

- Faça commits pequenos;
- Use branches para cada atividade ou correção;
- Escreva PRs claros e objetivos;
- Atualize sua `main` antes de começar uma branch nova;
- Sempre verifique o que outras pessoas já alteraram antes de editar.

---

## 9. Fluxo Geral de Trabalho (Resumo)

```txt
fork → clone → criar branch → editar arquivos
→ git add → git commit → git push → Pull Request
→ revisão → merge
```
