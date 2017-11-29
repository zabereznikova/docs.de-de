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
# <a name="using-annotation-in-queries"></a><span data-ttu-id="ef03f-102">Verwenden von Anmerkungen in Abfragen</span><span class="sxs-lookup"><span data-stu-id="ef03f-102">Using Annotation in Queries</span></span>
<span data-ttu-id="ef03f-103">Anmerkungen ermöglichen es Ihnen, Überwachungsdatensätze mit einem beliebigen Wert zu markieren, der nach der Erstellung konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ef03f-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="ef03f-104">Sie können z. B. mehrere Überwachungsdatensätze in mehreren Workflows mit "Mail Server" == "Mail Server1 markieren".</span><span class="sxs-lookup"><span data-stu-id="ef03f-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="ef03f-105">Auf diese Weise können alle Datensätze mit diesem Tag einfach gefunden werden, wenn zu einem späteren Zeitpunkt Überwachungsdatensätze abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="ef03f-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="ef03f-106">Hinzufügen von Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="ef03f-106">Adding Annotations</span></span>  
 <span data-ttu-id="ef03f-107">Eine Anmerkung kann wie im folgenden Beispiel einer Nachverfolgungsabfrage hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ef03f-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="ef03f-108">Diese Nachverfolgungsabfrageelemente können verwendet werden, um ein Nachverfolgungsprofil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ef03f-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="ef03f-109">Ein Nachverfolgungsprofil kann entweder in Form einer Konfiguration oder im Code erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ef03f-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef03f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef03f-110">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="ef03f-111">\<Teilnehmer ></span><span class="sxs-lookup"><span data-stu-id="ef03f-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)  
 [<span data-ttu-id="ef03f-112">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ef03f-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ef03f-113">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ef03f-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
