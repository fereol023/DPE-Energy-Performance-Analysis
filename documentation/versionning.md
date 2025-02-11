 ## VERSIONNING MAJOR.MINOR.PATCH

 ### 1. Fonctionnement du schéma de versionning major.minor.patch 
 * Pour mettre en place ce schéma de versionning, il suffit de suivre la convention [semver](https://semver.org/lang/fr/) et d'utiliser un outil de gestion de versionning tel que Git.
 * Pour faire une release major, il faut incrémenter le numéro de version major lorsque des changements non rétrocompatibles sont
   apportés à la codebase. Par exemple, si une fonctionnalité est supprimée ou si une API est modifiée de manière incompatible
   avec les versions précédentes.
 * Pour faire une release minor, il faut incrémenter le numéro de version minor lorsque de nouvelles fonctionnalités
   rétrocompatibles sont ajoutées. Par exemple, si une nouvelle fonction est implémentée ou si une fonctionnalité existante est
   améliorée.
 * Pour faire un patch, il faut incrémenter le numéro de version patch lorsque des correctifs rétrocompatibles sont appliqués à la
   codebase. Par exemple, si un bug est corrigé ou si une vulnérabilité de sécurité est résolue.

 ### 2. Pertinence 
 
    Le schéma de versionning major.minor.patch est pertinent dans la mesure où il permet de communiquer clairement
    les changements apportés à une application ou à une bibliothèque. Il permet aux utilisateurs de savoir s'ils doivent mettre à
    jour leur code et dans quelle mesure, et il permet également aux développeurs de coordonner leurs efforts et de maintenir la
    compatibilité entre les différentes versions.

 ### 3. Avantages 
    
    Les avantages du schéma de versionning major.minor.patch sont nombreux. Tout d'abord, il permet de maintenir la
    compatibilité entre les différentes versions, ce qui facilite les mises à jour et réduit les risques de casse. Ensuite, il
    permet de communiquer clairement les changements apportés à la codebase, ce qui facilite la collaboration entre les
    développeurs et les utilisateurs. Enfin, il permet de gérer les dépendances de manière efficace, en évitant les conflits et
    les erreurs de version.

### mise en place
Voici les étapes pour mettre en place le pattern de versioning major.minor.patch avec GitHub :

 1. Créez un dépôt GitHub pour votre projet s'il n'en existe pas déjà.
 2. Dans votre projet, créez un fichier VERSION dans le répertoire racine. Ce fichier doit contenir la version actuelle de votre
    projet dans le format major.minor.patch.
 3. Créez une branche de développement (par exemple dev) à partir de la branche principale (généralement main).
 4. Effectuez toutes vos modifications et commits dans la branche de développement.
 5. Lorsque vous êtes prêt à faire une nouvelle release, créez une nouvelle branche de release (par exemple release/1.2.0) à
    partir de la branche de développement.
 6. Dans la branche de release, mettez à jour le numéro de version dans le fichier VERSION.
 7. Créez une étiquette (tag) avec le numéro de version dans la branche de release en utilisant la commande git tag v1.2.0.
 8. Fusionnez la branche de release dans la branche principale en utilisant une requête de fusion (pull request).
 9. Une fois la fusion effectuée, supprimez la branche de release.

En suivant ces étapes, vous aurez mis en place un système de versioning major.minor.patch pour votre projet sur GitHub.

La suppression de la branche de release après la fusion avec la branche principale est une pratique courante dans le développement
logiciel utilisant GitFlow ou un workflow similaire.

La raison principale est de garder le nombre de branches actives au minimum, afin de simplifier la gestion des branches et de
réduire les risques de confusion. Une fois que la release a été fusionnée avec la branche principale et publiée, il n'y a plus de
raison de garder la branche de release active.

De plus, si une correction est nécessaire pour une release spécifique, il est recommandé de créer une nouvelle branche de
correction (hotfix) à partir de la version taggée correspondante, plutôt que de réutiliser la branche de release d'origine. Cela
permet de conserver un historique clair des corrections apportées à chaque version.

# -------
En résumé, la suppression de la branche de release après la fusion avec la branche principale permet de simplifier la gestion des
branches et de maintenir un historique clair des versions et des corrections.

Dans le modèle GitFlow, il est recommandé d'avoir une branche develop pour les développements en cours et des branches feature pour chaque nouvelle fonctionnalité.

Les branches feature sont créées à partir de la branche develop et fusionnées dans develop une fois terminées et testées. La branche develop est utilisée pour tester et intégrer les nouvelles fonctionnalités avant de faire une release.

Donc, en résumé, il est possible d'avoir plusieurs branches feature en parallèle ainsi qu'une branche develop pour intégrer et tester les modifications avant de les fusionner dans la branche principale master.

# ------------
Dans ce pattern, les modifications sont généralement apportées sur une branche "develop" ou "feature" avant d'être fusionnées dans la branche principale. Les versions mineures et majeures sont créées à partir de la branche principale en créant une nouvelle branche de release (par exemple, "release/1.2.0"). Une fois la version testée et prête à être publiée, elle est fusionnée dans la branche principale et la branche de release est supprimée.

Donc même si le nom "master" n'est pas mentionné explicitement dans ce pattern, il est toujours recommandé d'avoir une branche principale pour gérer les versions stables et les releases.

# -------------
La branche principale est la branche qui représente la version la plus stable et la plus testée de votre projet. Elle doit toujours être à jour avec la dernière version stable du projet.

Dans le cas où vous utilisez le pattern de versionning GitFlow, la branche principale est généralement nommée "master" ou "main". Elle doit être mise à jour avec les versions stables provenant de la branche "develop". Cela signifie que lorsque vous êtes prêt à faire une release, vous devez créer une branche de release à partir de la branche "develop", la tester et la merger dans la branche principale.

Il est important de garder la branche principale à jour pour éviter les conflits et les problèmes de déploiement. Si la branche principale n'est pas à jour, il est possible que des fonctionnalités ou des corrections soient manquantes dans la version en production, ce qui peut causer des problèmes pour les utilisateurs.

# ---------- récap : 
Oui, vous avez bien compris le processus ! Voici les étapes résumées :

 1. On travaille sur la branche develop en créant des branches feature pour les modifications mineures ou majeures.
 2. Une fois le développement terminé, on merge la branche feature dans la branche develop.
 3. On crée ensuite un commit unique ou on upgrade la version dans la branche develop.
 4. On merge la branche develop dans la branche principale.
 5. On crée une branche release à partir de la branche principale pour déclencher le déploiement.
 6. Une fois le déploiement terminé, on supprime la branche release.
 7. La branche principale reste à jour avec la version en production.

Le git tag intervient lors de la création de la branche de release. Après avoir fusionné la branche de développement (develop)
dans la branche principale (main), on crée une nouvelle branche de release à partir de la branche principale. On met à jour le
numéro de version dans le code source de la branche de release, puis on crée un tag avec ce numéro de version en utilisant la
commande git tag vX.Y.Z. Une fois le déploiement effectué, on supprime la branche de release, mais le tag reste dans l'historique
de la branche principale.

Le rôle du tag dans Git est de marquer un commit spécifique avec une étiquette ou un numéro de version. Cela permet de facilement
identifier une version donnée du code et de la retrouver à tout moment dans l'historique de Git. Les tags peuvent être utilisés
pour identifier des releases, des versions bêta ou des versions de développement, et peuvent être lightweight ou annotated. Les
tags annotés contiennent des métadonnées supplémentaires telles que le nom de l'auteur, la date et un message de description. Le
tag est utilisé lors de la création d'une nouvelle version de l'application, après avoir fusionné la branche de développement dans
la branche principale. Il permet de retrouver facilement la version de code déployée en production.

Si la branche de release a été supprimée et que vous voulez retrouver la branche de départ pour effectuer un hotfix ou développer
une nouvelle feature, vous pouvez créer une nouvelle branche à partir du tag correspondant à la version que vous souhaitez
modifier.

Par exemple, si vous voulez travailler sur la version 1.2.3, vous pouvez créer une branche à partir du tag 1.2.3 en utilisant la
commande git checkout -b hotfix/1.2.4 v1.2.3 ou git checkout -b feature/new-feature v1.2.3.

Cela créera une nouvelle branche à partir du commit taggé avec la version 1.2.3, que vous pouvez ensuite utiliser pour effectuer
vos modifications et créer une nouvelle release ou hotfix.

https://www.geeksforgeeks.org/how-to-create-a-tag-in-a-github-repository/
