---
lab:
    title: '01 - Gérer les rôles utilisateur'
    learning path: '01'
    module: 'Module 01 - Implémenter une solution de gestion des identités'
---

# Locataires WWL - Conditions d'utilisation

<!-- Si un locataire vous est fourni dans le cadre d'une formation dirigée par un instructeur, veuillez noter que le locataire est mis à disposition dans le but de soutenir les laboratoires interactifs de la formation. Les locataires ne doivent pas être partagés ou utilisés à des fins autres que les laboratoires interactifs. Le locataire utilisé dans ce cours est un locataire d'essai qui ne peut pas être utilisé ou accessible après la fin du cours et n'est pas éligible à une extension. Les locataires ne doivent pas être convertis en abonnement payant. Les locataires obtenus dans le cadre de ce cours restent la propriété de Microsoft Corporation et nous nous réservons le droit d'y accéder et de les récupérer à tout moment. -->

# Deux options de connexion différentes

Ce laboratoire propose deux options de connexion différentes, utilisées pour différentes parties du laboratoire. Un style de connexion est pour les laboratoires nécessitant des ressources Azure, l'autre est pour les laboratoires nécessitant uniquement des ressources Microsoft Entra et Microsoft 365. Types de connexion :

  - Connexion basée sur les ressources Azure
  - Connexion au locataire Microsoft 365 + E3
      - Compte d'administrateur MOD

On vous indiquera quelle connexion utiliser dans chacun des laboratoires.


# Lab 01: Gérer les rôles utilisateur

### Type de connexion = Connexion au locataire Microsoft 365 + E3

## Scénario de laboratoire

Votre entreprise a récemment embauché un nouvel employé qui exercera des fonctions d'administrateur d'application. Vous devez créer un nouvel utilisateur et lui attribuer le rôle approprié.

#### Temps estimé : 30 minutes

### Exercice 1 - Créer un nouvel utilisateur et tester ses droits d'administrateur d'application

#### Tâche 1 - Ajouter un nouvel utilisateur

