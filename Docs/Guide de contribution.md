# Guide de Contribution

**Table des matières**

- Prérequis

- Configuration de l'environnement

- Workflow Git Flow

- Conventions de code

- Tests

- Documentation

**Prérequis**

- Node.js (version LTS recommandée)

- MongoDB

- Git

- VSCode (recommandé avec les extensions suggérées)

**Configuration de l'environnement**

- Cloner le repository :
```bash
git clone \[url-du-repo\]

cd \[nom-du-repo\]
```
- Installer les dépendances :
```bash
npm install
```
- Copier le fichier .example.env vers .env et configurer les variables d'environnement :
```
MONGODB_URI="mongodb://localhost:27017/default_db"

JWT_SECRET="\*\*strongRandomSecret123!@#\*\*"

HASH_SALT="\*\*randomSaltCode123!@#$%^&\*\*\*"

LOG_LEVEL="debug"

PORT=4000

HOST="localhost"

NODE_ENV="development"

CORS_ORIGIN="<http://localhost:3000>"
#  dev env

GIT_AUTHOR_NAME=""
```
**Workflow Git Flow**

- **Initialiser Git Flow**
```bash
git flow init
```
Accepter les valeurs par défaut pour les branches.

- **Développer une nouvelle fonctionnalité**
```
git flow feature start nom-feature
```
#  Développer la fonctionnalité
```
git flow feature publish nom-feature
```
#  Créer une Pull Request
```
git flow feature finish nom-feature
```
- **Corriger un bug**
```
git flow hotfix start nom-hotfix
```
#  Corriger le bug
```
git flow hotfix finish nom-hotfix
```
- **Préparer une release**
```
git flow release start X.X.X
```
#  Finaliser la version
```
git flow release finish X.X.X
```
**Conventions de code**

**Style de code**

se referer a [style de code](#)

**Conventions de Nommage**

**Variables**

- Utiliser le snake_case

- Préfixer les booléens avec is_
```
const user_name = 'John';

const is_active = true;

const users_list = [];
```
**Composants React**

- Utiliser le PascalCase

- Le nom du fichier doit correspondre au nom du composant
```
// UserProfile.component.tsx

function UserProfile() {

&nbsp; return &lt;div&gt;...&lt;/div&gt;;

}
```
**Props**

- Utiliser le camelCase
```
function UserCard({ firstName, lastName, onSubmit }) {

    //...
}
```
**Constantes**

- Utiliser UPPER_CASE avec des underscores
```
const MAX_ITEMS = 10;

const API_BASE_URL = '<https://api.example.com>';
```
**Documentation**

**JSDoc**

Tous les composants, fonctions et méthodes doivent être documentés avec JSDoc :
```
/\*\*

* Description du composant ou de la fonction

* @param {string} param1 - Description du premier paramètre

* @param {number} param2 - Description du deuxième paramètre

* @returns {ReactElement} Description de ce qui est retourné
\*/
```
**Structure du Projet**
```
src/

├── components/     # Composants réutilisables

├── constants/      # Constantes du projet

├── context/       # Gestion d'état avec React Context

├── hooks/         # Custom hooks

├── interfaces/    # Types TypeScript

├── layouts/       # Composants de mise en page

├── mutations/     # Mutations GraphQL

├── pages/         # Composants de pages

├── queries/       # Requêtes GraphQL

├── themes/        # Thèmes de l'application

└── utils/         # Fonctions utilitaires
```
**État de l'Application**

- Utiliser React Context pour la gestion d'état globale

- Modulariser les contextes par domaine fonctionnel

**Communication Backend**

- Utiliser GraphQL pour toutes les communications

- Implémenter la gestion des erreurs

- Inclure des états de chargement

**Style et Design**

- Utiliser Joy UI pour les composants

- Suivre le système de design établi

- Assurer la responsivité

**Tests**

- Tests unitaires avec Jest

- Tests de composants avec React Testing Library

- Tests end-to-end selon les besoins

**Accessibilité**

- Suivre les normes WCAG

- Tester avec des lecteurs d'écran

- Assurer la navigation au clavier

**Internationalisation**

- Utiliser le hook personnalisé pour les traductions

- Ne pas coder en dur les textes

- Supporter les formats régionaux (dates, nombres, etc.)

**Sécurité**

- Validation côté client

- Protection CSRF

- Gestion sécurisée des JWT


Ce guide assure une base de code cohérente et maintenable, tout en respectant les standards de l'industrie et les besoins spécifiques du projet.**