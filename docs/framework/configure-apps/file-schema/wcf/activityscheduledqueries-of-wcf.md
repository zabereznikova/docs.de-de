---
title: '&lt;activityScheduledQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 35bcb0dc0c33d30eee566869579edb32f131f495
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452695"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="5a7f0-102">&lt;activityScheduledQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="5a7f0-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="5a7f0-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="5a7f0-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="5a7f0-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="5a7f0-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="5a7f0-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5a7f0-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5a7f0-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5a7f0-106">\<system.serviceModel></span></span>  
<span data-ttu-id="5a7f0-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="5a7f0-107">\<tracking></span></span>  
<span data-ttu-id="5a7f0-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="5a7f0-108">\<profiles></span></span>  
<span data-ttu-id="5a7f0-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5a7f0-109">\<trackingProfile></span></span>  
<span data-ttu-id="5a7f0-110">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="5a7f0-110">\<workflow></span></span>  
<span data-ttu-id="5a7f0-111">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="5a7f0-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a7f0-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a7f0-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"   
                                  childActivityName="String"/>
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a7f0-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5a7f0-113">Attributes and elements</span></span>  

<span data-ttu-id="5a7f0-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a7f0-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a7f0-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="5a7f0-115">Attributes</span></span>  

<span data-ttu-id="5a7f0-116">Keine</span><span class="sxs-lookup"><span data-stu-id="5a7f0-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a7f0-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a7f0-117">Child elements</span></span>  
  
|<span data-ttu-id="5a7f0-118">Element</span><span class="sxs-lookup"><span data-stu-id="5a7f0-118">Element</span></span>|<span data-ttu-id="5a7f0-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a7f0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a7f0-120">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="5a7f0-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="5a7f0-121">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="5a7f0-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a7f0-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a7f0-122">Parent elements</span></span>  
  
|<span data-ttu-id="5a7f0-123">Element</span><span class="sxs-lookup"><span data-stu-id="5a7f0-123">Element</span></span>|<span data-ttu-id="5a7f0-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a7f0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a7f0-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5a7f0-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5a7f0-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="5a7f0-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a7f0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a7f0-127">See also</span></span>  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="5a7f0-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="5a7f0-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5a7f0-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="5a7f0-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
