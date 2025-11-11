# Labo 05 : Ajouter des utilisateurs invités au répertoire

### Type de connexion = Administrateur Microsoft 365

## Scénario du labo


Votre entreprise travaille avec de nombreux fournisseurs et, à l'occasion, vous devez ajouter certains comptes de fournisseurs à votre répertoire en tant qu'invité.

#### Durée estimée : 20 minutes

### Exercice 1 - Ajouter des utilisateurs invités au répertoire

#### Tâche - Ajouter l'utilisateur invité

1. Connectez-vous à [https://entra.microsoft.com](https://entra.microsoft.com) en tant qu'utilisateur auquel un rôle d'administrateur de répertoire limité ou le rôle d'inviteur d'invités est attribué, ou en tant qu'administrateur général.

2. Sélectionnez **Identité**.

3. Sous **Utilisateurs**, sélectionnez **Tous les utilisateurs**.

4. Sélectionnez **+ Nouvel utilisateur**.

5. Dans le menu Nouvel utilisateur, sélectionnez **Inviter un utilisateur externe** et ajoutez vos informations en tant qu'utilisateur invité.

    **REMARQUE** - Les adresses e-mail de groupe ne sont pas prises en charge ; entrez l'adresse e-mail d'un individu. De plus, certains fournisseurs de messagerie permettent aux utilisateurs d'ajouter un symbole plus (+) et du texte supplémentaire à leurs adresses e-mail pour faciliter des opérations telles que le filtrage des boîtes de réception. Cependant, Microsoft Entra ID ne prend actuellement pas en charge les symboles plus dans les adresses e-mail. Pour éviter les problèmes de livraison, omettez le symbole plus et tous les caractères qui le suivent jusqu'au symbole @.

6. Entrez une adresse e-mail, par exemple **sc300externaluser1@sc300email.com**.

7. Sélectionnez l'onglet **Propriétés**.

8. Sur la page Utilisateurs, vérifiez que votre compte est répertorié et, dans la colonne **Type d'utilisateur**, vérifiez que **Invité** s'affiche.

9. Une fois terminé, sélectionnez **Vérifier + Inviter**, puis sélectionnez **Inviter**.


Après avoir envoyé l'invitation, le compte utilisateur est automatiquement ajouté au répertoire en tant qu'invité.


### Exercice 2 - Inviter des utilisateurs invités en masse

#### Tâche 1 - Invitation d'utilisateurs en masse

Un partenariat récent a été établi avec une autre entreprise. Pour l'instant, les employés de l'entreprise partenaire seront ajoutés en tant qu'invités. Vous devez vous assurer que vous pouvez importer plusieurs utilisateurs invités à la fois.

1. Connectez-vous à [https://entra.microsoft.com](https://entra.microsoft.com) en tant qu'administrateur général.

2. Dans le volet de navigation, sélectionnez **Identité**.

3. Sous **Utilisateurs**, sélectionnez **Tous les utilisateurs**.

4. Sur la page Utilisateurs, dans le menu, sélectionnez **Opérations en masse > Invitation en masse**.

   ![Image d'écran affichant la page Tous les utilisateurs avec les options de menu Opérations en masse et Invitation en masse mises en évidence](./media/lp1-mod3-bulk-invite-option.png)

5. Dans le volet Inviter des utilisateurs en masse, sélectionnez **Télécharger** pour obtenir un modèle CSV exemple avec les propriétés d'invitation.

6. À l'aide d'un éditeur pour afficher le fichier CSV, passez en revue le modèle.

7. Ouvrez le modèle .csv et ajoutez une ligne pour chaque utilisateur invité. Les valeurs obligatoires sont:

    - **Adresse e-mail à inviter** - l'utilisateur qui recevra une invitation
    - **URL de redirection** - l'URL vers laquelle l'utilisateur invité est transféré après avoir accepté l'invitation.

    ![Image d'écran affichant l'exemple de modèle CSV d'invitation en masse des invités](./media/lp1-mod3-template-csv.png)

**Conseil de labo** - Les utilisateurs répertoriés dans la capture d'écran et les fichiers de modèle sont des exemples, ils n'existent pas réellement. Vous devrez ajouter des utilisateurs réels pour tester complètement cette fonctionnalité.

8. Enregistrez le fichier.

9. Sur la page Inviter des utilisateurs en masse, sous **Télécharger votre fichier csv**, accédez au fichier.

     **Remarque** - Lorsque vous sélectionnez le fichier, la validation du fichier .csv commence.

10. Une fois le contenu du fichier validé, vous verrez **Fichier téléchargé avec succès**. S'il y a des erreurs, vous devez les corriger avant de pouvoir soumettre le travail.

    ![Image d'écran affichant l'invitation en masse des utilisateurs avec le message Fichier téléchargé avec succès en évidence](./media/lp1-mod3-bulk-invite-users-upload-csv.png)

11. Lorsque votre fichier réussit la validation, sélectionnez **Soumettre** pour démarrer l'opération en masse Azure qui ajoute les invitations.

12. Pour afficher l'état du travail, sélectionnez **Sélectionnez ici pour afficher l'état de chaque opération**. Ou, vous pouvez sélectionner **Résultats de l'opération en masse** dans la section Activité. Pour plus de détails sur chaque élément de ligne au sein de l'opération en masse, sélectionnez les valeurs sous les colonnes **# Succès**, **# Échec** ou **Nombre total de demandes**. Si des échecs se sont produits, les raisons de l'échec seront répertoriées.

    ![Image d'écran affichant les résultats d'une opération en masse](./media/lp1-mod3-bulk-operations-results.png)

13. Lorsque le travail est terminé, vous verrez une notification indiquant que l'opération en masse a réussi.
