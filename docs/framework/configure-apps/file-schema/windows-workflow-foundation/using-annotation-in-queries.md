---
title: Verwenden von Anmerkungen in Abfragen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8713d84af96fa69df5ace33d76ec21560dab2c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-annotation-in-queries"></a>Verwenden von Anmerkungen in Abfragen
Anmerkungen ermöglichen es Ihnen, Überwachungsdatensätze mit einem beliebigen Wert zu markieren, der nach der Erstellung konfiguriert werden kann. Sie können z. B. mehrere Überwachungsdatensätze in mehreren Workflows mit "Mail Server" == "Mail Server1 markieren". Auf diese Weise können alle Datensätze mit diesem Tag einfach gefunden werden, wenn zu einem späteren Zeitpunkt Überwachungsdatensätze abgefragt werden.  
  
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
>  Diese Nachverfolgungsabfrageelemente können verwendet werden, um ein Nachverfolgungsprofil zu erstellen. Ein Nachverfolgungsprofil kann entweder in Form einer Konfiguration oder im Code erstellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [\<Teilnehmer >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)  
 [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
