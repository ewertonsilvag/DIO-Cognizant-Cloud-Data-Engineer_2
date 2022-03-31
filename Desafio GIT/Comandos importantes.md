## **Estados**

1. Modificado (modified);
1. Preparado (staged/index)
1. Consolidado (comitted);

## **Ajuda**

git help

## **Configuração**

As configurações do GIT são armazenadas no arquivo .gitconfig localizado dentro do diretório do usuário do Sistema Operacional.

**Exemplos de comando**

**Listar configurações**

    git config --list

**Setar usuário**

    git config --global user.name "Ewerton Gomes"

**Setar email**

    git config --global user.email 'ewertonsilvag@gmail.com'

**OBS:** Meu código não rodou sem as aspas, mas existe a opção também.

## **Repositório Local**

**Criar novo repositório**

	git init

**Verificar estado dos arquivos/diretórios**

	git status

**Adicionar arquivo/diretório (staged area)**

**Adicionar um arquivo em específico**

	git add meu_arquivo.txt

**Adicionar um diretório em específico**

	git add meu_diretorio

**Adicionar todos os arquivos/diretórios**
	
	git add .	

## **Comitar arquivo/diretório**

**Comitar um arquivo**
	
	git commit meu_arquivo.txt

**Comitar vários arquivos**

	git commit meu_arquivo.txt meu_outro_arquivo.txt
	
**Comitar informando mensagem**

	git commit meuarquivo.txt -m "minha mensagem de commit"

## **Remover arquivo/diretório**

**Remover arquivo**

	git rm meu_arquivo.txt

**Remover diretório**

	git rm -r diretorio

## **Visualizar histórico**

**Exibir histórico**
	
	git log
	
**Exibir histórico com diff das duas últimas alterações**

	git log -p -2
	
**Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-))**

	git log --stat

## **Desfazendo operações**

**Desfazendo alteração local (working directory)**
Este comando deve ser utilizando enquanto o arquivo não foi adicionado na **staged area**. 

	git checkout -- meu_arquivo.txt

**Desfazendo alteração local (staging area)**
Este comando deve ser utilizando quando o arquivo já foi adicionado na **staged area**.

	git reset HEAD meu_arquivo.txt

**Se o resultado abaixo for exibido, o comando reset *não* alterou o diretório de trabalho.**

	Unstaged changes after reset:
	M	meu_arquivo.txt

A alteração do diretório pode ser realizada através do comando abaixo:
	
	git checkout meu_arquivo.txt

## **Repositório Remoto**

**Exibir os repositórios remotos**

	git remote
	
	git remote -v

**Vincular repositório local com um repositório remoto**

	git remote add origin git@github.com:leocomelli/curso-git.git
	
**Exibir informações dos repositórios remotos**

	git remote show origin
	
**Renomear um repositório remoto** 

	git remote rename origin curso-git
	
**Desvincular um repositório remoto**
	
	git remote rm curso-git

**Enviar arquivos/diretórios para o repositório remoto**

**O primeiro *push* de um repositório deve conter o nome do repositório remoto e o branch.**

	git push -u origin master
	
**Os demais *pushes* não precisam dessa informação**

	git push
	

## **Atualizar repositório local de acordo com o repositório remoto**

**Atualizar os arquivos no branch atual**

	git pull
	
**Buscar as alterações, mas não aplica-las no branch atual**

	git fetch
	
**Clonar um repositório remoto já existente**

	git clone git@github.com:leocomelli/curso-git.git

## Branches

**O *master* é o branch principal do GIT.**

**O *HEAD* é um ponteiro *especial* que indica qual é o branch atual. Por padrão, o **HEAD** aponta para o branch principal, o *master*.**

**Criando um novo branch**

	git branch nome-branch
	
**Trocando para um branch existente**

	git checkout nome-branch

## Resolver merge entre os branches

	git merge bug-123
	
**Para realizar o *merge*, é necessário estar no branch que deverá receber as alterações. O *merge* pode automático ou manual. O merge automático será feito em arquivos textos que não sofreram alterações nas mesmas linhas, já o merge manual será feito em arquivos textos que sofreram alterações nas mesmas linhas.**

A mensagem indicando um *merge* manual será:

	Automerging meu_arquivo.txt
	CONFLICT (content): Merge conflict in meu_arquivo.txt
	Automatic merge failed; fix conflicts and then commit the result.


**Apagando um branch**

	git branch -d bug-123

### **Listar branches** 

**Listar branches**

	git branch

**Listar branches com informações dos últimos commits**

	git branch -v

**Listar branches que já foram fundidos (merged) com o *master***

	git branch --merged

**Listar branches que não foram fundidos (merged) com o *master***

	git branch --no-merged

### **Criando branches no repositório remoto**

**Criando um branch remoto com o mesmo nome**

	git push origin bug-123

**Criando um branch remoto com nome diferente**

	git push origin bug-123:new-branch

**Baixar um branch remoto para edição**

	git checkout -b bug-123 origin/bug-123


**Apagar branch remoto**

	git push origin:bug-123

## **Rebasing**

**Fazendo o *rebase* entre um o branch bug-123 e o master.**

	git checkout experiment
	
	git rebase master



