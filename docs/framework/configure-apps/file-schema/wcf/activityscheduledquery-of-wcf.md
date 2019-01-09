---
title: '&lt;activityScheduledQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: fd7830bc178de0693f0632cea3b390d792408ec1
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147876"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="3bc7d-102">&lt;activityScheduledQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="3bc7d-102">&lt;activityScheduledQuery&gt; of WCF</span></span>

<span data-ttu-id="3bc7d-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="3bc7d-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="3bc7d-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3bc7d-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="3bc7d-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3bc7d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3bc7d-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3bc7d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3bc7d-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="3bc7d-107">\<tracking></span></span>  
<span data-ttu-id="3bc7d-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="3bc7d-108">\<profiles></span></span>  
<span data-ttu-id="3bc7d-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3bc7d-109">\<trackingProfile></span></span>  
<span data-ttu-id="3bc7d-110">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="3bc7d-110">\<workflow></span></span>  
<span data-ttu-id="3bc7d-111">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="3bc7d-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="3bc7d-112">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="3bc7d-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bc7d-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bc7d-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bc7d-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3bc7d-114">Attributes and elements</span></span>  

<span data-ttu-id="3bc7d-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3bc7d-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bc7d-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="3bc7d-116">Attributes</span></span>  
  
|<span data-ttu-id="3bc7d-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="3bc7d-117">Attribute</span></span>|<span data-ttu-id="3bc7d-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bc7d-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="3bc7d-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="3bc7d-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="3bc7d-120">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="3bc7d-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3bc7d-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3bc7d-121">Child elements</span></span>

<span data-ttu-id="3bc7d-122">Keine</span><span class="sxs-lookup"><span data-stu-id="3bc7d-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="3bc7d-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3bc7d-123">Parent elements</span></span>  
  
|<span data-ttu-id="3bc7d-124">Element</span><span class="sxs-lookup"><span data-stu-id="3bc7d-124">Element</span></span>|<span data-ttu-id="3bc7d-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bc7d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bc7d-126">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="3bc7d-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="3bc7d-127">Eine Auflistung von Abfragen, die verwendet werden, um eine Aktivität, die für die Ausführung eingeplant, von einer übergeordneten Aktivität zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="3bc7d-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bc7d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bc7d-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="3bc7d-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3bc7d-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3bc7d-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3bc7d-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
