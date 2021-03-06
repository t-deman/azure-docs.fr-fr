---
title: Présentation d’Azure Security Center pour le module de sécurité IoT pour IoT Edge | Microsoft Docs
description: Comprendre l’architecture et les fonctionnalités d’Azure Security Center pour le module de sécurité IoT pour IoT Edge.
services: asc-for-iot
ms.service: ascforiot
documentationcenter: na
author: mlottner
manager: rkarlin
editor: ''
ms.assetid: e78523ae-d70a-456a-818d-f8b1b025d7cb
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/25/2019
ms.author: mlottner
ms.openlocfilehash: 847d6238bd42dc7da723dcc9acd47ed09c16dbf9
ms.sourcegitcommit: 0568c7aefd67185fd8e1400aed84c5af4f1597f9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65200577"
---
# <a name="azure-iot-edge-security-module"></a>Module de sécurité Azure IoT Edge

> [!IMPORTANT]
> Azure Security Center pour IoT est disponible en préversion publique.
> Cette version préliminaire est fournie sans contrat de niveau de service et n’est pas recommandée pour la production worklo§1ads. Certaines fonctionnalités peuvent être limitées ou non prises en charge. Pour plus d’informations, consultez [Conditions d’Utilisation Supplémentaires relatives aux Évaluations Microsoft Azure](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).

[Azure IoT Edge](https://docs.microsoft.com/azure/iot-edge/) fournit de puissantes fonctionnalités pour gérer et effectuer des flux de travail à la périphérie.
La partie clé IoT Edge joue dans les environnements IoT rendre particulièrement attractif pour les personnes malveillantes.

Azure Security Center (ASC) pour le module de sécurité IoT fournit une solution de sécurité complète pour votre IoT Edge appareils.
ASC pour le module IoT collecte, agrège et analyse les données de sécurité brute à partir de votre système d’exploitation et le système de conteneur dans les alertes et les recommandations de sécurité actionnables.

Similaire à ASC pour les agents de sécurité IoT pour les appareils IoT, l’ASC pour le module IoT Edge est hautement personnalisable via son jumeau de module.
Consultez [configurer votre agent](how-to-agent-configuration.md) pour en savoir plus.

ASC pour le module de sécurité IoT pour IoT Edge offre les fonctionnalités suivantes :

- Collecte les événements de sécurité brute à partir du système d’exploitation sous-jacent (Linux) et les systèmes de conteneur de IoT Edge.
  
  Consultez [ASC pour configurer l’agent IoT](how-to-agent-configuration.md) pour en savoir plus sur les collecteurs de données de sécurité disponibles.

- Analyse des manifestes de déploiement IoT Edge.

- Regroupe les événements de sécurité brute dans les messages envoyés via [IoT Edge Hub](https://docs.microsoft.com/azure/iot-edge/iot-edge-runtime#iot-edge-hub).

- Supprimer la configuration via l’utilisation de la représentation de module de sécurité.

  Consultez [configurer un ASC pour l’agent IoT](how-to-agent-configuration.md) pour en savoir plus.

ASC pour le module de sécurité IoT pour IoT Edge s’exécute dans un mode privilégié sous IoT Edge.
Mode privilégié est nécessaire pour autoriser le module pour surveiller le système d’exploitation et les autres modules IoT Edge.

## <a name="agent-supported-platforms"></a>Plateformes d’agent pris en charge

ASC pour le module de sécurité IoT pour IoT Edge est actuellement uniquement disponible pour Linux.

## <a name="next-steps"></a>Étapes suivantes

Dans cet article, vous avez appris sur l’architecture et les fonctionnalités de ASC pour le module de sécurité IoT pour IoT Edge.

Pour continuer la mise en route avec ASC pour un déploiement IoT, utilisez les articles suivants :

- Déployer [module de sécurité pour IoT Edge](how-to-deploy-edge.md)
- Découvrez comment [configurer votre module de sécurité](how-to-agent-configuration.md)
- Passez en revue l’ASC pour IoT [conditions préalables de Service](service-prerequisites.md)
- Découvrez comment [activer l’ASC pour le service IoT dans votre IoT Hub](quickstart-onboard-iot-hub.md)
- En savoir plus sur le service à partir de la [ASC pour IoT FAQ](resources-frequently-asked-questions.md)