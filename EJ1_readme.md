# Ejercicio 1

## Preguntas y respuestas

### - ¿Qué comando utilizaste en el paso 11? ¿Por qué?**

```git reset --hard HEAD~1```

Porque quiero mover el puntero Head al commit anterior y deshacer los cambios del staging area, devolviendo en el working area lo que habia en el penutlimo commit.

###  - ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

```git reset --hard 02702cd```

Primero busque con ```git reflog``` la id del commit que habita deshecho para volver a el. Utilice este comando para rehacer los cambios en el staging area y working area.

###  - El merge del paso 13, ¿Causó algún conflicto? ¿Por qué

Si porque styled ya tenía acceso a todos los commits de main

###  - El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

Si porque el archivo había sido modificado en cada rama y los cambios afectaban a las mismas líneas de código.

###  - El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

No, porque no habia archivos modificados y main no tenia acceso a los ultimos commits de la rama styled

###  - ¿Qué comando o comandos utilizaste en el paso 25?

```git log --graph```

###  - El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Si, porque el arbol es lineal

###  - ¿Qué comando o comandos utilizaste en el paso 27?

```git reset HEAD~1```

###  - ¿Qué comando o comandos utilizaste en el paso 28?

```git restore *md```

###  - ¿Qué comando o comandos utilizaste en el paso 29?

```git branch -D title```

###  - ¿Qué comando o comandos utilizaste en el paso 30?

Primero busque la id del commit y luego hice el commando siguiente
```git reset --hard 8ea92e2```

###  - ¿Qué comando o comandos usaste en el paso 32?

Busque la id del commit inicial con ```git reflog``` y luego hice
```git reset --hard d9fadac```

###  - ¿Qué comando o comandos usaste en el punto 33?

Lo mismo que e el 32, busque la id e hice un reset hard 
```git reset --hard 8ea92e2```

## Step by Step

### 1) Crear un repositorio en GitHub y clónalo en tu equipo

<pre>
<span style="color:#74C2FF">@Iv3 Ejercicios % </span>  git clone git@github.com:Iv3tt3/Practica_GIT.git
Cloning into 'Practica_GIT'...
warning: You appear to have cloned an empty repository.
<span style="color:#74C2FF">@Iv3 Ejercicios % </span> % cd Practica_GIT
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> % ls -a
.	..	.git

</pre>

### 2) Crear un archivo git-nuestro.md con el contenido:

Git nuestro

Git nuestro que estas en los repos 

Comprimidos sean tus commits

Venga a nosotros tu log

En el local como en el remote

Danos hoy nuestro pull de cada día

Perdona nuestros conflictos

Como también perdonamos los de otros geeks 

No nos dejes caer en detached HEAD

y líbranos de SVN

git commit --amend

<pre>

<span style="color:#74C2FF">@Iv3 Practica_GIT % </span>  git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git-nuestro.md

nothing added to commit but untracked files present (use "git add" to track)

</pre>

### 3) Añadir git-nuestro.md al staging area

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git add git-nuestro.md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   git-nuestro.md

</pre>

### 4) Mover lo que hay en el staging area al repositorio

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git commit -m "Initial commit git-nuestro.md"
[main (root-commit) 8a0dfe1] Initial commit git-nuestro.md
 1 file changed, 21 insertions(+)
 create mode 100644 git-nuestro.md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean

</pre>

### 5) Crear una rama llamada “styled”

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git branch styled
</pre>

### 6) Listar las ramas que hay en el repositorio

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git branch
* main
  styled
</pre>

### 7) Moverse a la rama “styled”

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout styled
Switched to branch 'styled'
</pre>

### 8) Comprobar que se está en la rama correcta

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git log
commit 8a0dfe1c5205c42b41a66e535a535f20ca13c7ef (HEAD -> styled, main)
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:35:25 2023 +0000

    Initial commit git-nuestro.md
</pre>

### 9) Modificar en el archivo git-nuestro.md:

*Git* nuestro que estás en los repos 

Comprimidos sean tus *commits* 

Venga a nosotros tu *log*

En el local como en el *remote* 

Danos hoy nuestro *pull* de cada día 

Perdona nuestros *conflictos*

Como también perdonamos los de otros geeks

No nos dejes caer en *detached HEAD*

