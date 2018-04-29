---
layout: post
title: Git e GitHub
date: 2018-04-27 16:50:00 +0300
description: Sistema de controle de versão distribuído e suas funcionalidades.
img: git-github/git-github.png
tags: [git, github, iniciante, controle de versão, estudos, tutorial]
---
O que é git e como esse sistema ajuda no desenvolvimento em equipe?

# git

  Git é um sistema de controle de versão distribuído e um sistema de gerenciamento de código fonte, com ênfase em velocidade. O Git foi inicialmente projetado e desenvolvido por Linus Torvalds para o desenvolvimento do kernel Linux, mas foi adotado por muitos outros projetos.
  Cada diretório de trabalho do Git é um repositório com um histórico completo e habilidade total de acompanhamento das revisões, não dependente de acesso a uma rede ou a um servidor central.
  O Git é um software livre, distribuído sob os termos da versão 2 da GNU General Public License. Sua manutenção é atualmente supervisionada por Junio Hamano.

  > Fonte:[Wikipédia](https://pt.wikipedia.org/wiki/Git)

  O projeto do Git é uma síntese da experiência de Torvalds com a manutenção do desenvolvimento altamente distribuído do projeto do Linux, junto com seu íntimo conhecimento de performance de sistemas de arquivos (conhecimentos adquiridos no mesmo projeto) e a necessidade urgente de produzir um sistema funcional em um curto espaço de tempo.

  Outra propriedade do Git é que ele salva o estado (snapshot) dos diretórios de arquivos. Os sistemas mais antigos de controle de versão de código fonte, Sistemas de Controle de Código Fonte (SCCF) e Sistemas de Controle de Revisão (SCR), trabalhavam em cima de arquivos individuais, enfatizando o espaço em disco ganho por intercalação de deltas (SCCF) ou por codificação de deltas (RCS) entre versões (mais similares). Sistemas de controle de versão posteriores mantiveram esta noção de arquivos possuírem uma identidade através de múltiplas revisões de um projeto. Porém, Torvalds rejeitou esse conceito.[29] Consequentemente, o Git não salva relacionamentos entre revisão de arquivos em nenhum nível abaixo da árvore de diretório do código fonte.

  ![git]({{site.baseurl}}/assets/img/git-github/git.png)

## Instalando o Git em nosso sistema operacional

  A instalação do git, é diferente para cada sistema operacional, por isso indico que siga o site oficial:

  [Instalação git](https://git-scm.com/downloads)

  Com o git instalado, precisamos criar uma conta em alguma plataforma de hospedagem de código-fonte, onde teremos acesso visual ao que está no git. Há diversas platafrmas de hospedagem, entre elas as mais conhecidas Bitbucket, GitHub e gitLab. Neste Post, colocarei como criar uma conta no GitHub, visto que é a plataforma mais usada e conhecida no momento.

  GitHub é uma plataforma de hospedagem de código-fonte com controle de versão usando o Git. Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo. GitHub é amplamente utilizado por programadores para divulgação de seus trabalhos ou para que outros programadores contribuam com o projeto, além de promover fácil comunicação através de recursos que relatam problemas ou mesclam repositórios remotos (issues, pull request).

![GitHub]({{site.baseurl}}/assets/img/git-github/github.png)

## Criando nossa conta no GitHub

  Para criar uma conta no Github, basta acessar o site [github.com](https://github.com/) e preencher o formulário principal com as informações pedidas.

  ![Formulário de cadastro GitHub.]({{site.baseurl}}/assets/img/git-github/github1.png)

  Minha recomendação nessa parte, é colocar um nome de usuário legal. Queseja fácil e ler e acessar, pois esse username, será utilizado em currículos e LinkedIn.

  ![Imagem de criação de um usuário de exemplo.]({{site.baseurl}}/assets/img/git-github/github-form.png)

  Será necessário informar, qual tipo de plano de uso queremos utilizar, nesse exemplo utilizarei a opção **free**.

  ![Tela de configuração de plano de uso do GitHub]({{site.baseurl}}/assets/img/git-github/github-plano.png)

  O GitHub vai perguntar algumas coisas antes de finalizar a configuração da sua conta para coleta de dados para melhoria da plataforma, podemos responder ou pular para a próxima tela.

  ![Tela de confirmação de criação de conta do GitHub.]({{site.baseurl}}/assets/img/git-github/github-confirm.png)

  Antes de criarmos o primeiro repositório, vamos configurar o usuário e email que usamos para criar nossa conta no GitHub no Git em nossa máquina.

## Configurando o Git com nossos dados do GitHub

  Execute o seguinte comando, colocando entre aspas o seu nome de usuário do GitHub:

  > git config --global user.name "Nome de usuário do GotHub"

  Configure também entre aspas, o email que foi cadastrado no GitHub:

  > git config --global user.email "email@provedor.com"

## Configurando nossa chave de acesso ao GitHub

  Sempre que vamos acessar um repositório hospedado no GitHub via terminal é necessário que tenhamos permissão de acesso e que façamos login. Para que não tenhamos que logar toda vez que queremos enviar algo para um repositório, utilizamos uma chave SSH. Uma chave de acesso que o GitHub consulta quando necessário.

  Para criar essa chave, siga o documento do próprio GitHub:

  [adicionando chave SSH](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

  Com o git e GitHub configurados, agora sim, podemos partir p/ prática.

## Nosso fluxo de trabalho com Git, GitHub e Terminal

  Uma regra legal é toda vez que for começar um projeto, seja em HTML, Node.js ou qualquer linguagem, é criar um repositório, clonar esse repositório em nossa máquina, trabalhar nele usando branches e fazer pequenos commits para enviar para o GitHub.

  Isso vai nos garantir alguma experiência que precisamos para utilizar essas ferramentas no dia-a-dia.

  Vamos começar.

### Criando um novo projeto

  Acesse sua conta no GitHub e clique no ícone de **mais(+)**no topo da página.

  ![Iniciando repositírio no GitHub]({{site.baseurl}}/assets/img/git-github/github01.png)

  Clique em **New repository.**

  Vamos imaginar que nosso projeto é para estudar HTML, então vou colocar esse nome no repositíro: aprendendo-html. Esse nome pode ser qualquer um de sua escolha, entretanto, temos como boa prática usar nomes curtos e que sejam de fácil compreensão.

  A descrição doprojeto é opicional, porém é bem interessante que se coloque um boom texto nessa parte, pois é o que irá identificar o que faz o seu projeto e outras pessoas podem querer te ajudar. Nesse nosso exemplo, vamos apenas colocar a frase "Repositório de estudos da linguagem HTML".

  ![Imagem dos campos de criação  do repositório preenchidos.]({{site.baseurl}}/assets/img/git-github/github02.png)

  Podemos criar o repositório com um README ou já informando qual a licença de uso do projeto, então dê uma olhada em bons exemplos de READMEs, nesse link: [README-Template.md](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2). E também a licensa que utilizará em seu projeto: [Choose an open source license](https://choosealicense.com/). Os exemplos são em inglês, mas podemos utilizar alguma ferramenta para traduzir para sua linguagem de preferência.

### Criando uma pasta de trabalho em nosso sistema operacional

  Com o nosso repositório criado, agora devemos clonar ele em nossa máquina, mas antes disso, vamos criar uma pasta onde clonaremos todos os futuros repositórios em que formos trabalhar.

  Se você estiver utilizando Windows, recomendo a instalação do cmder para utilizar no lugar do CMD, o terminal padrão do Windows. Assim os comandos serão padronizados e esse tutorial continuará servindo pra você.

  [![cmder](http://cmder.net/img/main.jpg)](http://cmder.net/)

  Vamos utilizar o terminal para criar uma pasta que será nosso workspace (local de trabalho). Fazemos isso para manter uma organização no sistema operacional, senão vamos perder nossos projetos espalhados por aí, assim como perdemos gifs de gatinhos que salvamos em nosso computador.

  Escolha uma pasta para guardar seus projetos, e será nesta pasta que iremos clonar nossos projetos.

### Clonando o repositório

  Seguindo no nosso exemplo, do repositório aprendendo-html, será necessário, agora, clonar ele dentro da pasta escolhida para armazenar nossos projetos. Para isso, digitamos no terminal o caminho do da pasta escolhida:

  > cd ~/projetos

  Agora podemos clonar o projeto. Para isso, vamos pegar o link no GitHub.

  O link está naquele botão de download que fica listado em nosso repositório criado:

  ![Botão de clone  ou download do nosso repositório no GitHub.]({{site.baseurl}}/assets/img/git-github/github03.png)

  Mude de **HTTPS** para **SSH**, pois já configuramos uma chave de acesso a nossa conta no GitHub.

  ![Mudando para SSH.]({{site.baseurl}}/assets/img/git-github/github04.png)

  Agora basta rodar o comando "git clone" e o link para o repositório. Exemplo:

  > git clone git@github.com:eusouumexemplo/aprendendo-html.git

  Podemos acessar a pasta do repositório Git com o comando cd. E então podemos começar a trabalhar nele.

  No nosso exemplo seria cd aprendendo-html.

### Criando uma branch

  Toda vez que formos alterar algo em um projeto versionado com o Git, vamos criar uma branch com o nome da tarefa que estamos fazendo. Para isso utilizamos o comando git checkout -b nome_da_tarefa.

  Feito isso, estaremos na branch que acabamos de criar e podemos, então, começar a codar loucamente.

  ![Gato codando loucamente.]({{site.baseurl}}/assets/img/git-github/tenor.gif)

### Fazendo o commit

  Sempre que finalizarmos alguma alteração, vamos criar um commit. Imagina que você acabou de criar uma página HTML e adicionou títulos e alguns textos nessa página. Teóricamente temos a primeira versão dela. Então fazemos um commit.

  Para isso, vamos adicionar os arquivos alterados com o comando git add nome_dos_arquivos e para saber quais foram os arquivos alterados, podemos rodar o comando git status.

  Com isso teríamos algo para commitar. Então basta rodar o comando git commit -m "mensagem de commit". Lembre-se de colocar uma mensagem descritiva do que foi adicionado com o commit.

### Fazendo o merge

  Com o nosso commit feito a nossa nova branch temos uma versão diferente da master. Podemos confirmar que estamos com diferença entre master e nossa branch rodando o seguinte comando (ainda na branch nova):

  >git diff master

  No nosso exemplo, isso resultaria em uma saída desse tipo:

  ![Saída do git diff na minha branch comparada com a master]({{site.baseurl}}/assets/img/git-github/github05.png)

  O Git nos mostra o novo commit, quais arquivos foram adicionados ou alterados e também mostra o que foi alterado.

  Sabendo que, realmente, nossa branch nova está com diferenças da master, precisaremos fazer um **merge** para **juntar** os novos commits, feitos na nova branch, com a master. Para isso precisamos voltar para a master e rodar o comando "git merge".

  Para voltar para a master, usamos o comando "git checkout master" e para fazer o merge, o comando "git merge nome_da_branch".

  O Git nos mostrará uma saída confirmando o que foi adicionado.

### Enviando para o GitHub

  Com todas as nossas alterações devidamente feitas, podemos, agora, enviar para o GitHub.

  Utilizamos o comando "git push origin master" para tal.

  Também poderíamos rodar somente um "git push".

  Com isso nosso commit irá aparecer no GitHub:

### Conclusão

  Com esse tutorial, podemos, sempre que formos estudar algo novo, criar um projeto de estudos no GitHub. Isso vai nos ajudar a treinar a linha de comando, Git e GitHub, além de criar um portfólio para mostrarmos em entrevistas de emprego.

  Essa prática também nos ajuda a entender melhor o fluxo de uso do Git com repositórios remotos (os repositórios hospedados em alguma plataforma como o GitHub) e elevará nosso nível de conhecimento e habilidades no terminal.

  Vamos reforçar o combinado: sempre que você for criar um novo projeto de estudos, volte aqui e siga o passo a passo de criação de um novo repositório e trabalhe com branches e commits até o push para o GitHub, ok? :)
