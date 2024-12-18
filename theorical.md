# Côté Front

## Théorie

### 1. Qu'est-ce que le FOUC & Comment l'empêcher ?
Le FOUC est un flash de contenu  visible avant que les styles et/ou images ne soient complètement chargés, du coup le visuel est dans un premier temps désordonné.

**Comment l'empêcher ?**
- Minimiser et combiner les fichiers CSS.
- Precharger les styles ou utiliser le fallback au cas ou le style ne charge pas.

### 2. Citez des techniques permettant une meilleure optimisation des performances d'un frontend (React ou autre)

#### a. Avec un fort contenu à afficher
- **Lazy Loading** : Charger les composants ou images seulement lorsqu'ils sont nécessaires.
- **Server-Side Rendering (SSR)** : Générer les pages côté serveur pour réduire le temps de chargement initial.
- **Code Splitting** : Diviser le code en fichiers plus petits et charger uniquement ce qui est requis.
- **Utiliser un CDN** : Distribuer les assets via un réseau de serveurs proche des utilisateurs.

#### b. Avec des données provenant d’APIs
- **Mise en cache** : Utiliser des bibliothèques comme SWR ou React Query pour éviter de refetch les mêmes données.
- **Pagination/Infinite Scrolling/list virtualisation** : Limiter la quantité de données affichées en une seule fois.
- **Déduplication des requêtes** : S'assurer qu'une requête ne soit pas exécutée plusieurs fois pour la même donnée.

# Côté Back

## Théorie

### Questions relatives aux bases de données

#### 1. Citez les différents types de relations possibles entre plusieurs tables, et leurs cas d'applications
- **One-to-One (1:1)** : Une seule correspondance entre deux entités (exemple : un utilisateur et un profil détaillé).
- **One-to-Many (1:N)** : Une entité associée à plusieurs autres (exemple : un utilisateur et ses commandes).
- **Many-to-Many (M:N)** : Plusieurs entités liées à plusieurs autres via une table de jonction (exemple : utilisateurs et rôles).

#### 2. Comment implémenteriez-vous une relation récurrente entre deux tables ?
Créer une relation auto-référencée via une clé étrangère pointant vers la même table.

**Exemple :**
- Table `Utilisateur` avec une colonne `ami_id` (clé étrangère) pointant vers `id` dans la même table.
- Cela permet de lier un utilisateur à un ou plusieurs amis dans la même structure.