y líbranos de *SVN*

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch styled
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")
</pre>

### 10) Añadir los cambios al staging area y luego pasarlos al repositorio

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git add *md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch styled
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   git-nuestro.md

<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git commit -m "gitnnuestro.md modified styled"
[styled 7954067] gitnnuestro.md modified styled
</pre>


### 11) Deshacer el último commit (perdiendo los cambios realizados en el working copy)

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git reset --hard HEAD~1
HEAD is now at d9fadac Initial commit git-nuestro.md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git log
commit d9fadacc6bde9dee7653a33d38c66f7cb9d0e9cf (HEAD -> styled, main)
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:55:05 2023 +0000

    Initial commit git-nuestro.md
</pre>

### 12) Rehacer el último commit (el que acabamos de deshacer)

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git reflog
d9fadac (HEAD -> styled, main) HEAD@{0}: reset: moving to HEAD~1
02702cd HEAD@{1}: commit: gitnnuestro.md modified styled
d9fadac (HEAD -> styled, main) HEAD@{2}: checkout: moving from main to styled
d9fadac (HEAD -> styled, main) HEAD@{3}: commit (initial): Initial commit git-nuestro.md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git reset --hard 02702cd
HEAD is now at 02702cd gitnnuestro.md modified styled
</pre>

### 13) Hacer un merge con ‘main’ (styled absorbe a main)
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git merge main
Already up to date.
</pre>

### 14) Volver a la rama main
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout main
Switched to branch 'main'
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git log
commit d9fadacc6bde9dee7653a33d38c66f7cb9d0e9cf (HEAD -> main)
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:55:05 2023 +0000

    Initial commit git-nuestro.md
</pre>

### 15) Crear una nueva rama llamada “htmlify”
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git branch htmlify
</pre>

### 16) Cambiar a la rama htmlify
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout htmlify
Switched to branch 'htmlify'
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git log
commit d9fadacc6bde9dee7653a33d38c66f7cb9d0e9cf (HEAD -> htmlify, main)
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:55:05 2023 +0000

    Initial commit git-nuestro.md
</pre>

### 17) Modificar en el archivo git-nuestro.md:
<p><em>Git</em> nuestro que estas en los repos<br /> 

Comprimidos sean tus <em>commits</em><br />

Venga a nosotros tu <em>log</em><br />

En el local como en el <em>remote</em><br />

Danos hoy nuestro <em>pull</em> de cada día<br /> 

Perdona nuestros <em>conflictos</em><br />

Como también perdonamos los de otros geeks<br />

No nos dejes caer en <em>detached HEAD</em><br /> 

y líbranos de <em>SVN</em><br />

<code>git commit --amend</code></p>

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch htmlify
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")

</pre>

### 18) Hacer un commit
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git add *md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch htmlify
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   git-nuestro.md

<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git commit -m "gitnuestro.md modified htmlify"
[htmlify 3859a3d] gitnuestro.md modified htmlify
 1 file changed, 10 insertions(+), 12 deletions(-)
</pre>

### 19) Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout styled
Switched to branch 'styled'
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git merge htmlify
Auto-merging git-nuestro.md
CONFLICT (content): Merge conflict in git-nuestro.md
Automatic merge failed; fix conflicts and then commit the result.
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> 
</pre>

### 20) Si hay conflictos, deberemos resolverlos quedándonos con el contenido de la rama “styled”.
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch htmlify
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git add *md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch htmlify
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   git-nuestro.md

<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git commit -m "gitnuestro.md modified htmlify"
[htmlify 3859a3d] gitnuestro.md modified htmlify
 1 file changed, 10 insertions(+), 12 deletions(-)
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout styled
Switched to branch 'styled'
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git merge htmlify
Auto-merging git-nuestro.md
CONFLICT (content): Merge conflict in git-nuestro.md
Automatic merge failed; fix conflicts and then commit the result.
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch styled
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
	both modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git add *md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch styled
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
	modified:   git-nuestro.md

<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git commit
[styled 6b9a7c3] Merge branch 'htmlify' into styled
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git log
commit 6b9a7c349ecdf7c4b5a27ecf284e90d60fbc2025 (HEAD -> styled)
Merge: 02702cd 3859a3d
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 20:24:12 2023 +0000

    Merge branch 'htmlify' into styled

