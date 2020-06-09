---
title: Sichere Sitzungen
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: cb02adc7514e27175088e7664b12e45bc8ca5cd9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590084"
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
