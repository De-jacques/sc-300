# Laboratoire 03 - Configurer une stratégie d'enregistrement pour l'authentification multifacteur

### Type de connexion = Administrateur Microsoft 365

## Scénario du laboratoire


L'authentification multifacteur (MFA) permet de vérifier votre identité en utilisant plus qu'un simple nom d'utilisateur et mot de passe. Elle ajoute une seconde couche de sécurité pour les connexions des utilisateurs. Pour que les utilisateurs puissent répondre aux sollicitations MFA, ils doivent d'abord s'enregistrer pour Microsoft Entra Multifactor Authentication. Vous devez configurer la stratégie d'enregistrement MFA de votre organisation Microsoft Entra pour l'affecter à tous les utilisateurs.

#### Durée estimée : 10 minutes

### Exercice 1 - Configurer la stratégie d'enregistrement MFA

#### Tâche 1 - Configuration de la stratégie

1. Connectez-vous à [https://entra.microsoft.com]( https://entra.microsoft.com) avec un compte Administrateur global.

2. Ouvrez le menu du portail puis sélectionnez **Microsoft Entra ID**.

3. Dans le menu de gauche, sous **Identité**, sélectionnez **Protection**.

4. Sur la page Sécurité, dans la navigation gauche, sélectionnez **Protection des identités**.

5. Sur la page Protection des identités, dans la navigation gauche sous **Protéger**, sélectionnez **Stratégie d'enregistrement pour l'authentification multifacteur**.

    ![Image affichant la page de stratégie d'enregistrement MFA avec le chemin de navigation mis en évidence](./media/lp2-mod4-browse-to-mfa-registration-policy.png)

6. Sous **Affectations**,...

7. Sous **Affectations**, sélectionnez **Tous les utilisateurs** et examinez les options disponibles.

8. Vous pouvez choisir **Tous les utilisateurs** ou **Sélectionner des personnes et des groupes** si vous limitez le déploiement.

9. De plus, vous pouvez exclure des utilisateurs de la stratégie.

10. Sous **Contrôles**, remarquez que **Exiger l'enregistrement de l'authentification multifacteur Microsoft Entra ID** est sélectionné et ne peut pas être modifié.


#### Tâche 2 - Configurer la stratégie Microsoft Entra Identity Protection pour l'enregistrement MFA

**Remarque** : Microsoft Entra Identity Protection nécessite l'activation de Microsoft Entra ID Premium P2.

1. Dans le centre d'administration Microsoft Entra, recherchez **Microsoft Entra ID Protection** via la barre de recherche.

2. Sous **Protéger** dans le menu, sélectionnez **Stratégie d'enregistrement pour l'authentification multifacteur**.

3. Sous **Affectations**, sélectionnez **Tous les utilisateurs** dans Utilisateurs, puis choisissez un utilisateur pour appliquer la stratégie.

4. Trouvez le champ **Application de la stratégie** dans la boîte de dialogue. Définissez la valeur sur **Activé**.

5. Sélectionnez **Enregistrer**.

Cela obligera l'utilisateur à compléter l'enregistrement MFA lors de sa prochaine tentative de connexion.

6. Depuis une fenêtre de navigation privée, accédez à `https://login.microsoftonline.com`. Saisissez le nom d'utilisateur et le mot de passe du locataire. Notez les informations de sécurité supplémentaires que l'utilisateur doit fournir.
