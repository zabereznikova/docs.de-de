---
title: Verwenden von Anmerkungen in Abfragen
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 3dd5d19cc303314386ae62ba67f7eec978f6d80b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185365"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="c7f47-102">Verwenden von Anmerkungen in Abfragen</span><span class="sxs-lookup"><span data-stu-id="c7f47-102">Using Annotation in Queries</span></span>

<span data-ttu-id="c7f47-103">Anmerkungen ermöglichen es Ihnen, Überwachungsdatensätze mit einem beliebigen Wert zu markieren, der nach der Erstellung konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7f47-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="c7f47-104">Beispielsweise kann es vorkommen, dass mehrere Überwachungsdaten Sätze in mehreren Workflows mit "Mail Server" = = "Mail Server1" gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="c7f47-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="c7f47-105">Auf diese Weise können alle Datensätze mit diesem Tag einfach gefunden werden, wenn zu einem späteren Zeitpunkt Überwachungsdatensätze abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="c7f47-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="c7f47-106">Hinzufügen von Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c7f47-106">Adding Annotations</span></span>  

 <span data-ttu-id="c7f47-107">Eine Anmerkung kann wie im folgenden Beispiel einer Nachverfolgungsabfrage hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c7f47-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="c7f47-108">Diese Nachverfolgungsabfrageelemente können verwendet werden, um ein Nachverfolgungsprofil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c7f47-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="c7f47-109">Ein Nachverfolgungsprofil kann entweder in Form einer Konfiguration oder im Code erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c7f47-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7f47-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7f47-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [<span data-ttu-id="c7f47-111">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c7f47-111">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c7f47-112">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="c7f47-112">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
