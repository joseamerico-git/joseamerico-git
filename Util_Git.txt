tutorial git hub

crie uma pasta abra a pasta no terminal

//cria um repositório
git init


//obtenha um repositório
//crie uma cópia de trabalho em um repositorio local

git clone /caminho/para/o/repositório

//se usar um servidor remoto 
git clone usuário@servidor:/caminho/para/o/repositório

//Estrutura básica do fluxo de trabalho com Git 
//INDEX, HEAD, WORKING DIR

//*****Arvore******

// 1 - WORKING-DIRECTORY (Pasta onde contém os arquivos vigentes).
// 2 - INDEX (Área temporaria ).
// 3 - Head (Aponta para o ultimo commit)

//adicionar arquivo ao index
git add [nome do arquivo]
git add *

// para confirmar as mudanças e enviar para o head para o git remoto
git commit -m "comentários das alterações" //obs ainda não enviamos os alterações para o arquivo remoto somente ao HEAD

//Enviando os arquivos para seu repositório remoto
git push origin master

//Se não clonamos um repositório existente e queremos nos conectar seu repositório a um servidor remoto
git remote add origin <servidor>

/*

Branches (Ramos)
Ramificando
Onde Branche master é o branch padrão quando criamos um repositório
Use outros branches para desenvolver e mescle-os (merge) ao branch master após a conclusão.

*/

//criando um novo branch
git checkout -b [nome do branch]
git checkout -b funcionalidade_x

//retorne para o branch master 
git checkout master

//removendo um brach 
git branch -d funcionalidade_x

/*
um branch não está disponível a outros a menos que você envie o branch para seu repositório remoto

*/
git push origin <funcionalidade_x>

//atualizar seu repositório local com a mais nova versão git pull na sua pasta de trabalho para obter e fazer merge alteraçoes remotas
git pull
//para fazer merge de um outro brach ao brach ativo 
git merge branch


/*
em ambos os casos o git tenta fazer o merge das alterações automaticamente. Infelizmente, isto nem sempre é possível e resulta em conflitos. Você é responsável por fazer o merge estes conflitos manualmente editando os arquivos exibidos pelo git. Depois de alterar, você precisa marcá-los como merged com
git add <arquivo>
antes de fazer o merge das alterações, você pode também pré-visualizá-as usando
git diff <branch origem> <branch destino>

é recomendado criar rótulos para releases de software. Este é um conhecido conceito, que também existe no SVN. Você pode criar um novo rótulo chamado 1.0.0 executando o comando
git tag 1.0.0 1b2e1d63ff
o 1b2e1d63ff representa os 10 primeiros caracteres do id de commit que você quer referenciar com seu rótulo. Você pode obter o id de commit com
git log
você pode também usar menos caracteres do id de commit, ele somente precisa ser único.

*/ 

//Alterações locais

//sobrescrever alterações locais alterações na sua árvore de trabalho com o conteúdo mais recente no HEAD
git checkout -- <arquivo>

//Alterações 
//substitui alterações locais com conteudo do HEAD
git checkout -- <arquivo>

//Recuperar os arquivos contidos no head substituindo todas as alterações locais recuperar histórico mais recente
git fetch origin
git reset --hard origin/master

//interface gráfica padrão do git 
gitk
//saidas do git coloridas
git config format.pretty oneline
//inclusões interativas 
git add -i