commit 3859a3d4fd303f0c759bf132bfe6c23c8e7e31bc (htmlify)
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 20:18:30 2023 +0000

    gitnuestro.md modified htmlify

commit 02702cdeb7614ac4915e7316c15601d6c675e208
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:57:31 2023 +0000

    gitnnuestro.md modified styled

commit d9fadacc6bde9dee7653a33d38c66f7cb9d0e9cf (main)
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:55:05 2023 +0000

    Initial commit git-nuestro.md
</pre>

### 21) Desde “main”, hacer un merge con “styled”
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout main
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git merge styled
Updating d9fadac..6b9a7c3
Fast-forward
 git-nuestro.md | 22 ++++++++++------------
 1 file changed, 10 insertions(+), 12 deletions(-)
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> 
</pre>

### 22) Crear una rama “title” y cambiarse a esa rama
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git branch title
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout title
Switched to branch 'title'
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git log
commit 6b9a7c349ecdf7c4b5a27ecf284e90d60fbc2025 (HEAD -> title, styled, main)
Merge: 02702cd 3859a3d
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 20:24:12 2023 +0000

    Merge branch 'htmlify' into styled

commit 3859a3d4fd303f0c759bf132bfe6c23c8e7e31bc (htmlify)
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 20:18:30 2023 +0000

    gitnuestro.md modified htmlify

commit 02702cdeb7614ac4915e7316c15601d6c675e208
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:57:31 2023 +0000

    gitnnuestro.md modified styled

commit d9fadacc6bde9dee7653a33d38c66f7cb9d0e9cf
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:55:05 2023 +0000

    Initial commit git-nuestro.md
</pre>

### 23) Añadir un título (a tu gusto) al archivo git-nuestro.md y hacer un commit.

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git status
On branch title
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git add *md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git commit -m "Title gitnuestro commit"
[title 8ea92e2] Title gitnuestro commit
 1 file changed, 2 insertions(+)
</pre>

### 24) Volver a la rama main
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout main 
Switched to branch 'main'
</pre>

### 25) Dibujar el diagrama
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git log --graph
*   commit 6b9a7c349ecdf7c4b5a27ecf284e90d60fbc2025 (HEAD -> main, styled)
|\  Merge: 02702cd 3859a3d
| | Author: Iv3tt3 <reach.iv3tt3@gmail.com>
| | Date:   Sun Dec 3 20:24:12 2023 +0000
| | 
| |     Merge branch 'htmlify' into styled
| | 
| * commit 3859a3d4fd303f0c759bf132bfe6c23c8e7e31bc (htmlify)
| | Author: Iv3tt3 <reach.iv3tt3@gmail.com>
| | Date:   Sun Dec 3 20:18:30 2023 +0000
| | 
| |     gitnuestro.md modified htmlify
| | 
* | commit 02702cdeb7614ac4915e7316c15601d6c675e208
|/  Author: Iv3tt3 <reach.iv3tt3@gmail.com>
|   Date:   Sun Dec 3 19:57:31 2023 +0000
|   
|       gitnnuestro.md modified styled
| 
* commit d9fadacc6bde9dee7653a33d38c66f7cb9d0e9cf
  Author: Iv3tt3 <reach.iv3tt3@gmail.com>
  Date:   Sun Dec 3 19:55:05 2023 +0000
  
:

</pre>

### 26) Hacer un merge “no fast-forward” de “title” en “main” (main absorbe a title)
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git merge --no-ff title
Merge made by the 'ort' strategy.
 git-nuestro.md | 2 ++
 1 file changed, 2 insertions(+)
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> 
</pre>

### 27) Deshacer el merge (sin perder los cambios del working copy)
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git reset HEAD~1 
Unstaged changes after reset:
M	git-nuestro.md
</pre>

### 28) Descartar los cambios
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git restore *md

</pre>

### 29) Eliminar la rama “title”
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git branch -d title
error: The branch 'title' is not fully merged.
If you are sure you want to delete it, run 'git branch -D title'.
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git branch -D title
Deleted branch title (was 8ea92e2).

</pre>

