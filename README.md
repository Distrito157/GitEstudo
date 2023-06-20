# Índice
+ [Repositório Git](#repgit)
+ [Configuração do Git](#configgit)
+ [Fluxo de trabalho básico](#fluxotrabalho)
+ [Ramificação e Mesclagem](#ramificamescla)
+ [Resolução de conflitos](#resolucaoconflitos)
+ [Desfazendo alterações](#desfazendoalts)
+ [Trabalhando com repositórios remotos](#trabalhoremoto)
+ [Tags](#tags)
+ [Gitignore](#gitignore)
+ [Rebase](#rebase)
+ [Git Stash](#gitstash)
+ [Git Hooks](#githooks)
+ Git Bisect
+ Cherry-pick
+ Submódulos do Git
+ Reflog
+ Subtrees do Git
+ Git LFS (Large File Storage)
+ Git Attributes
+ Hooks de Preparação e Comprovação
+ Anotação de linhas (Blame/Annotation)
+ Logs personalizados
+ Git refspecs
+ Aliases personalizados
+ Worktrees
+ Rastreamento de alterações (Change Tracking)
+ Bisect automático
+ Filtros de limpeza (Clean Filters)
+ Hooks de atualização (Update Hooks)
+ Estratégias de Mesclagem (Merge Strategies)
+ GPG (Assinaturas e Verificações)
+ Subcomandos avançados (e.g., cherry, rebase -i, blame -C, bisect --skip)

Esses são alguns dos fundamentos do Git, abrangendo desde os conceitos básicos até tópicos mais avançados. Lembre-se de que o Git é uma ferramenta poderosa e flexível, e quanto mais você explorar esses fundamentos, mais habilidades e conhecimentos adquirirá.

# <a name="#repgit"></a>Repositório Git

Um repositório Git é um local onde todas as versões e histórico de um projeto são armazenados. Ele contém todos os arquivos, diretórios e metadados relacionados ao projeto. O repositório Git mantém um registro completo de todas as alterações feitas ao longo do tempo, permitindo que os desenvolvedores acompanhem o progresso do projeto e revertam para versões anteriores, se necessário.

Existem dois tipos principais de repositórios Git:

1. **Repositório Local**: É o repositório que está no seu computador. Você pode criar um repositório local usando o comando `git init` em um diretório vazio. Ele conterá todas as informações do projeto e seu histórico de alterações.

2. **Repositório Remoto**: É um repositório hospedado em um servidor remoto, como [GitHub](https://github.com/), [GitLab](https://about.gitlab.com/) ou [Bitbucket](https://bitbucket.org/). Os repositórios remotos são usados para colaboração entre desenvolvedores e para compartilhar o código-fonte do projeto com outras pessoas. Você pode clonar um repositório remoto para criar uma cópia local em seu computador usando o comando `git clone`.

### Exemplo de criação de um repositório Git local:

1. Abra o terminal ou prompt de comando e navegue até o diretório do seu projeto.
2. Execute o comando `git init` para inicializar um repositório Git vazio.
3. Adicione os arquivos do projeto ao repositório usando o comando `git add`.
4. Faça um commit das alterações usando o comando `git commit -m "Mensagem do commit"`.

### Exemplo de clonagem de um repositório Git remoto:

1. Abra o terminal ou prompt de comando e navegue até o diretório onde deseja clonar o repositório.
2. Execute o comando `git clone URL_DO_REPOSITORIO` (substitua `URL_DO_REPOSITORIO` pela URL real do repositório remoto).
3. O Git irá clonar o repositório remoto para o seu computador, criando uma cópia local completa.

Lembre-se de que o Git armazena todas as versões e alterações no histórico de commits, permitindo que você acesse facilmente versões anteriores do projeto e compare as diferenças entre elas. Isso torna o repositório Git uma poderosa ferramenta para gerenciar e controlar o desenvolvimento de software.

