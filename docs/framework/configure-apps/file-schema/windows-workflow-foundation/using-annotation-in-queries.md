---
title: Verwenden von Anmerkungen in Abfragen
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: fd2d98852ca44e3485ddcf4be29d505b39011698
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614426"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="23805-102">Verwenden von Anmerkungen in Abfragen</span><span class="sxs-lookup"><span data-stu-id="23805-102">Using Annotation in Queries</span></span>
<span data-ttu-id="23805-103">Anmerkungen ermöglichen es Ihnen, Überwachungsdatensätze mit einem beliebigen Wert zu markieren, der nach der Erstellung konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="23805-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="23805-104">Sie können z. B. mehrere Überwachungsdatensätze in mehreren Workflows mit "Mailserver" gekennzeichnet werden == "Mail Server1 markieren".</span><span class="sxs-lookup"><span data-stu-id="23805-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="23805-105">Auf diese Weise können alle Datensätze mit diesem Tag einfach gefunden werden, wenn zu einem späteren Zeitpunkt Überwachungsdatensätze abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="23805-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="23805-106">Hinzufügen von Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="23805-106">Adding Annotations</span></span>  
 <span data-ttu-id="23805-107">Eine Anmerkung kann wie im folgenden Beispiel einer Nachverfolgungsabfrage hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="23805-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="23805-108">Diese Nachverfolgungsabfrageelemente können verwendet werden, um ein Nachverfolgungsprofil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23805-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="23805-109">Ein Nachverfolgungsprofil kann entweder in Form einer Konfiguration oder im Code erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="23805-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23805-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23805-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="23805-111">\<participants></span><span class="sxs-lookup"><span data-stu-id="23805-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)
- [<span data-ttu-id="23805-112">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="23805-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="23805-113">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="23805-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
