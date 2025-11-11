# Labo 08 - Activer l'authentification multifacteur

### Type de connexion = Connexion à Microsoft 365 + locataire E5

## Scénario du labo

Pour améliorer la sécurité dans votre organisation, vous avez été chargé d'activer l'authentification multifacteur pour Microsoft Entra ID.

#### Durée estimée : 15 minutes

**IMPORTANT** - Une licence Microsoft Entra ID Premium est requise pour cet exercice.

### Exercice 1 - Examiner et activer l'authentification multifacteur dans Azure

#### Tâche 1 - Examiner les options d'authentification multifacteur Azure

1. Accédez à [https://entra.microsoft.com](https://entra.microsoft.com) et connectez-vous à l'aide d'un compte administrateur général pour le répertoire.

2. Utilisez la fonction de recherche et recherchez **authentification multifacteur**.

3. Dans les résultats de la recherche, sélectionnez **Authentification multifacteur**.

    Vous pouvez également ouvrir **Identité**, puis sélectionner **Protection**, et sélectionner **Authentification multifacteur**.

4. Sur la page Prise en main, sous **Configurer**, sélectionnez **Paramètres MFA supplémentaires basés sur le cloud**.

    ![Capture d'écran montrant les options MFA dans le tableau de bord](./media/lp2-mod1-set-additional-mfa-settings.png)

5. Dans la nouvelle page du navigateur, vous pouvez voir les options MFA pour les utilisateurs Azure et les paramètres de service.

    ![Capture d'écran montrant la configuration MFA](./media/lp2-mod1-mfa-settings.png)

    C'est ici que vous sélectionneriez les méthodes d'authentification prises en charge. Dans l'écran ci-dessus, elles sont toutes sélectionnées.

    Vous pouvez également activer ou désactiver les mots de passe d'application ici, ce qui permet aux utilisateurs de créer des mots de passe de compte uniques pour les applications qui ne prennent pas en charge l'authentification multifacteur. Cette fonctionnalité permet à l'utilisateur de s'authentifier avec son identité Microsoft Entra à l'aide d'un mot de passe différent spécifique à cette application.

#### Tâche 2 - Configurer les règles d'accès conditionnel pour MFA pour Delia Dennis

Examinons ensuite comment configurer les règles de politique d'accès conditionnel qui appliqueraient l'authentification multifacteur aux utilisateurs invités accédant à des applications spécifiques sur votre réseau.

1. Revenez au centre d'administration Microsoft Entra et sélectionnez **Identité**, puis **Protection**, puis **Accès conditionnel**.

2. Dans le menu, sélectionnez **+ Nouvelle politique**. Dans la liste déroulante, sélectionnez **+ Créer une nouvelle politique**.

    ![Capture d'écran mettant en évidence le bouton Nouvelle Politique dans le centre d'administration Microsoft Entra.](./media/lp2-mod1-azure-ad-conditional-access-policy.png)

3. Nommez votre politique, par exemple **MFA_for_Delia**.

4. Sélectionnez **Utilisateurs ou identités de charge de travail** sous Affectations.

    - Sélectionnez **0 utilisateurs ou identités de charge de travail sélectionnés**  
    - Sur l'écran de droite, cochez la case **Sélectionner les utilisateurs et les groupes** pour configurer.
    - Cochez **Utilisateurs et groupes** (les utilisateurs disponibles seront remplis à droite)
    - Choisissez **Delia Dennis** dans la liste des utilisateurs, puis choisissez le bouton **Sélectionner**.

5. Sélectionnez **Aucune ressource cible sélectionnée** dans Ressources cibles.

   - Dans la liste déroulante, assurez-vous que **Applications cloud** est sélectionné.
   - Sous Inclure, marquez **Ressources (anciennement applications cloud)** et notez l'avertissement qui s'affiche concernant le fait de vous verrouiller potentiellement. 
   - Maintenant sous la section Inclure, choisissez l'élément **Sélectionner les ressources**.
   - Dans la section **Sélectionner**, sélectionnez le lien **Aucun**.
   - Dans la boîte de dialogue nouvellement ouverte, choisissez **Office 365**.
      - **Rappel** - dans un labo précédent, nous avons accordé à Delia Dennis une licence Office 365 et nous avons vérifié que cela fonctionnait.
   - Choisissez **Sélectionner**.

6. Choisissez un emplacement réseau dans la section Conditions, puis sélectionnez **Non configuré**.

   - Dans la section **Conditions**, choisissez le lien **0 condition sélectionnée**.
   - Au bas du menu nouvellement ouvert, trouvez la section **Emplacements** et sélectionnez **Non configuré**.
   - Choisissez **Oui** pour l'élément **Configurer**.
   - Sélectionnez **N'importe quel réseau ou emplacement**.

7. Sous **Contrôles d'accès**, trouvez la section **Accorder** et sélectionnez le lien **0 contrôle sélectionné**.

   - Cochez la case **Exiger l'authentification multifacteur** pour appliquer l'authentification multifacteur.
   - Assurez-vous que **Exiger tous les contrôles sélectionnés** est sélectionné.
   - Sélectionnez **Sélectionner**.

8. Définissez **Activer la politique** sur **Activé**.

9. Sélectionnez le bouton **Créer** pour créer la politique.

    ![Capture d'écran montrant la boîte de dialogue Ajouter une Politique complète](./media/lp2-mod1-conditional-access-new-policy-complete.png)

    L'authentification multifacteur est maintenant activée pour votre utilisateur et vos applications sélectionnés. La prochaine fois qu'un invité essaiera de se connecter à cette application, il sera invité à s'enregistrer pour l'authentification multifacteur.

#### Tâche 3 - Tester la connexion de Delia

1. Ouvrez une nouvelle fenêtre de navigation InPrivate.
2. Connectez-vous à https://www.office.com.
3. Sélectionnez l'option de connexion.
4. Entrez **DeliaD@** `<<votre adresse de domaine>>`.
5. Entrez le mot de passe = Entrez le mot de passe administrateur général du locataire (Remarque : Consultez l'onglet « Ressources de labo » pour récupérer le mot de passe administrateur).

**Remarque** - À ce stade, l'une de deux choses se produira. Vous devriez recevoir un message indiquant que vous devez configurer l'application Authenticator et vous inscrire à l'authentification multifacteur. Suivez les invites pour terminer en utilisant votre téléphone personnel. REMARQUE - il y a une chance que vous obteniez un message d'échec de connexion avec plusieurs options sur la façon de procéder. Sélectionnez l'option **Réessayer** dans ce cas.

Vous pouvez voir que du fait de la règle d'accès conditionnel que nous avons créée pour Delia, l'authentification multifacteur est requise pour lancer la page d'accueil Office 365.

### Exercice 2 - Configurer l'authentification multifacteur requise pour la connexion

#### Tâche 1 - Configurer l'authentification multifacteur par utilisateur Microsoft Entra

Enfin, examinons comment configurer l'authentification multifacteur pour les comptes utilisateurs. C'est une autre façon d'accéder aux paramètres d'authentification multifacteur.

1. Revenez au centre d'administration Microsoft Entra et trouvez le menu de navigation gauche Identité.

2. Sélectionnez **Utilisateurs**, puis sélectionnez **Tous les utilisateurs**.

3. En haut du volet Utilisateurs, sélectionnez **Authentification multifacteur par utilisateur**.
  - REMARQUE : vous devrez peut-être utiliser les points de suspension (...) pour accéder à l'élément de menu Authentification multifacteur par utilisateur.

   ![Capture d'écran montrant l'option MFA](./media/lp2-mod1-users-mfa.png)

4. Un nouvel onglet/fenêtre de navigateur s'ouvrira avec une boîte de dialogue des paramètres d'authentification multifacteur utilisateur.

   Vous pouvez activer ou désactiver l'authentification multifacteur sur une base utilisateur en sélectionnant un utilisateur et en utilisant ensuite les étapes rapides sur le côté droit.

   ![Capture d'écran montrant les options MFA](./media/lp2-mod1-mfa-service-settings-and-users.png)

5. Sélectionnez **Adele Vance** avec une coche.
6. Sélectionnez l'option **Activer l'authentification multifacteur** sous les étapes rapides.
7. Lisez la notification contextuelle si vous en recevez une, puis sélectionnez le bouton **Activer l'authentification multifacteur**.
8. Sélectionnez **Fermer**.
9. Notez qu'Adele a maintenant **Activé** comme son statut d'authentification multifacteur.
10. Vous pouvez sélectionner **paramètres de service** pour voir l'écran des paramètres MFA, vu plus tôt dans le labo.
11. Fermez l'onglet des paramètres MFA.

#### Tâche 2 - Essayer de se connecter en tant qu'Adele

1. Si vous souhaitez voir un autre exemple du processus de connexion MFA, vous pouvez essayer de vous connecter en tant qu'Adele.