1. Connectez-vous à [https://entra.microsoft.com](https://entra.microsoft.com) en tant qu'administrateur global.
 - Utilisez le compte **Administrateur Microsoft 365**.

2. Dans le menu à gauche, développez le menu déroulant **Entra ID**, s'il n'est pas déjà ouvert.

3. Dans le menu de navigation de gauche, sous **Utilisateurs**, sélectionnez **Tous les utilisateurs**, puis sélectionnez **+ Nouvel utilisateur** et **Créer un nouvel utilisateur**.

4. Créez un utilisateur avec les informations suivantes :

    | **Paramètre**| **Valeur**|
    | :--- | :--- |
    | Nom principal de l'utilisateur| franck.k|
    | Nom affiché| Franck KOUAME |

5. Assurez-vous que l'option **Mot de passe auto-généré** est cochée.

6. Copiez le mot de passe généré dans un endroit où vous pourrez vous en souvenir pour la tâche suivante.

     *Vous devrez changer le mot de passe lors de la première connexion à ce compte*

7. Sélectionnez **Vérifier + Créer**. Puis sélectionnez **Créer** sur l'écran de révision. L'utilisateur est maintenant créé et enregistré dans votre organisation.

#### Tâche 2 - Connexion et essai de création d'une application

1. Ouvrez une nouvelle fenêtre de navigation InPrivate.
2. Ouvrez le centre d'administration Microsoft Entra [https://entra.microsoft.com](https://entra.microsoft.com) en tant que Franck KOUAME.

    | **Paramètre**| **Valeur**|
    | :--- | :--- |
    | Nom d'utilisateur| franck.k@`votre nom de domaine.com`|
    | Mot de passe| Entrez le mot de passe auto-généré de la tâche précédente. |

3. Mettez à jour votre mot de passe.

    | **Paramètre**| **Valeur**|
    | :--- | :--- |
    | Mot de passe actuel| Utilisez le mot de passe auto-généré|
    | Nouveau mot de passe| Entrez un mot de passe unique et sécurisé |
    | Confirmer le mot de passe| Réeentrez un mot de passe unique et sécurisé |

  **Astuce de laboratoire** - il est recommandé d'utiliser le mot de passe utilisateur fourni dans l'environnement de laboratoire.

4. Recherchez et sélectionnez +++Applications d'entreprise+++ dans la boîte de dialogue de recherche en haut de l'écran.

5. Sélectionnez **+ Nouvelle application**. Remarquez que **+ Créez votre propre application** n'est pas disponible.

6. Essayez de sélectionner l'un des autres paramètres comme **Consentement et autorisations**, et **Paramètres utilisateur** pour vérifier que **Franck KOUAME** n'a pas de droits.

7. Sélectionnez le nom de **franck.k** dans le coin supérieur droit et déconnectez-vous.


### Exercice 2 - Attribuer le rôle d'administrateur d'application et créer une application

#### Tâche 1 - Attribuer un rôle à un utilisateur

À l'aide de Microsoft Entra ID, vous pouvez désigner des administrateurs limités pour gérer les tâches d'identité dans des rôles moins privilégiés. Les administrateurs peuvent être assignés à des fins telles que l'ajout ou le changement d'utilisateurs, l'attribution de rôles administratifs, la réinitialisation des mots de passe des utilisateurs, la gestion des licences des utilisateurs et la gestion des noms de domaine.

1. Si vous n'êtes pas déjà connecté en tant qu'administrateur, ouvrez le centre d'administration Microsoft Entra et connectez-vous.
2. Accédez à Identité, puis sélectionnez la page Utilisateurs.
3. Sélectionnez **Tous les utilisateurs** sous la section Gérer du menu.
4. Sélectionnez le compte **Franck K**.
5. Choisissez **Rôles attribués** dans le menu Gérer.
6. Sélectionnez **+ Ajouter des attributions**.
7. Sélectionnez le rôle `Administrateur d'application` dans le menu déroulant.
8. Sélectionnez le bouton **Suivant**.
9. Cochez la valeur **Active** pour le **Type d'attribution**.
10. Entrez une justification comme +++Nécessaire pour le laboratoire+++. Puis sélectionnez **Attribuer**

    ![Page des rôles attribués - montrant le rôle sélectionné](./media/directory-role-select-role.png)

**Remarque** - Si l'environnement de laboratoire a déjà activé Microsoft Entra ID Premium P2, la gestion des identités privilégiées (PIM) sera activée et vous devrez sélectionner **Suivant** et attribuer un rôle permanent à cet utilisateur.

11. Sélectionnez le bouton **Actualiser**.

**Remarque - Le rôle d'administrateur d'application nouvellement attribué apparaît sur la page des rôles attribués de l'utilisateur.**

#### Tâche 2 - Vérifier les autorisations d'application

1. Ouvrez une nouvelle fenêtre de navigation InPrivate.
2. Ouvrez le centre d'administration Microsoft Entra à +++https://entra.microsoftcom+++ en tant que Franck KOUAME.

    | **Paramètre**| **Valeur**|
    | :--- | :--- |
    | Nom d'utilisateur| franck.k@`votre nom de domaine.com`|
    | Mot de passe| Entrez le mot de passe unique et sécurisé que vous avez créé précédemment |

3. Recherchez et sélectionnez +++Applications d'entreprise+++ dans la boîte de dialogue de recherche en haut de l'écran.
4. Remarquez que **+ Nouvelle application** est maintenant disponible.
5. Sélectionnez **+ Nouvelle application**
6. Vérifiez que **+ Créez votre propre application** n'est plus grisé.  Si vous choisissez une application de galerie, vous verrez que le bouton **Créer** est disponible.

   **Remarque - Ce rôle a maintenant la capacité d'ajouter des applications au locataire.  Nous expérimenterons davantage cette fonctionnalité dans les laboratoires suivants.**

7. Déconnectez-vous de l'instance du portail Franck KOUAME et fermez le navigateur.

### Exercice 3 - Supprimer une attribution de rôle

#### Tâche 1 - Supprimer l'administrateur d'application de Franck KOUAME

Cette tâche utilisera une méthode alternative pour supprimer le rôle attribué ; elle utilisera l'option **Rôles et administrateurs** dans Microsoft Entra ID.

1. Si vous n'êtes pas déjà connecté en tant qu'administrateur, lancez le centre d'administration Microsoft Entra et connectez-vous maintenant.
2. Dans la barre de recherche, tapez **Rôles** puis lancez **Rôles et administration Microsoft Entra ID**.
3. Dans **Tous les rôles** de **Rôles et administrateurs**, sélectionnez le rôle **Administrateur d'application** dans la liste.
4. Sur la page **Administrateur d'application | Attributions**, vous devriez voir le nom de Franck KOUAME listé.
5. Faites défiler complètement vers la droite sur Franck KOUAME.
6. Sélectionnez **Supprimer** dans les options en haut du dialogue.
7. Répondez **Oui** lorsque la boîte de confirmation s'ouvre.
8. Fermez l'écran.

### Exercice 4 - Importation en masse d'utilisateurs

#### Tâche 1 - Opérations en masse pour créer des utilisateurs avec un fichier .csv

1. Dans le menu Microsoft Entra ID, ouvrez d'abord **Identité**, puis sélectionnez **Utilisateurs** et enfin sélectionnez **Tous les utilisateurs**.

2. Sur le tuile **Utilisateurs | Tous les utilisateurs**, sélectionnez la flèche déroulante **Opérations en masse** puis **Création en masse**.

3. La sélection de **Création en masse** ouvrira une nouvelle tuile. Cette tuile fournit un lien **Télécharger** vers un fichier modèle que vous allez modifier pour le remplir avec les informations de vos utilisateurs et télécharger pour ajouter la création en masse d'utilisateurs.

4. Sélectionnez **Télécharger** pour télécharger le fichier .csv.

5. Le modèle .csv vous fournit les champs inclus dans le profil utilisateur. Cela inclut le nom d'utilisateur, le nom affiché et le mot de passe initial requis. Vous pouvez également remplir des champs optionnels, tels que le département et l'emplacement d'utilisation, à ce moment. La capture d'écran suivante est un exemple de la façon dont vous pouvez remplir le fichier .csv: 

    ![Importation en masse à l'aide de l'entrée du fichier csv](./media/bulkimportexample.png)

    Vous pouvez modifier ce fichier pour ajouter des utilisateurs en masse.  Notez que vous n'avez pas besoin de remplir tous les champs.  Comme l'indiquent les données d'exemple fournies, vous devez principalement ajouter les informations de nom et de nom d'utilisateur.

6. Un fichier CSV exemple a été fourni dans le dossier Allfiles/Labs/Lab1 -- **SC300BulkUser.csv**.
   1. Ouvrez le Bloc-notes.
     - Dans l'environnement de laboratoire, sélectionnez le bouton Démarrer et tapez Bloc-notes.  
   1. Ouvrez le fichier SC300BulkUser.csv
   1. Remplacez **entrez le nom de votre domaine** par le domaine de votre environnement de laboratoire Azure.
   1. Enregistrez le fichier.

7. Dans la boîte de dialogue **Création en masse d'utilisateurs**, sélectionnez l'icône de dossier de fichier à l'étape 3.

8. Chemin vers le dossier Allfiles/Labs/Lab1 et sélectionnez le fichier **SC300BulkUser.csv**.

9. Sélectionnez **Ouvrir**.

7. Vous serez informé que le fichier a été téléchargé avec succès.  Choisissez **Soumettre** pour ajouter les utilisateurs. 

Après la création des utilisateurs, vous serez averti que la création a réussi.  Fermez la tuile de création en masse d'utilisateurs et les nouveaux utilisateurs seront peuplés dans la liste de **Utilisateurs | Tous les utilisateurs**. 


### Exercice 5 - Supprimer un utilisateur de Microsoft Entra ID

#### Tâche 1 - Supprimer un utilisateur

Il se peut qu'un compte soit supprimé puis doive être récupéré. Vous devez vérifier que vous pouvez récupérer un compte qui a été récemment supprimé.

1. Accédez à [https://entra.microsoft.com](Microsoft Entra admin center).

2. Dans la navigation de gauche, sous **Identité**, sélectionnez **Utilisateurs**.

3. Ouvrez la liste **Tous les utilisateurs**, sélectionnez la case à cocher pour un utilisateur qui sera supprimé. Par exemple, sélectionnez **Franck KOUAME**.

    **Astuce** - La sélection d'utilisateurs dans la liste vous permet de gérer plusieurs utilisateurs en même temps. Si vous sélectionnez l'utilisateur pour ouvrir la page de cet utilisateur, vous ne gérerez que cet utilisateur individuel.

    ![Image d'écran affichant la liste des utilisateurs avec une case utilisateur sélectionnée et une autre case mise en surbrillance indiquant la possibilité de sélectionner plusieurs utilisateurs dans la liste.](./media/lp1-mod2-remove-user.png)

4. Avec le compte utilisateur sélectionné, dans le menu, sélectionnez **Supprimer**.

5. Examinez la boîte de dialogue puis sélectionnez **Oui**.

#### Tâche 2 - Restaurer un utilisateur supprimé

1. Dans la page Utilisateurs, sélectionnez **Tous les utilisateurs** dans la navigation de gauche, sélectionnez **Utilisateurs supprimés**.

2. Examinez la liste des utilisateurs supprimés et sélectionnez **Franck KOUAME**.

    **Important** - Par défaut, les comptes d'utilisateur supprimés sont automatiquement supprimés définitivement d'Azure Active Directory après 30 jours.

3. Dans le menu, sélectionnez **Restaurer l'utilisateur**.

4. Examinez la boîte de dialogue puis sélectionnez **OK**.

5. Dans la navigation de gauche, sélectionnez **Tous les utilisateurs**.

6. Vérifiez que l'utilisateur a été restauré.

