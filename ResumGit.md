
# Resum Git i GitHub 

## 1. Git: Sistema de Control de Versions Distribuït

**Git** és el sistema de control de versions (VCS) més utilitzat arreu del món i és essencial per a qualsevol  persona que es dediqui al desenvolupament de software.

### 1.1 Conceptes Fonamentals de Git

*   **Sistema Distribuït:** Git és un sistema distribuït de control de versions. Això significa que cada desenvolupador té una **còpia completa** del codi (l'historial sencer del projecte) a la seva màquina local. Això garanteix que, fins i tot si el servidor remot falla, el treball pot continuar.
*   **Historial i Versions:** Git permet mantenir un historial complet de tot el codi desenvolupat. Cada canvi confirmat (commit) és com una **fotografia o instantània** de l'estat del projecte en un moment exacte del temps.
*   **Avantatges:** Permet emmagatzemar codi, facilita el treball en equip, permet fer *rollbacks* (tornar a versions anteriors sense errors), i ajuda a saber exactament quin *commit* va introduir un error concret.

### 1.2 El Flux de Treball

El flux de treball de Git es basa en tres àrees principals en l'entorn local:

1.  **Directori de Treball (Working Directory):** On es modifiquen, s'afegeixen o s'eliminen arxius.
2.  **Àrea d'Escenificació (Staging Area/Index):** Una etapa intermèdia on es **seleccionen** els canvis específics que es volen incloure en el pròxim *commit* (no tots els canvis han de passar automàticament al repositori).
3.  **Repositori Local (Git Directory):** On s'emmagatzemen els canvis de manera permanent mitjançant els *commits*.

### 1.3 Comandes Essencials de Git (Terminal)

| Categoria | Comanda | Descripció | Referències |
| :--- | :--- | :--- | :--- |
| **Configuració** | `git config --global user.name "Nom"` | Estableix el nom d'usuari de manera global, essencial abans del primer commit. | |
| | `git config --global user.email "correu@mail.com"` | Estableix el correu electrònic de manera global. | |
| | `git init` | Inicialitza un nou repositori Git local en el directori actual, creant la carpeta oculta `.git`. | |
| **Estat** | `git status` | Mostra l'estat actual del directori, indicant arxius sense seguiment (*untracked*) o modificats. | |
| | `git status -s` | Versió abreujada de l'estat. | |
| **Afegir Canvis** | `git add <fitxer>` | Afegeix un fitxer específic a l'Àrea d'Escenificació (Stage). | |
| | `git add .` | Afegeix tots els fitxers sense seguiment o modificats a l'Stage (ús generalment desaconsellat, excepte si s'està 100% segur). | |
| **Confirmar (Commit)** | `git commit -m "Missatge descriptiu"` | Confirma els canvis que es troben a l'Stage, creant una "fotografia". El missatge ha de ser significatiu. | |
| **Historial** | `git log` | Mostra l'historial complet de commits. | |
| | `git log --oneline` | Mostra l'historial en format concís. | |
| | `git reflog` | Mostra un historial complet de totes les interaccions amb el repositori local (incloent resets, etc.). | |
| **Diferències** | `git diff` | Mostra els canvis al Directori de Treball que encara no són a l'Stage. | |
| | `git diff --staged` | Mostra els canvis que estan a l'Stage pendents de commit. | |
| **Descartar/Netejar** | `git restore <fitxer>` | Descarta les modificacions locals del fitxer i el recupera a l'últim estat commitejat. | |
| | `git stash` | Desa temporalment els canvis locals (no commitejats) per canviar de branca o fer altres tasques. | |
| | `git stash pop` | Recupera els canvis guardats prèviament amb `git stash`. | |
| **Etiquetar** | `git tag <nom_tag>` | Etiqueta un punt important de l'historial (sovint per versions). | |

### 1.4 Gestió de Branques (Branching)

Les branques (Branches) permeten als desenvolupadors prendre una bifurcació de l'historial principal per treballar en una funcionalitat o correcció de forma aïllada i independent.

| Comanda | Descripció | Referències |
| :--- | :--- | :--- |
| `git branch` | Llista les branques locals. | |
| `git checkout <branca>` | Canvia a una branca existent. | |
| `git checkout -b <nova_branca>` | Crea una nova branca i s'hi canvia immediatament (p. ex., per crear la branca `dev`). | |
| `git switch <branca>` | Comanda moderna per canviar de branca, recomanada. (version>=2.23) | |
| `git merge <branca_origen>` | Fusiona els canvis de la branca d'origen a la branca actual (destí). | |
| `git branch -d <branca>` | Elimina una branca local després que s'hagi fusionat. | |

