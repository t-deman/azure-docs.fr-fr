---
title: 'Didacticiel : Configurer Zscaler pour l’approvisionnement automatique avec Azure Active Directory | Microsoft Docs'
description: Découvrez comment configurer Azure Active Directory pour approvisionner et retirer automatiquement des comptes d’utilisateurs à Zscaler.
services: active-directory
documentationcenter: ''
author: zchia
writer: zchia
manager: beatrizd-msft
ms.assetid: 31f67481-360d-4471-88c9-1cc9bdafee24
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 03/27/2019
ms.author: v-ant-msft
ms.openlocfilehash: 3ea502477cc5b380c99a183d9270c2b2e94375a8
ms.sourcegitcommit: c174d408a5522b58160e17a87d2b6ef4482a6694
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59275470"
---
# <a name="tutorial-configure-zscaler-for-automatic-user-provisioning"></a>Didacticiel : Configurer Zscaler pour l’approvisionnement automatique

L’objectif de ce didacticiel est de présenter les étapes à effectuer dans Zscaler et Azure Active Directory (Azure AD) pour configurer Azure AD pour approvisionner automatiquement et retirer les utilisateurs et/ou groupes à Zscaler.

> [!NOTE]
> Ce didacticiel décrit un connecteur reposant sur le service d’attribution d’utilisateurs Azure AD. Pour découvrir les informations importantes sur ce que fait ce service, comment il fonctionne et consulter le forum aux questions, reportez-vous à l’article [Automatiser l’attribution et l’annulation de l’attribution des utilisateurs dans les applications SaaS avec Azure Active Directory](../active-directory-saas-app-provisioning.md).
>

> Ce connecteur est actuellement en version préliminaire publique. Pour plus d’informations sur les conditions d’utilisation Microsoft Azure générales pour les fonctionnalités en version préliminaire, consultez [conditions d’utilisation supplémentaires pour les versions préliminaires de Microsoft Azure](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).

## <a name="prerequisites"></a>Conditions préalables

Le scénario décrit dans ce didacticiel part du principe que vous disposez des éléments suivants :

* un locataire Azure AD ;
* Un locataire Zscaler
* Un compte d’utilisateur dans Zscaler avec des autorisations d’administrateur

> [!NOTE]
> L’intégration d’approvisionnement Azure AD s’appuie sur l’API de SCIM de Zscaler, qui est disponible pour les développeurs Zscaler pour les comptes avec le package de l’entreprise.

## <a name="adding-zscaler-from-the-gallery"></a>Ajouter Zscaler à partir de la galerie

Avant de configurer Zscaler pour l’approvisionnement avec Azure AD automatique d’utilisateurs, vous devez ajouter Zscaler à partir de la galerie d’applications Azure AD à votre liste d’applications SaaS gérées.

**Pour ajouter Zscaler à partir de la galerie d’applications Azure AD, procédez comme suit :**

