# 5. Análise e Inspeção de Repositório

Este resumo aborda três comandos essenciais para análise e inspeção de repositórios Git: `git show`, `git diff` e `git shortlog`. Eles ajudam a entender as alterações realizadas, comparar versões e gerar resumos de histórico.

---

## **1. git show**
O comando `git show` exibe informações detalhadas sobre um commit específico. Ele combina informações de metadados (autor, data, etc.) com as alterações realizadas no commit.

### **Uso básico:**
```bash
git show <commit_hash>
```
Exemplo:

```bash
git show 5813f456
```

Este comando exibe o commit com hash 5813f456, mostrando as alterações realizadas e os metadado.

***Obs:*** O comando **git log** exibe uma lista de commits
## 2. git diff
O comando git diff compara diferentes estados do repositório, como:
- Alterações entre o diretório de trabalho e o índice (staging area).
- Alterações entre commits.
- Alterações entre branches.

Uso básico:

```bash
git diff
```

**Exemplos:** 
- Comparar o diretório de trabalho com o índice:
```bash
git diff
```

- Comparar dois commits:

```bash
git diff <commit1> <commit2>
```

- Comparar duas branches:


```bash
git diff branch1 branch2
```

- Comparar o commit atual com o anterior

```bash
git diff HEAD^
```

**Como comparar as diferenças entre o repositório local e remoto no Git**

Para comparar as diferenças entre o repositório local e o remoto, você pode usar o seguinte comando:

```bash
git fetch
git diff origin/<branch>
```
**Explicação dos comandos:**

1. git fetch:
- Este comando atualiza as referências do repositório remoto no seu repositório local, mas não faz o merge ou altera os arquivos no seu diretório de trabalho. Ele baixa as informações mais recentes do repositório remoto, como commits e branches.

2.git diff origin/branch:
- Após o git fetch, este comando compara a branch local com a branch remota correspondente (substitua <branch> pelo nome da branch, como main ou master).
- Ele mostra as diferenças entre o estado atual do repositório local e o remoto.


## 3. git shortlog
O comando git shortlog gera um resumo do histórico de commits, agrupando-os por autor. É útil para visualizar contribuições em projetos colaborativos.

Uso básico:

```bash
git shortlog
```

**Exemplo:**

```bash
git shortlog -s -n
```
- s: Mostra apenas o número de commits por autor.
- n: Ordena os autores pelo número de commits.

### Exercícios Práticos

**Exercício 1: Explorando git show**
1.Escolha um commit específico no seu repositório.
2.Use o comando git show para visualizar os detalhes do commit.
3.Identifique:
- O autor do commit.
- A data do commit.
- As alterações realizadas.


**Exercício 2: Comparando com git diff**
1.Faça alterações em um arquivo no seu repositório.
2.Use git diff para visualizar as mudanças antes de adicioná-las ao índice.
3.Crie dois commits diferentes e use git diff <commit1> <commit2> para comparar as alterações entre eles.

**Exercício 3: Resumindo com git shortlog**
1.Execute git shortlog no seu repositório.
2.Use a flag -s -n para visualizar o número de commits por autor, ordenados.
3.Analise quem contribuiu mais para o projeto.