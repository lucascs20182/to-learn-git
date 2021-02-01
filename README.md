# **DON'T PANIC**


forka, Raquel ヾ(-_- )ゞ 


Output comentado do history do meu terminal:


#### 1. Commit

```git clone https://github.com/lucascs20182/to-learn-git.git``` //copia o repositório criado no github

```git status``` //verifica a situação do versionamento

```git add index.html``` //adiciona o arquivo para uma espécie de área de preparação

```git add .``` //adiciona tudo para staging

```git status```

```git config --global user.email 'lucascs20182@gmail.com'``` //sem a flag --global a configuração fica apenas para o projeto

```git config --global user.name 'lucascs20182'```

```git commit -m "initial commit"``` //flag -m para passar a mensagem do commit direto no comando, sem abrir o arquivo num editor e depois ter que salvar etc.

```git status```

```git push origin master``` //empurra para o github as alterações da branch master

##### 1.2. What if I've to undo a commit? That is, move last git commit back to unstaged area?
```git reset HEAD^``

##### 1.2. What if I've to commit a manually deleted file or folder?
```git rm object/ -r``` //deleta recursivamente (tag -r) os arquivos da pasta object

```git add .``` //adiciona as demais modificações a staging area

```git commit -m "moving files"```

```git push```

##### 1.3. Como incorporar mudanças no último commit
```git commit --amend``` //se passar mensagem ele sobescrever a que você tinha escrito antes

```git push --force-with-lease```


#### 2. Branch

```git status```

```git log``` //lista últimos commits realizados

```git branch``` //informa branches existentes no projeto

```git branch dev-schedule-component``` //cria branch chamada dev-schedule-component

```git branch```

```git checkout dev-schedule-component``` //muda para branch dev-schedule-component

```git status```

```git add .```

```git commit -m "commit schedule.js da branch dev-schedule-component"```

```git branch -v``` //mostra o último commit realizado

```git push origin dev-schedule-component``` //empurra para o github as alterações da branch dev-schedule-component



#### 3. Merge

```git branch```

```git checkout master```

```git merge dev-schedule-component``` //unifica alterações das 2 branches

```git branch -d dev-schedule-component``` //deleta dev-schedule-component

```git branch```

```git push```



#### 4. SSH

```ssh-keygen``` //caso não queira utilizar pass, apenas dê enter ao ser solicitada

/*

    será criada uma pasta .ssh no diretório do user logado no seu pc.
    
    ex.: /home/nomeDoUsuario no Linux ou C:\users\nomeDoUsuario
    
    e dentro dela, no arquivo id_rsa.pub, terá a chave gerada
    
    que deverá ser adicionada ao github em settings -> ssh and GPG keys -> new SSH key
    
*/


//teste em uma nova pasta

```git clone git@github.com:lucascs20182/to-learn-git.git```



#### 4. Repos remotos

```git remote -v``` //verifica repositórios remotos; há um repositório que foi adicionado pelo git clone


//para adicionar um manualmente

```git remote add rep-learn-git git@github.com:lucascs20182/to-learn-git.git``` //adicionado repositório remoto com nome rep-learn-git

```git push -v rep-learn-git master``` //flag -v para gravar o repo como default e nos próximos pushes apenas dar ```git push```

```git push -v origin master```

```git push```



#### 4. Fetch e Pull

```git fetch origin master``` //cria apontamento com um branch do repo remoto, nesse caso o master

//commite index.html pelo github para criar atualizações que o repo local não tem

```git fetch``` // baixa os commits do repo remoto sem afetar o código local

```git merge origin/master``` //merge com as atualizações recentes do repo remoto

//commite README.md pelo github para criar atualizações que o repo local não tem

```git pull origin master``` //baixa atualizações mais recentes do repo remoto p/ repo local e faz merge automaticamente

// another way: downloads the latest from remote without trying to merge or rebase anything

``` git fetch --all ```

``` git reset --hard origin/master ```



#### 5. Fork

/*

    entre num repositório e clique em fork: faz uma cópia do repositório para o seu github
    
    o que possibilita enviar new pull request - solicitação de um merge com o repositório forkado
    
    
    //atualizando o fork
    ```git remote add upstream https://github.com/tiagor87/unifeso-financial-control``` //adiciona um remote com base na versão original 
       
    ```git fetch upstream``` //atualiza o upstream
    
    ```git merge upstream/master master``` //faz merge do upstream com branch master do projeto local
    
    ``` git push origin master ``` //empurra as modificações para o repo no github
*/
