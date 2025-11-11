# Labo 07 - Configurer et déployer la réinitialisation de mot de passe en libre-service

### Type de connexion = Administrateur Microsoft 365

## Scénario du labo

L'entreprise a décidé d'autonomiser les employés et d'activer la réinitialisation de mot de passe en libre-service. Vous devez configurer ce paramètre dans votre organisation.

#### Durée estimée : 15 minutes

### Exercice 1 - Créer un groupe avec SSPR activé et ajouter des utilisateurs

#### Tâche 1 - Créer un groupe auquel assigner SSPR

Vous souhaitez d'abord déployer SSPR auprès d'un ensemble limité d'utilisateurs pour vous assurer que votre configuration SSPR fonctionne comme prévu. Créons un groupe de sécurité pour le déploiement limité et ajoutons un utilisateur au groupe.

1. Dans le centre d'administration Microsoft Entra, ouvrez le menu de navigation **Identité** sur la gauche.
1. Sous **Groupes**, sélectionnez **Tous les groupes** et sélectionnez **Nouveau Groupe** dans la fenêtre de droite.

2. Créez un nouveau groupe en utilisant les informations suivantes :

    | **Paramètre**| **Valeur**|
    | :--- | :--- |
    | Type de groupe| Sécurité|
    | Nom du groupe| SSPRTesters|
    | Description du groupe| Testeurs du déploiement SSPR|
    | Type d'adhésion| Assigné|
    | Membres| Alex Wilber |
    | |  Allan Deyoung |
    | | Bianca Pisani |
  
    
3. Sélectionnez **Créer**.

    ![Image d'écran affichant la page Nouveau Groupe avec le type de groupe, le nom du groupe et créer en évidence](./media/lp2-mod2-create-sspr-security-group.png)

#### Tâche 2 - Activer SSPR pour votre groupe de test

Activez SSPR pour le groupe.

1. Revenez au menu de navigation **Identité**.

2. Sous **Protection**, sélectionnez **Réinitialisation de mot de passe**.

3. Sur la page Propriétés de réinitialisation de mot de passe, sous **Réinitialisation de mot de passe en libre-service activée**, sélectionnez **Sélectionné**.

4. Sous **Sélectionner un groupe**, remplacez le groupe SSPRSecurityGroupUsers existant par **SSPRTesters** que vous venez de créer.

5. Sur la page Propriétés de réinitialisation de mot de passe, sélectionnez **Enregistrer**.

    ![Image d'écran affichant la page des propriétés de réinitialisation de mot de passe avec sélectionné, sélectionner un groupe et enregistrer en évidence](./media/lp2-mod2-enable-password-reset-for-selected-group.png)

6. Sur l'écran **Réinitialisation de mot de passe**, regardez sous **Gérer**, sélectionnez et examinez les valeurs par défaut pour chacun des paramètres **Méthodes d'authentification**, **Inscription**, **Notifications** et **Personnalisation**.

    **Remarque** il est important d'avoir **téléphone** sélectionné comme l'une des méthodes d'authentification pour le reste de ce labo, mais vous pouvez avoir d'autres options aussi.

#### Tâche 3 - S'inscrire à SSPR avec Allan

Maintenant que la configuration SSPR est terminée, enregistrez un numéro de téléphone mobile pour l'utilisateur que vous avez créé.

1. Ouvrez un navigateur différent ou ouvrez une session de navigateur InPrivate ou Incognito, puis accédez à [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).

    Ceci est pour s'assurer que vous êtes invité à vous authentifier.

2. Connectez-vous en tant que **AllanD@** `<<organization-domain-name>>.onmicrosoft.com` avec le mot de passe fourni.

    **Remarque** - Remplacez organization-domain-name par votre nom de domaine.

3. Si vous êtes invité à mettre à jour votre mot de passe, entrez un nouveau mot de passe de votre choix. Assurez-vous d'enregistrer le nouveau mot de passe.

4. Si vous êtes invité à rester connecté, choisissez Oui.

5. Dans la boîte de dialogue **Plus d'informations requises**, sélectionnez **Suivant**.

6. Sur la page Sécuriser votre compte, sélectionnez **Suivant** pour utiliser l'application Authenticator.

7. Suivez les instructions à l'écran pour configurer votre compte dans Authenticator en scannant le code QR.

8. Complétez le processus en sélectionnant **Terminé** lorsque vous vous êtes inscrit avec succès.

  - **Remarque** - à ce stade, vous vous êtes inscrit à la fois à SSPR et MFA en une seule étape.

11. Fermez le navigateur. Vous n'avez pas besoin de terminer le processus de connexion.

#### Tâche 4 - Tester SSPR

Maintenant, testons si l'utilisateur peut réinitialiser son mot de passe.

1. Ouvrez un navigateur différent ou ouvrez une session de navigateur InPrivate ou Incognito, puis accédez à [https://portal.azure.com](https://portal.azure.com).

    Ceci est pour s'assurer que vous êtes invité à vous authentifier.

2. Entrez **AlexW@** `<<organization-domain-name>>.onmicrosoft.com` puis sélectionnez **Suivant**.

    **Remarque** - Remplacez organization-domain-name par votre nom de domaine.

3. Sur la page Entrer le mot de passe, sélectionnez **J'ai oublié mon mot de passe**.

4. Sur la page Récupérer l'accès à votre compte, complétez les informations demandées puis sélectionnez **Suivant**.

5. Suivez les instructions à l'écran pour obtenir le code de vérification de l'application Microsoft Authenticator.

6. Entrez votre code de vérification puis sélectionnez **Suivant**.

7. À l'étape Choisir un nouveau mot de passe, entrez puis confirmez votre nouveau mot de passe.

8. Une fois terminé, sélectionnez **Terminer**.

9. Connectez-vous en tant que **AllanD** avec le nouveau mot de passe que vous avez créé.

10. Entrez votre code de vérification et vérifiez que vous pouvez terminer le processus de connexion.

11. Une fois terminé, fermez votre navigateur.

#### Tâche 5 - Que se passe-t-il si vous essayez un utilisateur qui ne fait pas partie du groupe SSPRTesters ?

1. À titre de test, ouvrez une nouvelle fenêtre de navigateur InPrivate et essayez de vous connecter au portail Azure en tant que GradyA, puis sélectionnez l'option **J'ai oublié mon mot de passe**.
