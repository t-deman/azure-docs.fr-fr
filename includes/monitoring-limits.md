---
title: Fichier Include
description: Fichier Include
services: azure-monitor
author: rboucher
tags: azure-service-management
ms.topic: include
ms.date: 02/07/2019
ms.author: robb
ms.custom: include file
ms.openlocfilehash: 4700573d3f5319599a6437d092e20d8013d2f7fb
ms.sourcegitcommit: 956749f17569a55bcafba95aef9abcbb345eb929
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58632950"
---
| Ressource | Limite par défaut | Limite maximale |
| --- | --- | --- |
| Paramètres de mise à l'échelle automatique |100 par région et par abonnement. | Identique à la valeur par défaut. |
| Alertes de métrique (classique) |100 règles d’alerte actives par abonnement. | Appelez le support. |
| Alertes de métrique |100 règles d’alerte actives par abonnement. | Appelez le support. |
| Groupes d’actions |2 000 groupes d’actions par abonnement. | Appelez le support. |

**Limites spécifiques à un groupe d’action**

| Ressource | Limite par défaut | Limite maximale |
| --- | --- | --- |
| Envoi (Push) d'application Azure | 10 actions d’application azure par groupe d’actions. | Appelez le support. |
| Email | 1 000 actions de messagerie dans un groupe d’actions. Consultez également le [informations de limitation du débit](../articles/azure-monitor/platform/alerts-rate-limiting.md). | Appelez le support. |
| ITSM | 10 actions ITSM dans un groupe d’actions. | Appelez le support. | 
| Application logique | 10 actions d’application logique dans un groupe d’actions. | Appelez le support. |
| Runbook | 10 actions de runbook dans un groupe d’actions. | Appelez le support. |
| sms | 10 actions de SMS dans un groupe d’actions. Consultez également le [informations de limitation du débit](../articles/azure-monitor/platform/alerts-rate-limiting.md). | Appelez le support. |
| Voix | 10 actions de voice dans un groupe d’actions. Consultez également le [informations de limitation du débit](../articles/azure-monitor/platform/alerts-rate-limiting.md). | Appelez le support. |
| webhook | 10 actions de webhook dans un groupe d’actions.  Nombre maximal d’appels de webhook est 1500 par minute par abonnement. Autres limites sont disponibles à l’adresse [les informations spécifiques à certaines actions](../articles/azure-monitor/platform/action-groups.md#action-specific-information).  | Appelez le support. |
