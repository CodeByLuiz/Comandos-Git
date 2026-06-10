# 📚 Guia Completo de Git para Uso Diário

Este guia reúne os principais comandos do Git, exemplos práticos, resolução de erros comuns e boas práticas para o dia a dia de desenvolvimento.

---

# 🚀 Configuração Inicial

## Configurar usuário

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

## Ver configurações

```bash
git config --list
```

## Definir editor padrão

```bash
git config --global core.editor "code --wait"
```

## Definir branch padrão

```bash
git config --global init.defaultBranch main
```

---

# 📂 Criando Repositórios

## Inicializar repositório

```bash
git init
```

## Clonar repositório

```bash
git clone URL
```

Exemplo:

```bash
git clone https://github.com/usuario/projeto.git
```

## Clonar branch específica

```bash
git clone -b develop URL
```

---

# 🔍 Consultas e Status

## Ver status atual

```bash
git status
```

## Histórico completo

```bash
git log
```

## Histórico resumido

```bash
git log --oneline
```

## Histórico gráfico

```bash
git log --graph --oneline --all
```

## Ver alterações

```bash
git diff
```

## Ver alterações staged

```bash
git diff --staged
```

---

# ➕ Adicionando Arquivos

## Adicionar arquivo específico

```bash
git add arquivo.txt
```

## Adicionar tudo

```bash
git add .
```

ou

```bash
git add --all
```

## Adicionar parcialmente

```bash
git add -p
```

---

# 💾 Commits

## Criar commit

```bash
git commit -m "Mensagem do commit"
```

## Commit rápido

```bash
git commit -am "Mensagem"
```

## Alterar último commit

```bash
git commit --amend
```

## Alterar mensagem do último commit

```bash
git commit --amend -m "Nova mensagem"
```

---

# 🌿 Branches

## Criar branch

```bash
git branch feature/login
```

## Listar branches

```bash
git branch
```

## Ver branches remotas

```bash
git branch -r
```

## Ver todas

```bash
git branch -a
```

## Trocar branch

```bash
git switch main
```

## Criar e trocar

```bash
git switch -c feature/login
```

## Renomear branch

```bash
git branch -m novo-nome
```

## Excluir branch

```bash
git branch -d nome-branch
```

## Forçar exclusão

```bash
git branch -D nome-branch
```

---

# 🔀 Merge

## Fazer merge

```bash
git merge feature/login
```

## Merge sem fast-forward

```bash
git merge --no-ff feature/login
```

## Cancelar merge

```bash
git merge --abort
```

---

# 🔄 Rebase

## Rebase simples

```bash
git rebase main
```

## Rebase interativo

```bash
git rebase -i HEAD~5
```

## Continuar rebase

```bash
git rebase --continue
```

## Cancelar rebase

```bash
git rebase --abort
```

---

# ☁️ Trabalhando com Remotos

## Ver remotos

```bash
git remote -v
```

## Adicionar remoto

```bash
git remote add origin URL
```

## Alterar remoto

```bash
git remote set-url origin URL
```

## Remover remoto

```bash
git remote remove origin
```

---

# ⬆️ Push

## Primeiro push

```bash
git push -u origin main
```

## Push normal

```bash
git push
```

## Push de branch específica

```bash
git push origin feature/login
```

## Forçar push

```bash
git push --force
```

## Forma mais segura

```bash
git push --force-with-lease
```

---

# ⬇️ Pull e Fetch

## Atualizar branch

```bash
git pull
```

## Pull com rebase

```bash
git pull --rebase
```

## Buscar alterações sem merge

```bash
git fetch
```

---

# 📦 Stash

## Guardar alterações

```bash
git stash
```

## Guardar com descrição

```bash
git stash push -m "ajuste login"
```

## Listar stashes

```bash
git stash list
```

## Recuperar stash

```bash
git stash pop
```

## Aplicar sem remover

```bash
git stash apply
```

## Remover stash

```bash
git stash drop
```

---

# 🏷️ Tags

## Criar tag

```bash
git tag v1.0.0
```

## Criar tag anotada

```bash
git tag -a v1.0.0 -m "Versão 1.0"
```

## Enviar tags

```bash
git push --tags
```

## Listar tags

```bash
git tag
```

---

# ↩️ Restaurar Arquivos

## Restaurar arquivo

```bash
git restore arquivo.txt
```

## Remover do stage

```bash
git restore --staged arquivo.txt
```

## Restaurar tudo

```bash
git restore .
```

---

# ⚠️ Reset

## Voltar commit mantendo alterações

```bash
git reset --soft HEAD~1
```

## Voltar commit removendo stage

```bash
git reset --mixed HEAD~1
```

## Apagar tudo

```bash
git reset --hard HEAD~1
```

---

# 🔙 Revert

## Desfazer commit mantendo histórico

```bash
git revert HASH
```

---

# 🍒 Cherry Pick

```bash
git cherry-pick HASH
```

---

# 🧹 Limpeza

## Simular limpeza

```bash
git clean -n
```

## Limpar arquivos

```bash
git clean -f
```

## Limpar arquivos e diretórios

```bash
git clean -fd
```

---

# 🔥 Recuperação de Emergência

## Ver histórico oculto

```bash
git reflog
```

## Recuperar commit perdido

```bash
git reflog
git checkout HASH
```

## Recuperar branch apagada

```bash
git reflog
git branch recuperada HASH
```

---

# 🚨 Erros Mais Comuns

## Push rejeitado

Erro:

```text
non-fast-forward
```

Solução:

```bash
git pull origin main
git push
```

---

## Conflito de Merge

Arquivo:

```text
<<<<<<< HEAD
Código Local
=======
Código Remoto
>>>>>>> branch
```

Após resolver:

```bash
git add .
git commit
```

---

## Detached HEAD

Erro:

```text
HEAD detached
```

Solução:

```bash
git switch -c nova-branch
```

---

## Arquivo adicionado por engano

```bash
git restore --staged arquivo.txt
```

---

## Commit errado

```bash
git reset --soft HEAD~1
```

---

## Arquivo apagado sem querer

```bash
git restore arquivo.txt
```

---

# ⚡ Fluxo Diário Recomendado

```bash
git pull

git switch -c feature/nova-funcionalidade

git add .

git commit -m "Implementa funcionalidade"

git push -u origin feature/nova-funcionalidade
```

---

# 📋 Cheat Sheet Rápido

| Ação | Comando |
|--------|----------|
| Ver status | `git status` |
| Adicionar tudo | `git add .` |
| Commit | `git commit -m "msg"` |
| Enviar | `git push` |
| Atualizar | `git pull` |
| Buscar remoto | `git fetch` |
| Trocar branch | `git switch nome` |
| Criar branch | `git switch -c nome` |
| Stash | `git stash` |
| Restaurar arquivo | `git restore arquivo` |
| Recuperar commit | `git reflog` |

---

# 🎯 Boas Práticas

- Faça commits pequenos e frequentes.
- Use mensagens claras.
- Evite `git push --force`.
- Sempre execute `git pull` antes de começar.
- Use branches para novas funcionalidades.
- Utilize Pull Requests para revisão.
- Mantenha a branch `main` sempre estável.
- Prefira `git pull --rebase` para histórico limpo.
- Use tags para versões publicadas.

---

**Autor:** Seu Nome  
**Última atualização:** Junho/2026
