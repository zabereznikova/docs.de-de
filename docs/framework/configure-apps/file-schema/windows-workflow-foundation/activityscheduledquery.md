---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: d49c6d933a09dce5d657746358f1a5f716ab639b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790415"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="18caa-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="18caa-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="18caa-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="18caa-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="18caa-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="18caa-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="18caa-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="18caa-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="18caa-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="18caa-105">\<system.serviceModel></span></span>  
<span data-ttu-id="18caa-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="18caa-106">\<tracking></span></span>  
<span data-ttu-id="18caa-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="18caa-107">\<trackingProfile></span></span>  
<span data-ttu-id="18caa-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="18caa-108">\<workflow></span></span>  
<span data-ttu-id="18caa-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="18caa-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="18caa-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="18caa-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18caa-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="18caa-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18caa-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="18caa-112">Attributes and Elements</span></span>  
 <span data-ttu-id="18caa-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="18caa-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18caa-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="18caa-114">Attributes</span></span>  
  
|<span data-ttu-id="18caa-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="18caa-115">Attribute</span></span>|<span data-ttu-id="18caa-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18caa-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18caa-117">activityName</span><span class="sxs-lookup"><span data-stu-id="18caa-117">activityName</span></span>|<span data-ttu-id="18caa-118">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="18caa-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="18caa-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="18caa-119">childActivityName</span></span>|<span data-ttu-id="18caa-120">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="18caa-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18caa-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="18caa-121">Child Elements</span></span>  
 <span data-ttu-id="18caa-122">Keine</span><span class="sxs-lookup"><span data-stu-id="18caa-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18caa-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="18caa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="18caa-124">Element</span><span class="sxs-lookup"><span data-stu-id="18caa-124">Element</span></span>|<span data-ttu-id="18caa-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18caa-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18caa-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="18caa-126">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="18caa-127">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="18caa-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18caa-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18caa-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="18caa-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="18caa-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="18caa-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="18caa-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
