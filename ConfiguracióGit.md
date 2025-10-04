# Comandes bàsiques de `git config`

La comanda `git config` s'utilitza per establir i consultar la configuració de Git.  
Es pot aplicar en tres nivells:

- **--system** → Configuració global del sistema (per a tots els usuaris).
- **--global** → Configuració per a l'usuari actual (habitual).
- **--local** → Configuració només per al repositori actual.

---

## Identitat de l'usuari

```bash
# Establir el nom d'usuari
git config --global user.name "Nom Cognom"

# Establir l'adreça de correu
git config --global user.email "usuari@exemple.com"
```

# Definir editor per defecte (exemple amb nano o VS Code)
Si volem nano com a editor per defecte:
```bash
git config --global core.editor "nano"
```
Si volem VSCode com a editor per defecte amb el modificador "wait" per tal que git esperi a que es tanqui l'editor:

```bash
git config --global core.editor "code --wait"
```

# Control de salts de línia (CRLF)

Els sistemes operatius utilitzen diferents formats per als salts de línia:

- Windows → CRLF (\r\n)

- Linux/Mac → LF (\n)

Git pot convertir automàticament els salts per evitar problemes
## Opció recomanada per a desenvolupadors en Windows
### Converteix LF → CRLF en fer checkout i CRLF → LF en fer commit
```bash
git config --global core.autocrlf true
```


## Opció recomanada per a desenvolupadors en Linux/Mac
### Manté LF i mostra avís si hi ha CRLF
```bash
git config --global core.autocrlf input
```


## Desactivar qualsevol conversió
```bash
git config --global core.autocrlf false
```

# Llistar les configuracions

```bash
# Veure tota la configuració
git config --list
# Consultar una clau concreta
git config user.name
git config user.email
```
# Editar les configuracions
```bash
# Obrir la configuració global amb editor
git config --global --edit
```