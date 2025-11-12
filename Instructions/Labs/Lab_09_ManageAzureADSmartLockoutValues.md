
# Labo 09 - Gérer les valeurs de verrouillage intelligent de Microsoft Entra

### Type de connexion = Administrateur Microsoft 365

## Scénario du labo

Vous devez configurer les paramètres de protection supplémentaires des mots de passe pour votre organisation.

#### Durée estimée : 5 minutes

### Exercice 1 - Gérer les valeurs de verrouillage intelligent de Microsoft Entra

#### Tâche - Ajouter des verrouillages intelligents

En fonction des exigences de votre organisation, vous pouvez personnaliser les valeurs de verrouillage intelligent de Microsoft Entra. La personnalisation des paramètres de verrouillage intelligent, avec des valeurs spécifiques à votre organisation, nécessite des licences Microsoft Entra ID Premium P1 ou supérieures pour vos utilisateurs.

1. Accédez à [https://entra.microsoft.com](https://entra.microsoft.com) et connectez-vous à l'aide d'un compte administrateur global pour le répertoire.

2. Ouvrez le menu du portail, puis sélectionnez **Identité**.

3. Dans le menu Identité, ouvrez le menu **Protection**.

4. Dans la navigation de gauche, sélectionnez **Méthodes d'authentification**.

5. Puis sélectionnez **Protection par mot de passe**.

    ![Image d'écran affichant la page Méthodes d'authentification et les sélections mises en évidence pour accéder à la protection par mot de passe](./media/lp2-mod3-browse-to-password-protection.png)

6. Dans les paramètres de protection par mot de passe, dans la zone **Durée du verrouillage en secondes**, définissez la valeur sur **120**.

7. À côté de **Mode**, sélectionnez **Appliqué**.

8. Enregistrez vos modifications.

    **REMARQUE** - Lorsque le seuil de verrouillage intelligent est déclenché, vous recevrez le message suivant tant que le compte est verrouillé :
    - Votre compte est temporairement verrouillé pour éviter une utilisation non autorisée. Réessayez plus tard et, si vous rencontrez toujours des problèmes, contactez votre administrateur.

9. Cela peut être testé en choisissant un utilisateur dans votre locataire Microsoft Entra, en accédant à <login.microsoftonline.com> dans un navigateur privé et en entrant un mot de passe incorrect jusqu'à ce que le compte reçoive une notification indiquant qu'il est verrouillé.
