---
title: Sichere Sitzungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 65a54c06efffb2e3167c77bd109a50a31b971add
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="secure-sessions"></a>Sichere Sitzungen
Eine Funktion von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sind zuverlässige Sitzungen, die garantieren, dass Meldungen in der Reihenfolge empfangen werden, in der sie gesendet wurden. Die Themen in diesem Abschnitt erläutern die Sicherheitsaspekte, die bei der Erstellung einer zuverlässigen Sitzung beachtet werden sollten. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]zuverlässige Sitzungen finden Sie unter [mit Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
> [!NOTE]
>  Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne zustandsbehaftete Token für den Sicherheitskontext (SCT). Wenn Token für den Sicherheitszustandskontext (SCTs) mit einem Identitätswechsel verwendet werden, wird ein <xref:System.InvalidOperationException> ausgelöst. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|||  
|-|-|  
|[Sichere Unterhaltungen und sichere Sitzungen.](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|Sichere Konversationen und sichere Sitzungen werden synonym verwendet. In diesem Thema wird erläutert, wie eine sichere Konversation funktioniert und wann und warum das Muster verwendet wird.|  
|[Vorgehensweise: Erstellen einer sicheren Sitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|Stellt exemplarisch die Grundlagen der Erstellung einer sicheren Sitzung vor.|  
|[Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|Stellt exemplarisch die Schritte der Erstellung einer Webfarm vor, die den Zustand und Sitzungen mit Clients beibehält.|  
|[Sicherheitsüberlegungen für sichere Sitzungen](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|Beschreibt besondere Überlegungen für sichere Sitzungen.|  
  
## <a name="reference"></a>Verweis  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Sitzungen, Instanzerstellung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [Entwerfen und Implementieren von Diensten](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Aktivieren der Nachrichtenreplayerkennung](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 [Replayangriffe](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
