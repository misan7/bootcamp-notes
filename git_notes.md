# GIT

# Git basics

## Init a Repository

To inicialize a repository we have to use the command `git init`
This command will create a hidden `.git` sub-folder in the project folder

## Track first changes

First time our files are *untracked*
To start tracking our files we have to `commit` them

For example, if we have an `index.html` created we can start tracking it by doing:

```
git init
git add index.html
git commit -m "first commit"
```

**GIT LOG**: Think of Git's log as a journal that remembers all the changes we've committed so far, in the order we committed them.
```
git log
commit 2c1d85d41ab4477d8fec775f55fad6de6ec4e5d1
Author: Sergio MT <sergio.mt88@gmail.com>
Date:   Tue Apr 11 09:26:47 2017 +0200

    git_basics.md created
```

```
git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   git_basics.md

no changes added to commit (use "git add" and/or "git commit -a")
```

```
git clone https://github.com/Misan7/css3-examples.git
```

```
git add --all
```

```
git push origin master
```

**Updatining a repository**

```
git add fileOrFolder
git commit -m "Update"
git push
```

**Control de versiones:** permite trabajar en equipo y crear repositorios.
**Repositorio:** al inicicializar se puede llevar
**Rama(brunch):** arranca una versión autónoma del proyecto sin modificar la principal.

**git init:** crea una carpeta oculta en la cual podemos ir adelante y atrás. Se ha de hacer de manera horizontal. *A partir de este momento funcionan los comandos GIT*.
**git status**: para comprobar el estado y cambios del git.

**git config**: Enseña los comandos.

**git config -l**: Para añadir datos -> 
$ git config --global user.name "John Doe"
$ git config --global user.email "john@doe.org"
$ git config --global color.ui auto

**git add:** Para hacer un commit de los archivos y carpetas. (p.Ej. git add index.html). Añade a *staging area*.
    - **git add --al**l: añade toda la carpeta y archivos de dentro.

**git commit -m:** Es para comitear los archivos. -m significa mensaje. El mensaje se pone entre comillas "".

**git diff:** salen los cambios en el archivo.

**git log --stat:** para comprobar cambios de forma más austera.

## Creations commands

### Creation directory

#### Creation file