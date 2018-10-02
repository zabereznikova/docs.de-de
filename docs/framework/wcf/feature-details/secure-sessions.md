---
title: Sichere Sitzungen
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
author: BrucePerlerMS
ms.openlocfilehash: 09c261afb2c64a46fc1f4619c4ec6b2e87b3fbbf
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48027324"
---
# <a name="secure-sessions"></a>Sichere Sitzungen
Ein Feature von Windows Communication Foundation (WCF) ist die zuverlässige Sitzungen, die garantieren, dass Nachrichten in der Reihenfolge empfangen werden, die sie gesendet wurden. Die Themen in diesem Abschnitt erläutern die Sicherheitsaspekte, die bei der Erstellung einer zuverlässigen Sitzung beachtet werden sollten. Weitere Informationen zu zuverlässigen Sitzungen finden Sie unter [mithilfe von Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
> [!NOTE]
>  Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne zustandsbehaftete Token für den Sicherheitskontext (SCT). Wenn Token für den Sicherheitszustandskontext (SCTs) mit einem Identitätswechsel verwendet werden, wird ein <xref:System.InvalidOperationException> ausgelöst. Weitere Informationen finden Sie unter [nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|||  
|-|-|  
|[Sichere Unterhaltungen und sichere Sitzungen.](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|Sichere Konversationen und sichere Sitzungen werden synonym verwendet. In diesem Thema wird erläutert, wie eine sichere Konversation funktioniert und wann und warum das Muster verwendet wird.|  
|[Vorgehensweise: Erstellen einer sicheren Sitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|Stellt exemplarisch die Grundlagen der Erstellung einer sicheren Sitzung vor.|  
|[Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|Stellt exemplarisch die Schritte der Erstellung einer Webfarm vor, die den Zustand und Sitzungen mit Clients beibehält.|  
|[Sicherheitsüberlegungen für sichere Sitzungen](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|Beschreibt besondere Überlegungen für sichere Sitzungen.|  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Sitzungen, Instanzerstellung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [Entwerfen und Implementieren von Diensten](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Aktivieren der Nachrichtenreplayerkennung](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 [Replayangriffe](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