1. Dans le volet de navigation gauche du **[portail Azure](https://portal.azure.com)**, cliquez sur l’icône **Azure Active Directory**.

    ![Bouton Azure Active Directory](common/select-azuread.png)

2. Accédez à **Applications d’entreprise**, puis sélectionnez l’option **Toutes les applications**.

    ![Panneau Applications d’entreprise](common/enterprise-applications.png)

3. Pour ajouter l’application, cliquez sur le bouton **Nouvelle application** en haut de la boîte de dialogue.

    ![Bouton Nouvelle application](common/add-new-app.png)

4. Dans la zone de recherche, tapez **Zscaler**, sélectionnez **Zscaler** dans le volet de résultats, puis cliquez sur le bouton **Ajouter** pour ajouter l’application.

    ![Zscaler dans la liste des résultats](common/search-new-app.png)

## <a name="assigning-users-to-zscaler"></a>Affectation d’utilisateurs à Zscaler

Azure Active Directory utilise un concept appelé « affectations » pour déterminer les utilisateurs devant recevoir l’accès aux applications sélectionnées. Dans le cadre de l’approvisionnement automatique d’utilisateurs, seuls les utilisateurs et/ou les groupes qui ont été « assignés » à une application dans Azure AD sont synchronisés.

Avant de configurer et activer l’approvisionnement automatique d’utilisateurs, vous devez décider quels utilisateurs et/ou groupes dans Azure AD ont besoin d’accéder à Zscaler. Une fois choisi, vous pouvez affecter ces utilisateurs et/ou groupes à Zscaler en suivant les instructions fournies ici :

* [Affecter un utilisateur ou un groupe à une application d’entreprise](https://docs.microsoft.com/azure/active-directory/active-directory-coreapps-assign-user-azure-portal)

### <a name="important-tips-for-assigning-users-to-zscaler"></a>Conseils importants pour l’affectation d’utilisateurs à Zscaler

* Il est recommandé qu’un seul utilisateur Azure AD est affecté à Zscaler pour tester la configuration du provisionnement automatique d’utilisateurs. Les autres utilisateurs et/ou groupes peuvent être affectés ultérieurement.

* Quand vous assignez un utilisateur à Zscaler, vous devez sélectionner un rôle spécifique à l’application valide (si disponible) dans la boîte de dialogue d’attribution. Les utilisateurs dont le rôle est **Accès par défaut** sont exclus de l’approvisionnement.

## <a name="configuring-automatic-user-provisioning-to-zscaler"></a>Configuration de l’approvisionnement automatique d’utilisateurs à Zscaler

Cette section vous guide tout au long des étapes de configuration du service d’approvisionnement de AD Azure pour créer, mettre à jour et désactiver des utilisateurs et/ou groupes dans Zscaler en fonction des affectations d’utilisateurs et/ou de groupes dans Azure AD.

> [!TIP]
> Vous pouvez également choisir d’activer basée sur SAML SSO pour Zscaler en suivant les instructions fournies dans le [didacticiel l’authentification unique de le Zscaler](zscaler-tutorial.md). L’authentification unique peut être configurée indépendamment de l’attribution automatique d’utilisateurs, bien que ces deux fonctionnalités se complètent.

### <a name="to-configure-automatic-user-provisioning-for-zscaler-in-azure-ad"></a>Pour configurer l’approvisionnement automatique pour Zscaler dans Azure AD :

1. Se connecter à la [Azure portal](https://portal.azure.com) et sélectionnez **Applications d’entreprise**, sélectionnez **toutes les applications**, puis sélectionnez **Zscaler**.

    ![Panneau Applications d’entreprise](common/enterprise-applications.png)

2. Dans la liste des applications, sélectionnez **Zscaler**.

    ![Le lien Zscaler dans la liste des Applications](common/all-applications.png)

3. Sélectionnez l’onglet **Approvisionnement**.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/provisioning-tab.png)

4. Définissez le **Mode d’approvisionnement** sur **Automatique**.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/provisioning-credentials.png)

5. Sous le **informations d’identification administrateur** section, entrée le **URL de locataire** et **jeton Secret** de votre compte de Zscaler, comme décrit à l’étape 6.

6. Pour obtenir le **URL de locataire** et **jeton Secret**, accédez à **Administration > Paramètres d’authentification** dans l’interface utilisateur du portail de Zscaler et cliquez sur **SAML** sous **Type d’authentification**.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/secret-token-1.png)

    Cliquez sur **configurer SAML** pour ouvrir **Configuration SAML** options.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/secret-token-2.png)

    Sélectionnez **Enable SCIM-Based approvisionnement** pour récupérer **une URL de Base** et **le jeton du porteur**, puis enregistrez les paramètres. Copie le **une URL de Base** à **URL de locataire**, et **le jeton du porteur** à **jeton Secret** dans le portail Azure.

7. Après avoir renseigné les champs indiqués à l’étape 5, cliquez sur **tester la connexion** pour vérifier qu’Azure AD peut se connecter à Zscaler. Si la connexion échoue, vérifiez que votre compte de Zscaler dispose des autorisations d’administrateur et réessayez.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/test-connection.png)

