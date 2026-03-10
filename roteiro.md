## Roteiro básico de versionamento com Git

Este repositório é um exemplo simples em Python, com:

- `app.py`: código da aplicação
- `test_app.py`: testes
- `.github/workflows/ci.yml`: CI com GitHub Actions

A ideia do versionamento é registrar mudanças no projeto com segurança.

---

## 1. Iniciar o repositório

Se o projeto ainda não estiver versionado:

```bash
git init
```

Esse comando cria o repositório Git na pasta atual.

---

## 2. Verificar o estado dos arquivos

```bash
git status
```

Esse comando mostra arquivos novos, modificados e prontos para commit.

---

## 3. Adicionar arquivos para versionamento

Adicionar um arquivo específico:

```bash
git add app.py
```

Adicionar vários arquivos:

```bash
git add app.py test_app.py
```

Adicionar tudo que foi alterado:

```bash
git add .
```

---

## 4. Criar um commit

```bash
git commit -m "adiciona funcao de subtracao"
```

O commit salva um ponto da evolução do projeto.

---

## 5. Criar uma nova branch

Para desenvolver uma mudança sem mexer direto na branch principal:

```bash
git checkout -b subtracao
```

Esse comando:

- cria a branch `subtracao`
- já troca para ela

---

## 6. Trocar de branch

Ir para a branch principal:

```bash
git checkout master
```

Voltar para a branch de funcionalidade:

```bash
git checkout subtracao
```

---

## 7. Exemplo prático neste repositório

Fluxo básico:

1. Criar uma branch para alterar `app.py`
2. Fazer a mudança
3. Adicionar os arquivos
4. Criar um commit
5. Voltar para `master`
6. Fazer o merge

Exemplo:

```bash
git checkout -b subtracao
git add app.py test_app.py
git commit -m "cria funcao de subtracao"
git checkout master
git merge subtracao
```

---

## 8. Juntar branches com merge

Quando a branch estiver pronta:

```bash
git checkout master
git merge subtracao
```

Isso traz para `master` as alterações feitas na branch `subtracao`.

---

## 9. Conferir o histórico

```bash
git log --oneline
```

Mostra os commits de forma resumida.

---

## Resumo dos comandos básicos

```bash
git init
git status
git add .
git commit -m "mensagem"
git checkout -b nome-da-branch
git checkout master
git checkout nome-da-branch
git merge nome-da-branch
git log --oneline
```

---

## Observação

Neste repositório, depois de enviar alterações para o GitHub, o workflow em `.github/workflows/ci.yml` executa os testes automaticamente com `pytest`.