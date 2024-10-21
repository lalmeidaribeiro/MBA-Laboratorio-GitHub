<h1>Labs - Laboratorio GitHub</h1>
<p>Este repositório foi criado como parte do laboratório realizado nos dias 21 e 28 de junho de 2024 pela Faculdade Impacta. O principal objetivo foi apresentar o GitHub e os comandos mais utilizados. Durante as sessões, criamos este repositório e executamos diversos comandos Git para o aprendizado prático.<p>
<p>Abaixo, listo alguns dos comandos utilizados para fins de referência e lembrete: </p>

- `git init` - Inicializa um novo repositório Git no diretório atual.
- `git clone` - Cria uma cópia local de um repositório remoto.
- `git log` - Buscando o histórico dos arquivos.
- `git log --oneline` - Exibe o histórico de commits de forma concisa, mostrando cada commit em uma única linha. 
- `git log --patch` - Exibe o histórico de commits, assim como o git log, mas inclui as diferenças (diffs) introduzidas em cada commit. Isso significa que, além de ver as mensagens dos commits, você também verá as alterações específicas feitas em cada arquivo.
- `git log --stat`- Exibe o histórico de commits, mostrando um resumo das alterações feitas em cada commit(Hash do commit, autor e a data, mensagem do commit).

## Configurações do Git 
- `git config --global user.name "SEU USUÁRIO GITHUB"`, `git config --global user.email "SEU EMAIL GITHUB"`- São usados para configurar o nome de usuário e o endereço de e-mail que o Git irá usar para identificar suas contribuições nos commits.
- `git config --list` - Exibe uma lista de todas as configurações do Git que estão atualmente aplicadas no seu sistema. Isso inclui configurações globais, locais (por repositório) e do sistema.  
- `git config --global --unset user.name` - Usado para remover a configuração do nome de usuário global do Git. Após executar esse comando, o Git não terá mais um nome de usuário definido para todos os repositórios em seu sistema.

## Acessando GitHub com Git localmente
- `git add .`- Usado para adicionar todas as alterações feitas em arquivos no diretório atual e em subdiretórios à área de staging (preparação para commit) no Git.
- `git commit -m " "` - usado para criar um novo commit no Git, registrando as alterações que foram adicionadas à área de staging. A opção -m permite que você inclua uma mensagem de commit diretamente no comando.
- `git push`- Usado para enviar (ou "empurrar") suas alterações locais para um repositório remoto. Isso é comum em ambientes de colaboração.
- `gh --version` - É usado para verificar a versão da CLI do GitHub (GitHub CLI) instalada em seu sistema. A CLI do GitHub é uma ferramenta que permite interagir com os repositórios do GitHub diretamente do terminal.
- `gh auth login`- É usado para autenticar a CLI do GitHub (GitHub CLI) com sua conta do GitHub. Esse processo permite que você execute comandos que exigem autenticação, como criar repositórios, gerenciar issues e pull requests.

## Estado dos trabalhos e estados de um arquivo
- `git status`- Verificar o estado do seu repositório. É uma boa prática verificar antes de fazer commits para garantir que você está ciente de todas as alterações feitas.
- `git diff` - Usado para mostrar as diferenças entre várias versões dos arquivos em um repositório Git
- `git diff --staged` - é usado para mostrar as diferenças entre o que está na área de staging e o último commit. Em outras palavras, ele exibe as alterações que você adicionou à área de staging, mas que ainda não foram comitadas.

## Desfazendo mudanças de estados 
-  `git restore --staged nome do arquivo` - Usado para remover um arquivo da área de staging, movendo-o de volta para o diretório de trabalho. Isso significa que as alterações feitas nesse arquivo ainda estarão lá, mas não estarão mais preparadas para o próximo commit

## Arquivo gitignore e testes 
- `git add .gitignore`, `git commit -m "arquivo .gitignore"` - Adiciona e da nome ao arquivo .gitignore"
- O arquivo `.gitignore` é utilizado para especificar quais arquivos ou diretórios o Git deve ignorar, ou seja, que não devem ser rastreados pelo sistema de versionamento. Ele é importante para garantir que todos os colaboradores do projeto também tenham as mesmas configurações de arquivos a serem ignorados.

## Buscando atualizações no repositório remoto
- `git fetch`- Utiliazado para baixar as atualizações do repositório remoto para o seu repositório local. Isso inclui novas branches, commits e tags que foram adicionados ao repositório remoto, mas não altera sua cópia local do código.
- `git log --oneline main..origin/main`- Esse comando exibe uma lista de commits que estão presentes na branch `origin/main` (a versão remota da branch `main`) mas não estão na sua branch local `main`. A opção `--oneline` formata a saída para mostrar apenas o hash abreviado do commit e a mensagem, tornando-a mais concisa.
- `git diff main origin/main` - Este comando compara as diferenças entre sua branch local `main` e a branch remota `origin/main`. Ele mostrará as alterações que foram feitas no repositório remoto que ainda não estão na sua branch local. A saída incluirá as linhas que foram adicionadas, removidas ou modificadas.
 
## Resolve conflitos
- `git pull --rebase` - Atualiza sua branch local aplicando suas mudanças em cima das alterações do remoto, mantendo um histórico mais limpo.
- `git rebase --continue`- Continua o rebase após a resolução de conflitos, aplicando as mudanças restantes..

