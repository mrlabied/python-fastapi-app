
# TP7 – Security Notes

## Q3. Pourquoi faut-il épingler une version (@v4) plutôt que @main ?

La référence @v4 permet d'utiliser une version publiée et identifiée de l'action.

La référence @main peut changer à tout moment. Une modification malveillante ou une erreur dans cette branche pourrait affecter notre workflow.

Pour renforcer la sécurité, on peut utiliser le SHA complet d'un commit précis.

## Q4. Le badge créateur vérifié garantit-il qu'une action est sûre ?

Non. Le badge indique que GitHub a vérifié l'identité du créateur.

Il ne garantit pas que le code de l'action est sans vulnérabilité ou qu'il ne contient aucun comportement malveillant.

## Q5. Citez deux vérifications à faire avant d'utiliser une action d'un fournisseur inconnu.

1. Vérifier le code source, les permissions demandées, les dépendances et les éventuelles vulnérabilités.
2. Vérifier la réputation du fournisseur, les mises à jour, les issues et les versions publiées. Il faut également épingler une version ou un SHA de commit fiable.
