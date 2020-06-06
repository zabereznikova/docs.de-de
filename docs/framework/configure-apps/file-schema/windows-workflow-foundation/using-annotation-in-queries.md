---
title: Verwenden von Anmerkungen in Abfragen
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 728408e744bc1eca62158fab1a7a17e985fe3b6c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69947286"
---
# <a name="using-annotation-in-queries"></a>Verwenden von Anmerkungen in Abfragen
Anmerkungen ermöglichen es Ihnen, Überwachungsdatensätze mit einem beliebigen Wert zu markieren, der nach der Erstellung konfiguriert werden kann. Beispielsweise kann es vorkommen, dass mehrere Überwachungsdaten Sätze in mehreren Workflows mit "Mail Server" = = "Mail Server1" gekennzeichnet werden. Auf diese Weise können alle Datensätze mit diesem Tag einfach gefunden werden, wenn zu einem späteren Zeitpunkt Überwachungsdatensätze abgefragt werden.  
  
## <a name="adding-annotations"></a>Hinzufügen von Anmerkungen  
 Eine Anmerkung kann wie im folgenden Beispiel einer Nachverfolgungsabfrage hinzugefügt werden.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
> [!NOTE]
> Diese Nachverfolgungsabfrageelemente können verwendet werden, um ein Nachverfolgungsprofil zu erstellen. Ein Nachverfolgungsprofil kann entweder in Form einer Konfiguration oder im Code erstellt werden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [Nachverfolgung und Ablaufverfolgung für Workflows](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Überwachungsprofile](../../../windows-workflow-foundation/tracking-profiles.md)