8. Dans le champ **E-mail de notification**, entrez l’adresse e-mail d’une personne ou d’un groupe qui doit recevoir les notifications d’erreur d’approvisionnement, puis cochez la case **Envoyer une notification par e-mail en cas de défaillance**.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/notification.png)

9. Cliquez sur **Enregistrer**.

10. Sous le **mappages** section, sélectionnez **synchroniser les utilisateurs Azure Active Directory à Zscaler**.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/user-mappings.png)

11. Passez en revue les attributs utilisateur qui sont synchronisés à partir d’Azure AD à Zscaler dans le **mappage d’attributs** section. Les attributs sélectionnés en tant que **correspondance** propriétés sont utilisées pour faire correspondre les comptes d’utilisateur dans Zscaler pour les opérations de mise à jour. Cliquez sur le bouton **Enregistrer** pour valider les modifications.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/user-attribute-mappings.png)

12. Sous le **mappages** section, sélectionnez **synchroniser les groupes Azure Active Directory à Zscaler**.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/group-mappings.png)

13. Passez en revue les attributs groupe qui sont synchronisés à partir d’Azure AD à Zscaler dans le **mappage d’attributs** section. Les attributs sélectionnés en tant que **correspondance** propriétés sont utilisées pour faire correspondre les groupes dans Zscaler pour les opérations de mise à jour. Cliquez sur le bouton **Enregistrer** pour valider les modifications.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/group-attribute-mappings.png)

14. Pour configurer des filtres d’étendue, reportez-vous aux instructions suivantes fournies dans [Approvisionnement d’applications basé sur les attributs avec filtres d’étendue](./../active-directory-saas-scoping-filters.md).

15. Pour activer l’approvisionnement de service pour Zscaler Azure AD, modifiez le **état d’approvisionnement** à **sur** dans le **paramètres** section.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/provisioning-status.png)

16. Définissez les utilisateurs et/ou groupes que vous aimeriez approvisionner sur Zscaler en choisissant les valeurs souhaitées dans **étendue** dans le **paramètres** section.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/scoping.png)

17. Lorsque vous êtes prêt à effectuer l’approvisionnement, cliquez sur **Enregistrer**.

    ![Configuration de Zscaler](./media/zscaler-provisioning-tutorial/save-provisioning.png)

Cette opération démarre la synchronisation initiale de tous les utilisateurs et/ou groupes définis dans **Étendue** dans la section **Paramètres**. La synchronisation initiale prend plus de temps que les synchronisations suivantes, qui se produisent toutes les 40 minutes environ tant que le service de provisionnement Azure AD est en cours d’exécution. Vous pouvez utiliser la **détails de la synchronisation** section pour surveiller la progression et suivre les liens vers des rapports d’activité, qui décrit toutes les actions effectuées par le service sur Zscaler de provisionnement Azure AD d’approvisionnement.

Pour plus d’informations sur la lecture des journaux d’activité d’approvisionnement Azure AD, consultez [Création de rapports sur l’approvisionnement automatique de comptes d’utilisateur](../active-directory-saas-provisioning-reporting.md).

## <a name="additional-resources"></a>Ressources supplémentaires

* [Gestion de l’approvisionnement de comptes d’utilisateur pour les applications d’entreprise](../manage-apps/configure-automatic-user-provisioning-portal.md)
* [Qu’est-ce que l’accès aux applications et l’authentification unique avec Azure Active Directory ?](../manage-apps/what-is-single-sign-on.md)

## <a name="next-steps"></a>Étapes suivantes

* [Découvrez comment consulter les journaux d’activité et obtenir des rapports sur l’activité d’approvisionnement](../active-directory-saas-provisioning-reporting.md)

<!--Image references-->
[1]: ./media/zscaler-provisioning-tutorial/tutorial-general-01.png
[2]: ./media/zscaler-provisioning-tutorial/tutorial-general-02.png
[3]: ./media/zscaler-provisioning-tutorial/tutorial-general-03.png
