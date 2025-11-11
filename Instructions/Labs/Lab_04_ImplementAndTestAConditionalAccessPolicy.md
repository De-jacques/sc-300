# Laboratoire 04 - Implémenter et tester une stratégie d’accès conditionnel

### Type de connexion = administrateur Microsoft 365

## Scénario du laboratoire

Votre organisation doit pouvoir limiter l’accès des utilisateurs à ses applications internes. Vous devez déployer une stratégie d’accès conditionnel Microsoft Entra.

Remarque — Pour les stratégies d’accès conditionnel, vous pouvez désactiver les paramètres de sécurité par défaut; les points clés à retenir sont ceux de la formation. Des informations supplémentaires sur les paramètres de sécurité par défaut sont disponibles ici : <https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/concept-fundamentals-security-defaults>

#### Durée estimée : 20 minutes

### Exercice 1 - Définir une stratégie d’accès conditionnel pour bloquer DebraB sur Sway

#### Tâche 1 — Vérifier que DebraB a accès à Sway

1. Ouvrez une nouvelle fenêtre de navigateur en mode InPrivate.
2. Allez sur https://www.office.com.
3. Lorsqu’on vous le demande, connectez-vous en tant que DebraB :

  | Paramètre | Valeur |
  | :--- | :--- |
  | Nom d’utilisateur | **DebraB@** `<<your lab domain>>.onmicrosoft.com` |
  | Mot de passe | Saisissez le mot de passe fourni |
    
4. Passez les écrans d’accueil et d’introduction.
5. Ouvrez la page **Applications**, puis sélectionnez l’icône **Sway** pour vérifier qu’elle se charge correctement.
6. Déconnectez‑vous d’Office et fermez la session du navigateur.

#### Tâche 2 — Créer une stratégie d’accès conditionnel

Microsoft Entra Conditional Access est une fonctionnalité avancée de Microsoft Entra ID qui permet de définir des politiques détaillées contrôlant qui peut accéder à vos ressources. Avec l’accès conditionnel, vous pouvez protéger vos applications en limitant l’accès des utilisateurs selon des critères tels que les groupes, le type d’appareil, l’emplacement et le rôle.

1. Accédez à https://entra.microsoft.com et connectez‑vous avec un compte administrateur global du répertoire.
2. Ouvrez le menu du portail puis sélectionnez **Microsoft Entra ID**.
3. Dans le menu, sous **Identity**, sélectionnez **Protection**.
4. Sur la page Security, dans la navigation de gauche, sélectionnez **Conditional access**.
5. Dans **Overview (Preview)**, cliquez sur **+ Create new policy**.

   ![Image affichant la page Conditional Access avec New policy en surbrillance](./media/lp2-mod1-conditional-access-new-policy.png)

6. Dans la zone **Name**, saisissez **Block Sway for DebraB**.

   Remarque — Utilisez ce nom pour identifier rapidement la stratégie et sa fonction.

7. Sous **Assignments**, sélectionnez **0 users and groups selected**.
8. Dans l’onglet Include, sélectionnez **Select users and groups**, puis cochez la case **Users and groups**.
9. Dans le panneau de sélection, choisissez le compte **DebraB**, puis cliquez sur **Select**.
10. Dans **Target resources**, sélectionnez **No target resource selected**.
11. Vérifiez que **Cloud apps** est sélectionné, puis cliquez sur **Select apps**, et choisissez **None** dans la section de sélection.
12. Dans le panneau de sélection, recherchez **Sway**, sélectionnez **Sway**, puis cliquez sur **Select**.
13. Sous **Access controls**, dans la section **Grant**, sélectionnez **0 controls selected**.
14. Dans le panneau Grant, sélectionnez **Block access**, puis cliquez sur **Select**.

   Remarque — Cette stratégie est configurée uniquement pour l’exercice afin de démontrer rapidement une stratégie d’accès conditionnel.

15. Sous **Enable policy**, sélectionnez **On**, puis cliquez sur **Create**.

   ![Image affichant une nouvelle stratégie d’accès conditionnel avec les paramètres en surbrillance](./media/lp2-mod3-create-conditional-access-policy.png)

#### Tâche 3 — Tester la stratégie d’accès conditionnel

Vous devez tester vos stratégies d’accès conditionnel pour vous assurer qu’elles fonctionnent comme prévu.

1. Ouvrez un nouvel onglet de navigateur en mode InPrivate et allez sur https://sway.cloud.microsoft.
   - Lorsqu’on vous le demande, connectez‑vous en tant que DebraB :

   | Paramètre | Valeur |
   | :--- | :--- |
   | Nom d’utilisateur | **DebraB@** `<<your lab domain>>.onmicrosoft.com` |
   | Mot de passe | Saisissez le mot de passe fourni |
     
