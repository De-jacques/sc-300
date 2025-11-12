# Labo 10 - Activer les stratégies de risque à la connexion et de risque utilisateur

### Type de connexion = Administrateur Microsoft 365

## Scénario du labo

En tant que couche de sécurité supplémentaire, vous devez activer et configurer les stratégies de risque à la connexion et de risque utilisateur de votre organisation Microsoft Entra.

#### Durée estimée : 10 minutes


### Exercice 1 - Activer la stratégie de risque utilisateur

#### Tâche 1 - Configurer la stratégie

1. Connectez-vous à [https://entra.microsoft.com]( https://entra.microsoft.com) à l'aide d'un compte administrateur global.

2. Ouvrez le menu du portail, puis sélectionnez **Entra ID**.

3. Dans le menu, sous **Protection des identités**, sélectionnez **Tableau de bord**.

4. Dans le tableau de bord Protection des identités, dans la navigation de gauche, sélectionnez **Stratégie de risque utilisateur**.

    ![Image d'écran affichant la page Stratégie de risque utilisateur et le chemin d'accès mis en évidence](./media/lp2-mod4-browse-to-identity-protection.png)

5. Sous **Attributions**, sélectionnez **Tous les utilisateurs** et examinez les options disponibles.

6. Vous pouvez choisir parmi **Tous les utilisateurs** ou **Sélectionner des individus et des groupes** si vous limitez votre déploiement.

7. De plus, vous pouvez choisir d'exclure des utilisateurs de la stratégie.

8. Sous **Risque utilisateur**, sélectionnez **Faible et supérieur**.

9. Dans le volet Risque utilisateur, sélectionnez **Élevé**, puis sélectionnez **Terminé**.

10. Sous **Contrôles** > **Accès**, sélectionnez **Bloquer l'accès**.

11. Dans le volet Accès, examinez les options disponibles.

    **Conseil** - La recommandation de Microsoft est d'Autoriser l'accès et Exiger la modification du mot de passe.

12. Cochez la case **Exiger la modification du mot de passe**, puis sélectionnez **Terminé**.

13. Sous **Application de la stratégie**, sélectionnez **Activé**, puis sélectionnez **Enregistrer**.

#### Tâche 2 - Activer la stratégie de risque à la connexion

1. Sur la page Protection des identités, dans la navigation de gauche, sélectionnez **Stratégie de risque à la connexion**.

2. Comme pour la stratégie de risque utilisateur, la stratégie de risque à la connexion peut être attribuée à des utilisateurs et des groupes et vous permet d'exclure des utilisateurs de la stratégie.

3. Sous **Risque à la connexion**, sélectionnez **Faible et supérieur**.

4. Dans le volet Risque à la connexion, sélectionnez **Élevé**, puis sélectionnez **Terminé**.

5. Sous **Contrôles** > **Accès**, sélectionnez **Bloquer l'accès**.

6. Cochez la case **Exiger l'authentification multifacteur**, puis sélectionnez **Terminé**.

7. Sous **Application de la stratégie**, sélectionnez **Activé**, puis sélectionnez **Enregistrer**.
