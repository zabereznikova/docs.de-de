---
title: '&lt;activityScheduledQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 6192fea9a520a3f453593e5efac964a5d32a492f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756292"
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="ea01b-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="ea01b-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="ea01b-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="ea01b-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="ea01b-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ea01b-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="ea01b-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ea01b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ea01b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ea01b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ea01b-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="ea01b-107">\<tracking></span></span>  
<span data-ttu-id="ea01b-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ea01b-108">\<trackingProfile></span></span>  
<span data-ttu-id="ea01b-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="ea01b-109">\<workflow></span></span>  
<span data-ttu-id="ea01b-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="ea01b-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea01b-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea01b-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea01b-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ea01b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ea01b-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea01b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea01b-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="ea01b-114">Attributes</span></span>  
 <span data-ttu-id="ea01b-115">Keine</span><span class="sxs-lookup"><span data-stu-id="ea01b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea01b-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea01b-116">Child Elements</span></span>  
  
|<span data-ttu-id="ea01b-117">Element</span><span class="sxs-lookup"><span data-stu-id="ea01b-117">Element</span></span>|<span data-ttu-id="ea01b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea01b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea01b-119">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="ea01b-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="ea01b-120">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="ea01b-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea01b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea01b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ea01b-122">Element</span><span class="sxs-lookup"><span data-stu-id="ea01b-122">Element</span></span>|<span data-ttu-id="ea01b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea01b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea01b-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ea01b-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ea01b-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ea01b-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea01b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea01b-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="ea01b-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ea01b-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ea01b-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ea01b-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