2. Vérifiez que l’accès à Microsoft Sway vous est refusé.

   ![Image affichant l’accès à la ressource bloqué à cause d’une stratégie d’accès conditionnel activée](./media/lp2-mod3-test-conditional-access-policy.png)

3. Si vous êtes connecté, fermez l’onglet, attendez 1 minute, puis réessayez.
    
   Remarque — Si vous êtes automatiquement connecté à Sway en tant que DebraB, vous devrez vous déconnecter manuellement. Vos informations d’identification/accès sont mises en cache. Une fois déconnecté puis reconnecté, la session Sway devrait refuser l’accès.

4. Fermez l’onglet et revenez à la page Conditional Access.
5. Sélectionnez la stratégie **Block Sway for DebraB**.
6. Sous **Enable policy**, sélectionnez **Off**, puis cliquez sur **Save**.

### Exercice 2 - Tester les stratégies d’accès conditionnel avec "What if"

#### Tâche — Utiliser What if pour tester les stratégies d’accès conditionnel

1. Ouvrez le menu Microsoft Entra admin center puis sélectionnez **Microsoft Entra ID**.
2. Dans le menu, sous **Identity**, sélectionnez **Protection**.
3. Sur la page Security, dans la navigation de gauche, sélectionnez **Conditional access**.
4. Dans le volet de navigation, sélectionnez **Policies**.
5. Sélectionnez **What If**.
6. Sous **User or Workload identity**, sélectionnez **No user or service principal selected**.
7. Choisissez **DebraB** comme utilisateur.
8. Sous **Cloud apps, actions, or authentication context**, sélectionnez **Sway**.
9. Cliquez sur **What if**. Un rapport s’affichera en bas du panneau indiquant les **Politiques qui s’appliqueront** et les **Politiques qui ne s’appliqueront pas**.

Cela vous permet de tester les politiques et leur efficacité avant de les activer.

### Exercice 3 - Configurer les contrôles de fréquence de connexion via une stratégie d’accès conditionnel

#### Tâche — Utiliser le centre d’administration Microsoft Entra pour configurer l’accès conditionnel

Dans le cadre de la configuration de sécurité de votre entreprise, vous devez tester une stratégie d’accès conditionnel pouvant contrôler la fréquence de connexion.

1. Accédez à https://entra.microsoft.com et connectez‑vous avec un compte administrateur global du répertoire.
2. Ouvrez le menu du portail puis sélectionnez **Microsoft Entra ID**.
3. Dans le menu, sous **Identity**, sélectionnez **Protection**.
4. Dans le menu Protection, dans la navigation de gauche, sélectionnez **Conditional access**.
5. Dans le menu supérieur, sélectionnez **+ New policy**, puis dans le menu déroulant sélectionnez **Create a new policy**.

   ![Image affichant la page Conditional Access avec New policy en surbrillance](./media/lp2-mod1-conditional-access-new-policy.png)

6. Dans la zone **Name**, saisissez **Sign in frequency**.
7. Sous **Assignments**, sélectionnez **0 users and groups selected**.
8. Dans l’onglet Include, cochez **Select users and groups**, puis cochez la case **Users and groups**.
9. Dans le panneau de sélection, choisissez votre compte **Grady Archie**, puis cliquez sur **Select**.
10. Sélectionnez **Target Resources - No target resources selected**.
11. Dans la section **Include**, assurez‑vous que **Select resources** est sélectionné, puis choisissez **None** dans la section Select.
12. Dans le panneau de sélection, sélectionnez **Office 365**, puis cliquez sur **Select**.
13. Sous **Access controls**, sélectionnez **Session**.
14. Dans le panneau Session, sélectionnez **Sign-in frequency**.
15. Dans la zone de valeur, entrez **30**.
16. Dans le menu des unités, sélectionnez **Days**, puis cliquez sur **Select**.
17. Sous **Enable policy**, sélectionnez **Report-only**, puis cliquez sur **Create**.

   ![Image affichant une nouvelle stratégie d’accès conditionnel liée à la session avec paramètres en surbrillance](./media/lp2-mod3-create-session-conditional-access-policy.png)

   REMARQUE — Le mode Report-only est un nouvel état pour les stratégies d’accès conditionnel qui permet aux administrateurs d’évaluer l’impact des politiques avant de les appliquer dans leur environnement. Avec le mode report-only :
    
- Les stratégies d’accès conditionnel peuvent être activées en mode report-only.
- Lors de la connexion, les stratégies en mode report-only sont évaluées mais non appliquées.
- Les résultats sont consignés dans les onglets Conditional Access et Report-only des détails du journal de connexion.
- Les clients disposant d’un abonnement Azure Monitor peuvent surveiller l’impact de leurs stratégies via le workbook Conditional Access insights.