### 30) Rehacer el merge que hemos deshecho
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git reflog
6b9a7c3 (HEAD -> main, styled) HEAD@{0}: reset: moving to HEAD~1
c543f7e HEAD@{1}: merge title: Merge made by the 'ort' strategy.
6b9a7c3 (HEAD -> main, styled) HEAD@{2}: checkout: moving from title to main
8ea92e2 HEAD@{3}: commit: Title gitnuestro commit
6b9a7c3 (HEAD -> main, styled) HEAD@{4}: checkout: moving from main to title
6b9a7c3 (HEAD -> main, styled) HEAD@{5}: merge styled: Fast-forward
d9fadac HEAD@{6}: checkout: moving from styled to main
6b9a7c3 (HEAD -> main, styled) HEAD@{7}: commit (merge): Merge branch 'htmlify' into styled
02702cd HEAD@{8}: checkout: moving from htmlify to styled
3859a3d (htmlify) HEAD@{9}: commit: gitnuestro.md modified htmlify
d9fadac HEAD@{10}: checkout: moving from main to htmlify
d9fadac HEAD@{11}: checkout: moving from styled to main
02702cd HEAD@{12}: reset: moving to 02702cd
d9fadac HEAD@{13}: reset: moving to HEAD~1
02702cd HEAD@{14}: commit: gitnnuestro.md modified styled
d9fadac HEAD@{15}: checkout: moving from main to styled
d9fadac HEAD@{16}: commit (initial): Initial commit git-nuestro.md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git reset --hard 8ea92e2
HEAD is now at 8ea92e2 Title gitnuestro commit
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> 
</pre>

### 31) Volver a main y eliminar el resto de ramas
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git branch -d styled    
Deleted branch styled (was 6b9a7c3).
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git branch -d htmlify
Deleted branch htmlify (was 3859a3d).
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> 
</pre>

### 32) Volver al commit inicial cuando se creó el poema
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git reset --hard d9fadac
HEAD is now at d9fadac Initial commit git-nuestro.md
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git log
commit d9fadacc6bde9dee7653a33d38c66f7cb9d0e9cf (HEAD -> main)
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:55:05 2023 +0000

    Initial commit git-nuestro.md
</pre>

### 33) Volver al estado final, cuando pusimos título al poema
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git reset --hard 8ea92e2
HEAD is now at 8ea92e2 Title gitnuestro commit
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git log
commit 8ea92e2be237563dcf2fb21bd688d369112e7f24 (HEAD -> main)
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 20:29:22 2023 +0000

    Title gitnuestro commit

commit 6b9a7c349ecdf7c4b5a27ecf284e90d60fbc2025
Merge: 02702cd 3859a3d
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 20:24:12 2023 +0000

    Merge branch 'htmlify' into styled

commit 3859a3d4fd303f0c759bf132bfe6c23c8e7e31bc
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 20:18:30 2023 +0000

    gitnuestro.md modified htmlify

commit 02702cdeb7614ac4915e7316c15601d6c675e208
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:57:31 2023 +0000

    gitnnuestro.md modified styled

commit d9fadacc6bde9dee7653a33d38c66f7cb9d0e9cf
Author: Iv3tt3 <reach.iv3tt3@gmail.com>
Date:   Sun Dec 3 19:55:05 2023 +0000

    Initial commit git-nuestro.md
</pre>

### 34) Crear los siguientes tags:
inicial: en el primer commit
styled: modificación del paso 10 
htmlify: modificación del paso 17-18 
title: modificación del paso 30
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git tag inicial d9fadac
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git tag styled 02702cd
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git tag htmlify 3859a3d                 
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git tag title 8ea92e2
</pre>

### 35) Ir al tag htmlify
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout htmlify
Note: switching to 'htmlify'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 3859a3d gitnuestro.md modified htmlify
</pre>

### 36) Vuelve a la rama main
<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git checkout main
Previous HEAD position was 3859a3d gitnuestro.md modified htmlify
Switched to branch 'main'

</pre>

### 37) Sube a GitHub todas las ramas y todos los tags

<pre>
<span style="color:#74C2FF">@Iv3 Practica_GIT % </span> git push --set-upstream origin main
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 12 threads
Compressing objects: 100% (10/10), done.
Writing objects: 100% (15/15), 1.89 KiB | 967.00 KiB/s, done.
Total 15 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), done.
To github.com:Iv3tt3/Practica_GIT.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

</pre>