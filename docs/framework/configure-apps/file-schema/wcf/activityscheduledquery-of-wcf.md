---
title: '&lt;activityScheduledQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 9a53d72316dad0178f24e05656a4fb4531b88aec
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087764"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="28650-102">&lt;activityScheduledQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="28650-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="28650-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="28650-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="28650-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="28650-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="28650-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="28650-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="28650-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="28650-106">\<system.serviceModel></span></span>  
<span data-ttu-id="28650-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="28650-107">\<tracking></span></span>  
<span data-ttu-id="28650-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="28650-108">\<trackingProfile></span></span>  
<span data-ttu-id="28650-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="28650-109">\<workflow></span></span>  
<span data-ttu-id="28650-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="28650-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="28650-111">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="28650-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28650-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="28650-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"   
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking> 
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28650-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="28650-113">Attributes and Elements</span></span>  
 <span data-ttu-id="28650-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28650-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28650-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="28650-115">Attributes</span></span>  
  
|<span data-ttu-id="28650-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="28650-116">Attribute</span></span>|<span data-ttu-id="28650-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28650-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28650-118">activityName</span><span class="sxs-lookup"><span data-stu-id="28650-118">activityName</span></span>|<span data-ttu-id="28650-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="28650-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="28650-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="28650-120">childActivityName</span></span>|<span data-ttu-id="28650-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="28650-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28650-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28650-122">Child Elements</span></span>  
 <span data-ttu-id="28650-123">Keine</span><span class="sxs-lookup"><span data-stu-id="28650-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28650-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28650-124">Parent Elements</span></span>  
  
|<span data-ttu-id="28650-125">Element</span><span class="sxs-lookup"><span data-stu-id="28650-125">Element</span></span>|<span data-ttu-id="28650-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28650-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28650-127">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="28650-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="28650-128">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="28650-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28650-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28650-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="28650-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="28650-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="28650-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="28650-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
