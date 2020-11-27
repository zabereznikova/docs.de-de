---
title: Sichere Sitzungen
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: fd8406af0c37981b2ddc7ab8ddb0c82c63cbc0b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288545"
---
# <a name="secure-sessions"></a>Sichere Sitzungen

Eine Funktion von Windows Communication Foundation (WCF) sind zuverlässige Sitzungen, die garantieren, dass Nachrichten in der Reihenfolge empfangen werden, in der Sie gesendet wurden. Die Themen in diesem Abschnitt erläutern die Sicherheitsaspekte, die bei der Erstellung einer zuverlässigen Sitzung beachtet werden sollten. Weitere Informationen zu zuverlässigen Sitzungen finden Sie unter [Verwenden von Sitzungen](../using-sessions.md).  
  
> [!NOTE]
> Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne zustandsbehaftete Token für den Sicherheitskontext (SCT). Wenn zustandsbehaftete Token für den Sicherheitskontext (SCTs) mit einem Identitätswechsel verwendet werden, wird ein <xref:System.InvalidOperationException> ausgelöst. Weitere Informationen finden Sie unter [nicht unterstützte Szenarien](unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|||  
|-|-|  
|[Sichere Unterhaltungen und sichere Sitzungen.](secure-conversations-and-secure-sessions.md)|Sichere Konversationen und sichere Sitzungen werden synonym verwendet. In diesem Thema wird erläutert, wie eine sichere Konversation funktioniert und wann und warum das Muster verwendet wird.|  
|[Vorgehensweise: Erstellen einer sicheren Sitzung](how-to-create-a-secure-session.md)|Stellt exemplarisch die Grundlagen der Erstellung einer sicheren Sitzung vor.|  
|[Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung](how-to-create-a-security-context-token-for-a-secure-session.md)|Stellt exemplarisch die Schritte der Erstellung einer Webfarm vor, die den Zustand und Sitzungen mit Clients beibehält.|  
|[Sicherheitsüberlegungen für Sicherheitssitzungen](security-considerations-for-secure-sessions.md)|Beschreibt besondere Überlegungen für sichere Sitzungen.|  
  
## <a name="reference"></a>Referenz  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Sitzungen, Instanziierung und Parallelität](sessions-instancing-and-concurrency.md)  
  
 [Entwerfen und Implementieren von Diensten](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung](how-to-enable-message-replay-detection.md)
- [Wiederholungsangriffe](replay-attacks.md)
- [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](how-to-create-a-service-that-requires-sessions.md)