**Nota sobre Branches:** En el flux de treball, és comú crear branques com `dev` per al desenvolupament o `ticket1` per a correccions urgents. Un cop es realitza una fusió (`merge`), es produeix un *commit* que justifica aquesta fusió, especialment si hi ha hagut discordança entre els estats de les branques.

## 2. GitHub: Plataforma de Codi Col·laboratiu

**GitHub** és una plataforma remota i al núvol que allotja repositoris Git. És el **punt d'unió** on els equips col·laboren i sincronitzen els seus canvis.

### 2.1 Configuració i Sincronització Remota

*   **Connexió SSH:** Per autenticar la màquina local amb GitHub de forma segura, es recomana l'ús de claus SSH (Secure Shell Protocol). La clau pública generada localment (`.pub`) ha de ser afegida a la configuració del perfil de GitHub.
    *   Comanda per generar la clau: `ssh-keygen -t ed25519 -C "your_email@example.com"` (exemple).
    *   [+info](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
*   **Enllaçament Remot:** Per indicar al repositori local on es troba el repositori remot:
    *   `git remote add origin <URL>`: Associa el repositori local amb la URL remota sota l'àlies `origin`.
*   **Clonació:** Per descarregar un repositori existent des de GitHub a l'entorn local:
    *   `git clone <URL>`.
*   **Pujar Canvis (Push):** Envia els *commits* locals al repositori remot.
    *   `git push -u origin <branca>`: S'utilitza la primera vegada per establir la branca remota (`-u` o `--set-upstream`).
    *   `git push`: Per a pushes posteriors. Git rebutjarà el push si el repositori local no està al dia amb el remot.
*   **Descarregar Canvis (Pull):** Descarrega els canvis del repositori remot al local.
    *   `git pull`: Baixa els canvis del remot.
    *   `git fetch`: Descarrega l'historial de canvis sense aplicar-los localment (útil per a revisar).

### 2.2 Flux Col·laboratiu a GitHub

El treball col·laboratiu es basa en la filosofia de GitHub Flow, centrat en la creació de *Pull Requests* (PRs).

*   **Repositori (Repo):** Un contenidor d'un projecte. El nom de repositori que coincideix amb el nom d'usuari (p. ex., `mouredev/mouredev`) és especial i actua com a pàgina d'inici del perfil.
*   **README.md:** Arxiu de documentació clau per al projecte, mostrat a la pàgina principal del repositori. Utilitza la sintaxi **Markdown (.md)**.
*   **Fork (Bifurcació):** Crea una còpia del repositori d'un altre usuari al teu compte de GitHub. Això és necessari quan no es tenen permisos d'escriptura al repositori original i es vol contribuir.
*   **Pull Request (PR):** Sol·licitud per fusionar els canvis fets a una branca (ja sigui en el mateix repositori o des d'un *fork*) amb una branca de destí (p. ex., `main`).
    *   Permet a l'equip revisar els canvis abans de fusionar-los.
    *   El procés de creació d'una PR s'inicia normalment des de la interfície de GitHub, un cop els canvis han estat pujats a la branca.
*   **Resolució de Conflictes:** Si diferents desenvolupadors modifiquen la mateixa línia de codi, es genera un conflicte durant la fusió (merge). Els conflictes s'han de resoldre manualment abans que la PR pugui ser acceptada i fusionada.
*   **Merge (Fusió de PR):** El procés d'acceptar la PR i incorporar els canvis a la branca de destí.
*   **GitHub Pages:** Permet allotjar llocs web estàtics gratuïtament directament des d'un repositori.
*   **GitHub Actions:** Eina per a l'automatització de tasques (CI/CD, tests, desplegaments).
*   **Issues (Incidències):** Eina per reportar errors, fer seguiment de tasques o suggerir millores.

### 2.3 Gestió de Fitxers de Documentació (Markdown)

La majoria de documentació de Git es realitza utilitzant **Markdown (.md)**.

*   **Sintaxi Markdown:** És una sintaxi senzilla per escriure text enriquit (negreta, cursiva, llistes, títols) utilitzant caràcters especials.
*   **Fitxer `README.md`:** És el document que es mostra per defecte a la pàgina principal de qualsevol repositori. És important documentar amb *READMEs* els repositoris.

---