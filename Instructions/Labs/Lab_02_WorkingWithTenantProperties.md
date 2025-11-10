---
lab:
    title: '02 - Travailler avec les propriétés du locataire'
    learning path: '01'
    module: 'Module 01 - Implémenter une solution de gestion des identités'
---

# Laboratoire 02 : Travailler avec les propriétés du locataire

### Type de connexion = Microsoft 365 + connexion à un locataire E3

## Scénario du laboratoire

Vous devez identifier et mettre à jour les différentes propriétés associées à votre locataire.

#### Durée estimée : 15 minutes

### Exercice 1 - Créer un sous-domaine personnalisé

#### Tâche 1 - Créer un nom de sous-domaine personnalisé

Vous utilisez Microsoft Entra ID pour créer un domaine que vous avez acheté. Si vous souhaitez créer un sous-domaine pour diviser votre domaine .onmicrosoft.com existant, vous devez utiliser le centre d'administration Microsoft 365.

1. Ouvrez https://entra.microsoft.com et connectez-vous à l'aide d'un compte Administrateur global pour l'annuaire.

1. Dans le menu **Identité**, utilisez l'option **Afficher plus** en bas.

1. Ouvrez le menu **Paramètres**, sélectionnez **Noms de domaine**.

1. Sélectionnez **+ Ajouter un domaine personnalisé**.

1. Dans le champ **Nom de domaine personnalisé**, créez un sous-domaine personnalisé pour le locataire du laboratoire en ajoutant **sales** devant le nom de domaine **onmicrosoft.com**. Le format ressemblera à ceci :

    ```
    Sales.labTenantName.onmicrosoft.com
    ```

**Remarque** - Il vous sera demandé d'ouvrir le centre d'administration Microsoft 365 pour compléter cette action.

1. Sélectionnez **Ajouter le domaine** pour ajouter le sous-domaine.

1. Entrez le nom de sous-domaine `sales.tenantname.onmicrosoft.com` dans la boîte de dialogue. N'oubliez pas de remplacer *tenantname* par le nom de votre locataire.

1. Sélectionnez le bouton **Utiliser ce domaine** en bas de l'écran.

1. Sélectionnez le bouton **Fermer** lorsque l'écran suivant s'ouvre. Pour les besoins de ce laboratoire, nous ne configurerons pas le DNS.

### Exercice 2 - Changer le nom d'affichage du locataire

#### Tâche 1 - Définir le nom du locataire et le contact technique

1. Depuis le centre d'administration Microsoft Entra, ouvrez le menu **Identité**.

1. Dans la navigation de gauche, sélectionnez **Présentation**, puis cliquez sur **Propriétés**.

1. Modifiez les propriétés du locataire pour les champs **Nom** et **Contact technique** dans la boîte de dialogue.

    | **Paramètre** | **Valeur** |
    | :--- | :--- |
    | Nom | Contoso Marketing |
    | Contact technique | `votre compte Administrateur global` |

1. Sélectionnez **Save** pour mettre à jour les propriétés du locataire.

   **Vous remarquerez le changement de nom immédiatement après l'enregistrement.**

#### Tâche 2 - Vérifier le pays ou la région et d'autres valeurs associées à votre locataire

1. Dans le menu **Identité**, sélectionnez **Présentation**, puis **Propriétés**.

2. Sous **Propriétés du locataire**, localisez **Pays ou région** et consultez l'information.

    **IMPORTANT** - Lors de la création du locataire, le champ Country or region est défini à ce moment-là. Ce paramètre ne peut pas être modifié par la suite.

3. Dans la page **Propriétés**, sous **Propriétés du locataire**, localisez **Emplacement** et consultez l'information.

    ![Image montrant la page Propriétés d'Azure Active Directory avec les paramètres Country or region et Location mis en évidence](./media/azure-active-directory-properties-country-location.png)

#### Tâche 3 - Trouver l'ID du locataire

Les abonnements Azure ont une relation de confiance avec Microsoft Entra ID. Microsoft Entra ID est utilisé pour authentifier les utilisateurs, services et appareils pour l'abonnement. Chaque abonnement possède un identifiant de locataire (tenant ID) associé, et il existe plusieurs façons de trouver cet ID.

1. Ouvrez le centre d'administration Microsoft Entra à https://entra.microsoft.com

1. Dans le menu **Identité**, sélectionnez **Présentation**, puis **Propriétés**.

1. Sous **Propriétés du locataire**, localisez **ID du locataire**. Il s'agit de votre identifiant unique de locataire.

    ![Image affichant la page Tenant properties avec la case Tenant ID mise en évidence](./media/portal-tenant-id.png)

**Remarque** - Il est utile de noter votre Tenant-ID dans le Bloc-notes ou un autre emplacement pour l'utiliser dans de futurs laboratoires.


