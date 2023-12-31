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

# <a name="repgit"></a>Repositório Git

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

# <a name="configgit"></a>Configuração do git

A configuração do Git permite que você personalize o comportamento e as opções do Git de acordo com suas preferências e necessidades. Existem diferentes níveis de configuração, desde configurações específicas do usuário até configurações específicas do projeto.

1. **Configuração do usuário**: Essas configurações são aplicadas globalmente e se aplicam a todos os repositórios em seu sistema. Você pode definir seu nome de usuário, endereço de e-mail e outras opções usando os seguintes comandos:
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@example.com"
```
2. **Configuração do repositório**: Essas configurações são específicas para um repositório em particular e substituem as configurações globais quando definidas. Para configurar opções específicas de um repositório, navegue até o diretório do repositório e execute os seguintes comandos:
```bash
git config user.name "Seu Nome"
git config user.email "seuemail@example.com"
```
3. **Visualizando as configurações**: Para visualizar as configurações atuais, você pode usar o seguinte comando:
```bash
git config --list
```
4. Outras configurações: Além das configurações básicas de usuário e e-mail, existem várias outras opções de configuração disponíveis no Git. Algumas configurações comuns incluem a definição de um editor de texto padrão para mensagens de commit, a configuração de alias para comandos frequentemente usados e a definição de opções de merge e diff. Você pode explorar essas configurações e mais detalhes na documentação oficial do Git. 

# <a name="fluxotrabalho"></a>Fluxo de trabalho básico no Git

1. **Inicialização do repositório**: Comece criando um repositório Git para o seu projeto. Isso pode ser feito usando o comando `git init` em um diretório vazio ou clonando um repositório existente usando o comando `git clone`.
2. **Adicionar arquivos**: Adicione os arquivos do seu projeto ao repositório Git usando o comando `git add`. Você pode adicionar arquivos individualmente ou usar curingas para adicionar vários arquivos de uma só vez.
```bash
git add arquivo1.txt     # Adiciona um arquivo específico
git add pasta/           # Adiciona todos os arquivos dentro de uma pasta
git add .                # Adiciona todos os arquivos e pastas no diretório atual
```
3. **Realizar um commit**: Depois de adicionar os arquivos, você precisa fazer um commit para registrar as alterações no repositório Git. Um commit é uma confirmação das alterações realizadas. Use o comando `git commit` para criar um commit com uma mensagem descritiva.
```bash
git commit -m "Mensagem descritiva do commit"
```
4. **Trabalhando com branches**: O uso de branches permite que você trabalhe em diferentes linhas de desenvolvimento separadas. É uma boa prática criar um branch separado para cada nova funcionalidade ou correção de bug. Use o comando `git branch` para criar um novo branch e o comando `git checkout` para alternar entre os branches existentes.
```bash
git branch novo-branch     # Cria um novo branch
git checkout outro-branch  # Alterna para outro branch
```
5. **Mesclar branches**: Após desenvolver uma funcionalidade em um branch separado, você pode mesclar suas alterações de volta ao branch principal usando o comando `git merge`.
```bash
git checkout branch-principal   # Alterna para o branch principal
git merge novo-branch           # Mescla as alterações do novo branch
```
6. **Atualizar o repositório remoto**: Se você estiver trabalhando com um repositório remoto, como o GitHub, é importante manter o repositório remoto atualizado com as alterações locais. Use o comando `git push` para enviar seus commits para o repositório remoto.
```bash
git push origin branch-principal   # Envia os commits para o branch principal no repositório remoto
```
7. **Atualizar o repositório local**: Para obter as alterações feitas por outras pessoas em um repositório remoto, você pode usar o comando `git pull` para buscar e mesclar as alterações para o seu repositório local.
```bash
git pull origin branch-principal   # Obtém e mescla as alterações do branch principal no repositório remoto
```

# <a name="ramificamescla"></a>Ramificação e mesclagem
A ramificação e mesclagem (branching and merging) é uma funcionalidade fundamental do Git que permite que você trabalhe em diferentes linhas de desenvolvimento independentes e integre as alterações de volta ao branch principal quando estiverem prontas. Isso permite que você desenvolva novas funcionalidades, corrija bugs ou experimente alterações sem interferir no código principal.

Aqui está uma explicação detalhada de como funciona a ramificação e mesclagem no Git:
1. **Criar um novo branch**: Para começar a trabalhar em uma nova funcionalidade ou correção de bug, você pode criar um novo branch separado usando o comando `git branch`.
```bash
git branch novo-branch     # Cria um novo branch chamado "novo-branch"
```
Isso cria uma cópia exata do branch atual, incluindo todos os commits anteriores.

2. **Alternar para o novo branch**: Use o comando `git checkout` para alternar para o novo branch e começar a fazer alterações nele.
```bash
git checkout novo-branch   # Alterna para o branch "novo-branch"
```
Agora você está trabalhando no novo branch e pode fazer commits nele sem afetar o branch principal.

3. **Fazer as alterações**: Faça as alterações desejadas nos arquivos do projeto no novo branch. Adicione, modifique ou exclua arquivos conforme necessário.
```cpp
// Faça as alterações necessárias nos arquivos
```
4. Fazer commits no novo branch: Use o comando `git commit` para criar commits das alterações feitas no novo branch. Cada commit representa uma etapa ou conjunto de alterações lógicas.
```bash
git commit -m "Mensagem descritiva do commit"
```
Continue fazendo commits à medida que você progride no trabalho no novo branch.

5. **Mesclar alterações**: Quando você achar que o trabalho no novo branch está concluído e pronto para ser integrado ao branch principal, você pode mesclar as alterações usando o comando `git merge`. Volte para o branch principal usando `git checkout` e execute o comando `git merge` para mesclar as alterações do novo branch.
```bash
git checkout branch-principal   # Alterna para o branch principal
git merge novo-branch           # Mescla as alterações do novo branch
```
O Git tentará mesclar automaticamente as alterações do novo branch com o branch principal. Se houver conflitos, o Git indicará as áreas conflitantes e você precisará resolvê-las manualmente.

6. **Resolver conflitos**: Resolver conflitos: Se ocorrerem conflitos durante a mesclagem, você precisará resolvê-los manualmente. O Git marcará as áreas conflitantes nos arquivos com sinais de marcação especiais. Edite os arquivos para resolver os conflitos, removendo as marcações e mantendo apenas as partes corretas.
```cpp
// Resolva os conflitos nos arquivos
```
Após resolver os conflitos, faça um novo commit para registrar a resolução dos conflitos.

7. **Remover branch**: Depois que as alterações do novo branch forem mescladas com sucesso ao branch principal, você pode remover o novo branch se não precisar mais dele. Use o comando `git branch -d` para remover o branch.
Isso não afeta os commits que foram mesclados no branch principal.


A ramificação e mesclagem permite que você trabalhe de forma colaborativa em projetos, permitindo que cada pessoa trabalhe em seu próprio branch sem interferir no trabalho dos outros. Isso facilita o gerenciamento de alterações, o teste de funcionalidades independentes e a resolução de conflitos antes de integrar as alterações ao branch principal.

É importante ter cuidado ao mesclar os branches, pois conflitos podem ocorrer se várias pessoas modificarem as mesmas partes dos arquivos. Sempre revise as alterações e teste-as cuidadosamente antes de mesclar os branches.
