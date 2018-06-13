---
title: '&lt;activityScheduledQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 946406e5513a0fee6793071c397f61bf1fe71c65
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744888"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="b7c5e-102">&lt;activityScheduledQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="b7c5e-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="b7c5e-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="b7c5e-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b7c5e-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="b7c5e-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="b7c5e-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b7c5e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="b7c5e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b7c5e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b7c5e-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="b7c5e-107">\<tracking></span></span>  
<span data-ttu-id="b7c5e-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b7c5e-108">\<trackingProfile></span></span>  
<span data-ttu-id="b7c5e-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="b7c5e-109">\<workflow></span></span>  
<span data-ttu-id="b7c5e-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="b7c5e-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7c5e-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7c5e-111">Syntax</span></span>  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7c5e-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b7c5e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b7c5e-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b7c5e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7c5e-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="b7c5e-114">Attributes</span></span>  
 <span data-ttu-id="b7c5e-115">Keine</span><span class="sxs-lookup"><span data-stu-id="b7c5e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b7c5e-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7c5e-116">Child Elements</span></span>  
  
|<span data-ttu-id="b7c5e-117">Element</span><span class="sxs-lookup"><span data-stu-id="b7c5e-117">Element</span></span>|<span data-ttu-id="b7c5e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7c5e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7c5e-119">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="b7c5e-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="b7c5e-120">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="b7c5e-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7c5e-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7c5e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b7c5e-122">Element</span><span class="sxs-lookup"><span data-stu-id="b7c5e-122">Element</span></span>|<span data-ttu-id="b7c5e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7c5e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7c5e-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b7c5e-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b7c5e-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="b7c5e-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7c5e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7c5e-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="b7c5e-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b7c5e-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b7c5e-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="b7c5e-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
