# 📦 Utilisation des Snippets React

Ce guide explique comment installer et utiliser **`React Snippets.code-snippets`** dans :

- VS Code  
- WebStorm (Live Templates)

---

## 1. Pré‐requis

- Avoir récupéré ou cloné ce dépôt contenant le fichier  
  `React Snippets.code-snippets`.

---

## 2. Installation & usage sous **VS Code**

1. **Ouvrir votre dossier d’utilisateur VS Code**  
   - **macOS / Linux**  
     `~/.config/Code/User/snippets/`  
   - **Windows**  
     `%APPDATA%\Code\User\snippets\`

2. **Copier** `React Snippets.code-snippets` dans ce dossier.

3. **Redémarrer** VS Code (ou recharger la fenêtre `Ctrl+Shift+P` ▶ > **Reload Window**).

4. **Activer un snippet**  
   - Dans un fichier `.jsx`, `.tsx` ou `.js`/`.ts` configuré pour React.  
   - Tapez le **préfixe** (ex. `rfc`, `usf`, `usq`…) et appuyez sur **Tab** ou **Entrée**.  
   - Les **tabstops** `$1, $2, … $0` vous positionnent automatiquement pour remplir les variables.

---

## 3. Installation & usage sous **WebStorm** (Live Templates)

WebStorm ne lit pas directement le format `.code-snippets` de VS Code ; il faut transformer chaque snippet en **Live Template** :

1. **Ouvrir les préférences**  
   - **macOS** : `WebStorm › Preferences…`  
   - **Windows/Linux** : `File › Settings…`

2. **Aller dans**  
   `Editor › Live Templates`

3. **Créer un nouveau groupe** (facultatif)  
   - Cliquez sur **+** ▶ **Template Group**  
   - Nommez-le par ex. **ReactSnippets**

4. **Ajouter un Live Template**  
   - Sélectionnez le groupe **ReactSnippets** (ou **JavaScript** / **TypeScript**).  
   - Cliquez sur **+ ▶ Live Template**.

5. **Renseigner les détails**  
   - **Abbreviation** : le préfixe du snippet (ex. `rfc`).  
   - **Description** : courte explication (ex. “React Function Component”).  
   - **Template text** : copiez le corps du snippet depuis le JSON VS Code.  
     - Remplacez les **tabstops** VS Code (`$1`, `$0`) par la syntaxe WebStorm :  
       ```text
       $END$        // anciennement $0
       $VAR1$       // anciennement $1
       ```
   - **Define** ▶ cochez les contextes où il s’applique :  
     - `JavaScript › JSX`  
     - `TypeScript › JSX`  

6. **Enregistrer**  
   - Cliquez sur **Apply** puis **OK**.

7. **Utiliser le template**  
   - Dans l’éditeur, tapez l’**abbreviation** puis **Tab**.  
   - Remplissez les variables via **Tab** pour passer d’un placeholder à l’autre.

---

## 4. Exemple de conversion

### VS Code (JSON)

```jsonc
"React Function Component": {
  "prefix": "rfc",
  "body": [
    "import React from \"react\";",
    "",
    "type Props = {",
    "  $1",
    "};",
    "",
    "export const $2: React.FC<Props> = ({ $1 }) => {",
    "  return <div>$0</div>;",
    "}"
  ],
  "description": "React Function Component"
}
