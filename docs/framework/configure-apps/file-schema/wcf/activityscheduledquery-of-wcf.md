---
title: '&lt;activityScheduledQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 4efd6ba13e8a54d3338c25b077477d4abdbe9ab5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="ce255-102">&lt;activityScheduledQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="ce255-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="ce255-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="ce255-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="ce255-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ce255-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="ce255-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ce255-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="ce255-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ce255-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ce255-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="ce255-107">\<tracking></span></span>  
<span data-ttu-id="ce255-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ce255-108">\<trackingProfile></span></span>  
<span data-ttu-id="ce255-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="ce255-109">\<workflow></span></span>  
<span data-ttu-id="ce255-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="ce255-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="ce255-111">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="ce255-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce255-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce255-112">Syntax</span></span>  
  
```xml
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce255-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce255-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ce255-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce255-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce255-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce255-115">Attributes</span></span>  
  
|<span data-ttu-id="ce255-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="ce255-116">Attribute</span></span>|<span data-ttu-id="ce255-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce255-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce255-118">activityName</span><span class="sxs-lookup"><span data-stu-id="ce255-118">activityName</span></span>|<span data-ttu-id="ce255-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="ce255-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="ce255-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="ce255-120">childActivityName</span></span>|<span data-ttu-id="ce255-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="ce255-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce255-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce255-122">Child Elements</span></span>  
 <span data-ttu-id="ce255-123">Keine</span><span class="sxs-lookup"><span data-stu-id="ce255-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce255-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce255-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ce255-125">Element</span><span class="sxs-lookup"><span data-stu-id="ce255-125">Element</span></span>|<span data-ttu-id="ce255-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce255-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce255-127">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="ce255-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="ce255-128">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="ce255-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce255-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce255-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="ce255-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ce255-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ce255-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ce255-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
