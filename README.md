# Resum i  Mapa Conceptual de **Git: Sistema de Control de Versions**

Aquest repositori conté un mapa conceptual interactiu sobre **Git**, així com un resum pensats per introduir els conceptes bàsics de control de versions i el seu ús col·laboratiu en projectes de desenvolupament de programari.

---

## 📂 Estructura del repositori

```
/
├── docs/
│   └── index.html                     # Versió HTML generada amb Markmap (GitHub Pages)
├── ConfiguracióGit.md                 # Guia ràpida de configuració de git
├── git_mapa_conceptual_markmap.md     # Fitxer del mapa conceptual en Markdown (compatible amb Markmap)
    guia_markdown_mouredev_pro.pdf     # Guia de Markdown de la mà de MoureDev
├── README.md                           # Aquest fixer guia      
└── ResumGit.md                         # Resum dels conceptes principals de Git

```

---

## 🧩 Contingut principal
### `ResumGit.md`
Conté un resum dels conceptes més rellevants a l'hora d'utilitzar Git tant en local com en remot utilitzant GitHub
Pots visualitzar directament el fitxer des de la web GitHub o bé [clonant el repositori](#-clonar-el-repositori)

### `git_mapa_conceptual_markmap.md`
Conté el **resum jeràrquic en Markdown** del mapa conceptual.  
Pots obrir-lo:
- Directament a [Markmap REPL](https://markmap.js.org/repl)
- O amb l’extensió **Markmap** a [VS Code](https://marketplace.visualstudio.com/items?itemName=gera2ld.markmap-vscode)

Exemple de secció:
```markdown
# Git: Sistema de Control de Versions (VCS)

## Definició i Propòsit
- Sistema de control de versions (VCS)
- Controlar canvis
- Facilitar el treball col·laboratiu
```

---

## 💡 Visualització local (sense GitHub Pages)

🧠 Instal·lació de Markmap (global)
```bash
npm install -g markmap-cli
```


Obrir el mapa localment:
```bash
npx markmap-cli git_mapa_conceptual_markmap.md
```


---

## 🧠 Resum del contingut del mapa

El mapa cobreix els conceptes clau de Git:

- **Definició i propòsit**
- **Concepte clau** (commits, branches, merges, HEAD…)
- **Configuració inicial**
- **Comandes bàsiques**
- **Flux de treball comú**
- **Eines col·laboratives** (GitHub, GitLab, CI/CD)
- **Recursos d’aprenentatge**

---
## 🚀 Clonar el repositori

Per obtenir una còpia local del projecte i començar a treballar-hi:

```bash
# 1️⃣ Clona el repositori (substitueix l'URL pel del teu projecte)
git clone git@github.com:2DAW-ICV/MaterialGit.git

# 2️⃣ Entra al directori del projecte
cd nom-repositori

# 3️⃣ Comprova en quina branca estàs
git branch
```
---  

## ✏️ Autor
Aquest material ha estat elaborat per l'equip docent de 2DAW com a recurs didàctic per introduir el treball amb Git i GitHub de manera visual i interactiva.

---

> 🔗 Basat en la tecnologia [Markmap](https://markmap.js.org)  
>  Compartit amb finalitats educatives