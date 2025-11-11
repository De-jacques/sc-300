
# Labo 25 - Créer des révisions d'accès pour les utilisateurs internes et externes

### Type de connexion = Administrateur Microsoft 365

## Scénario du labo

L'accès des utilisateurs privilégiés doit être examiné régulièrement de manière similaire. Puisqu'il s'agit d'attributions d'accès élevées, l'examen de celles-ci doit être effectué de manière cohérente tel qu'identifié par l'entreprise. Les attributions privilégiées inutilisées et inutiles doivent être supprimées. La suppression automatisée doit également être configurée pour les utilisateurs qui ne sont plus avec l'entreprise ou qui ont changé de département au sein de l'entreprise.

#### Durée estimée : 5 minutes

### Exercice 1 - Créer une révision d'accès interne

#### Tâche - Créer une nouvelle révision d'accès

1. Connectez-vous à [https://entra.microsoft.com](https://entra.microsoft.com) en tant qu'administrateur général.

2. Les révisions d'accès peuvent gérer le cycle de vie de l'accès. Dans **Microsoft Entra ID**, trouvez **Gouvernance des identités**, puis sélectionnez **Révisions d'accès**.

3. Sélectionnez **+ Nouvelle révision d'accès**.

4. Dans la zone **Sélectionner ce qu'il faut examiner**, choisissez **Équipes + Groupes** dans la liste déroulante.

5. Sélectionnez **Sélectionner Équipes + groupes** et choisissez le groupe **Ventes et Marketing** dans la liste, puis appuyez sur **Sélectionner**.

6. Définissez l'**Étendue** sur **Tous les utilisateurs**.

7. Sélectionnez **Suivant : Révisions** pour avancer dans l'assistant.

8. L'étape suivante consiste à déterminer les réviseurs. Ces réviseurs peuvent être le membre lui-même pour effectuer un auto-examen ou peuvent être attribués aux superviseurs pour examiner l'accès pour tout un département. Vous pouvez également définir l'action lorsqu'un réviseur ne répond pas pour supprimer automatiquement cet accès privilégié au membre.

9. Choisissez un réviseur **Alex Wilber** et l'option de récurrence de révision **Annuellement**. Puis sélectionnez **Suivant : Paramètres**.

10. Les paramètres avancés vous permettent de mettre un message dans le cadre de la révision.

11. Accédez à l'onglet **Suivant : Vérifier + Créer** pour finaliser la révision d'accès.

12. Nommez la révision d'accès **SC300 Access Review Test**.

13. Sélectionnez **Créer** au bas de la page.

    **Remarque** - Lorsque la révision d'accès est créée, la liste des révisions d'accès sera remplie avec les rôles et les propriétaires des révisions.

14. Les membres en cours d'examen recevront un e-mail lorsque la révision est initiée.

15. La sélection d'une révision d'accès de l'un des rôles fournira l'état de ces révisions d'accès.