## Salva o trabalho temporariamente
- `git stash --message="meu primeiro stash"` - Usado para guardar temporariamente suas alterações não comitadas, permitindo que você limpe seu diretório de trabalho sem perder suas mudanças. O parâmetro --message permite que você adicione uma mensagem descritiva ao stash, facilitando a identificação posterior.
- `git stash list`- Esse comando exibe uma lista de todos os stashes criados. Cada stash é identificado por um índice, que pode0 ser usado para referenciá-lo mais tarde.
- `git stash pop` - É usado para aplicar as alterações do stash mais recente ao seu diretório de trabalho e, em seguida, remover esse stash da lista

## Trabalhando em times organizadamente - Fluxo a ser seguido
- `git fetch` - Baixa as atualizações do repositório remoto para o seu repositório local, mas não faz merge nem rebase. Isso permite que você veja as mudanças que ocorreram no remoto sem alterar seu diretório de trabalho
- `git stash` -  Guarda temporariamente suas alterações não comitadas, limpando seu diretório de trabalho. Isso é útil se você precisar atualizar seu repositório e não quiser perder suas mudanças.  `git pull` - Puxa as alterações do repositório remoto e as integra à sua branch local. Isso garante que você esteja trabalhando com a versão mais recente do código.
- `git stash pop` - Aplica as alterações que você havia guardado no stash e remove esse stash da lista. Isso traz de volta suas modificações após a atualização do repositório.
- `git add .` - Adiciona todas as mudanças no seu diretório de trabalho à área de staging, preparando-as para serem comitadas.
- `git commit -m "commit trabalhando em equipe"` - Cria um novo commit com as mudanças que você adicionou à área de staging. A mensagem descreve o que foi alterado.
- `git push` - Envia seus commits locais para o repositório remoto, atualizando a branch correspondente no remoto com suas mudanças.
- `git stash drop` - Remove um stash específico da lista, liberando espaço. Isso é útil se você não precisar mais de um stash que foi guardado

## Revertendo o commits
- `git diff [penúltimo commit] [último commit]` - Mostra as diferenças entre dois commits específicos.
- `git revert [commit a ser revertido]` - Cria um novo commit que desfaz as alterações de um commit anterior.
- `git show [codigo commit reversão]` - Exibe detalhes sobre um commit específico, incluindo as alterações revertidas.

## Histórico do projeto 
- `git checkout [código do commit]` - O comando git checkout [código do commit] é usado para mudar o HEAD do seu repositório para um commit específico. Isso permite que você visualize o estado do repositório naquele commit sem alterar a branch atual.
- `git checkout main` - O comando git checkout `main` é usado para mudar para a branch main (ou `master`, dependendo do nome da sua branch principal).

## Criando branchs 
- `git branch primeiro-branch` - Cria uma nova branch chamada `primeiro-branch`.
- `git branch --list` - Exibe todas as branches disponíveis no repositório local.
- `git switch primeiro-branch`- Muda para a branch `primeiro-branch`. `git status` - Mostra o estado atual do repositório.
- `git switch main` - Muda para a branch main.
- `git push origin primeiro-branch` - Envia a branch primeiro-branch para o repositório remoto.

## Unindo branchs 
- `git switch main` - O comando `git switch main` é usado para mudar para a branch `main`. O `git switch` é uma maneira mais recente e intuitiva de alternar entre branches, introduzida para simplificar o uso do `git checkout`. Em resumo muda para a branch `main`.
- `git merge primeiro-branch`, `git push` - é usado para unir as alterações da branch primeiro-branch na branch atualmente ativa (que, neste caso, é main, após o comando anterior).Após o merge, o comando `git push` é usado para enviar as alterações resultantes para o repositório remoto.
- `git push origin --delete primeiro-branch` -Este comando é usado para deletar a branch ` primeiro-branch` no repositório remoto (`origin`). Isso é útil quando você já uniu as alterações da branch e não precisa mais dela.
- `git branch -d primeiro-branch` - É usado para excluir a branch `primeiro-branch ` localmente.

## Resolvendo conflitos de merge 
- `git branch conflito` - Esse comando cria uma nova branch chamada `conflito`. Essa é uma prática comum quando você antecipa que pode haver conflitos ao tentar unir branches
- `git switch conflito` - O comando `git switch conflito` é usado para mudar para a branch `conflito` que você acabou de criar. Isso permite que você trabalhe nessa branch para resolver os conflitos.
<p>Esses passos são úteis para isolar e resolver conflitos sem afetar outras partes do projeto. Se houver conflitos após um merge, você pode usar essas branches para gerenciar e resolver as alterações de forma controlada</p>

 ## Usando tags 
- `git tag v1.0 -m "primeira versão"` - Cria uma nova tag v1.0 com uma mensagem.
- `git push --tags` - Envia todas as tags locais para o repositório remoto.
- `git tag v0.1 [codigo commit] -m "versão beta"` - Cria uma tag v0.1 em um commit específico com uma mensagem.
- `git checkout v0.1` - Muda para o estado do repositório associado à tag v0.1.
- `git tag -d [nome da tag]` - Remove uma tag localmente.
- `git push --delete [nome do repositório remoto] [nome da tag]` -Remove uma tag do repositório remoto.

<p>Passo a passo da aula disponivel em: https://github.com/joaovictorino/git-github</p>
