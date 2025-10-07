# Git: Sistema de Control de Versions (VCS)

## Definició i Propòsit
- Sistema de control de versions (VCS)
- Controlar canvis
- Facilitar el treball col·laboratiu en programari OpenSource i projectes privats
- Creat per Linus Torvalds (creador del Kernel de Linux)

## Concepte Clau
- Historial complet i organitzat de canvis
- Permet diferents versions, anàlisi i retorn
- Distribuït: cada desenvolupador té una còpia completa
- Repositoris locals i remots
- Branch (Branca): línia de desenvolupament alternativa
- Commit: Punt concret en el temps amb informació i canvis
- [Checkout / Switch](https://kodekloud.com/blog/git-switch-vs-checkout/): Passar a un punt de treball independent (legacy vs v2.23)
- Merge: Unió de canvis entre branques
- Stash: Guardar canvis per recuperar-los més tard
- HEAD: Punt actual al qual es troba el repositori

## Avantatges
- Historial complet i recuperable de canvis
- Treball en equip de manera simultània
- Permet tornar enrere si hi ha errors
- Facilita l’experimentació amb branques independents

## Configuració Inicial
- `git config --global user.name "el teu nom"`
- `git config --global user.email "el teu@correu.com"`
- `git config --list` (per veure configuració actual)
- `git config --global core.editor "nom_editor"`
- `git config --global core.autocrlf true` (Windows)
- `git config --global core.autocrlf input` (Linux/Mac)

## Comandes Bàsiques de Git i Control

### Creació de Repositori
- `git init` (inicialitzar repositori)
- `git status` (veure l’estat actual: Branch, Commits, Staged)
- `git add fitxer` (afegir fitxer a staging area)
- `git add .` (afegir tots els fitxers modificats)
- `git commit -m "Missatge"` (guardar canvis)

### Historial i Canvis
- `git log` (llista de commits)
- `git log --oneline` (historial resumit)
- `git diff` (veure canvis no staged)
- `git diff --staged` (veure canvis staged)
- `git checkout -- fitxer` (tornar a versió anterior)
- `git reset HEAD fitxer` (treure fitxer de l’staging area)

### Branching i Merges
- `git branch` (llista de branques)
- `git branch nom_branca` (crear nova branca)
- `git checkout nom_branca` (canviar a branca)
- `git switch nom_branca` (canviar a branca versio>=2.23)
- `git merge branca` (fusionar branca a l’actual)
- `git branch -d branca` (eliminar branca)

### Repositoris Remots
- `git remote add origin <URL>` (enllaçar a remot)
- `git clone <URL>` (clonar repositori remot)
- `git push origin main` (pujar canvis)
- `git pull origin main` (baixar i fusionar canvis)
- `git fetch` (baixar canvis sense fusionar)

### Desfer Canvis
- `git restore fitxer` (descartar canvis locals)
- `git revert commit_id` (desfer commit creant-ne un de nou)
- `git reset --hard commit_id` (restaurar estat complet)
- `git reset --soft commit_id` (mantenir canvis a staging)

### Altres
- `.gitignore` (fitxer per ignorar arxius i carpetes)
- `git stash` (guardar canvis temporalment)
- `git stash pop` (recuperar canvis guardats)
- `git tag -a v1.0 -m "Versió 1.0"` (crear etiqueta)

## Flux de Treball Comú
- `git init` (crear repositori nou) o `git clone` (clonar un existent)
- `git add` i `git commit` (guardar canvis locals)
- `git push` (enviar canvis al remot)
- `git pull` (sincronitzar amb remot)
- `git branch` i `git merge` (gestió de branques)

## Eines de Treball Grupal
- Pull Request (GitHub/GitLab)
- Fork i contribució a projectes OpenSource
- Revisió de codi i comentaris
- Issues de coordinació
- Automatització amb CI/CD

## Recursos
- [Repositori MoureDev Hello-git](https://github.com/mouredev/hello-git)
- [Repositori ITB Curs Git i GitHub](https://github.com/git-github-curs-xtec/curs-git-i-github/tree/main/Material%20Docent)
- [Llibre: Pro Git (Scott Chacon i Ben Straub)](https://git-scm.com/book/en/v2)
- [GitHub Learning Lab](https://github.com/apps/github-learning-lab)
- [GitHub Codespaces](https://docs.github.com/en/codespaces)
- [GitHub Pages](https://docs.github.com/en/pages)

