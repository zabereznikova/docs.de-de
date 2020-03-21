---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152423"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="0ca05-101">\<ActivityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="0ca05-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="0ca05-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="0ca05-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="0ca05-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0ca05-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="0ca05-104">Weitere Informationen zum Nachverfolgen von Profilabfragen finden Sie unter [Nachverfolgungsprofile](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0ca05-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0ca05-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ca05-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0ca05-106">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0ca05-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="0ca05-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Tracking->**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="0ca05-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="0ca05-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="0ca05-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="0ca05-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Workflow->**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0ca05-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="0ca05-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ActivityScheduledQueries>**</span><span class="sxs-lookup"><span data-stu-id="0ca05-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca05-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ca05-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ca05-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0ca05-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0ca05-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ca05-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ca05-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="0ca05-114">Attributes</span></span>  
 <span data-ttu-id="0ca05-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="0ca05-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ca05-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ca05-116">Child Elements</span></span>  
  
|<span data-ttu-id="0ca05-117">Element</span><span class="sxs-lookup"><span data-stu-id="0ca05-117">Element</span></span>|<span data-ttu-id="0ca05-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ca05-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ca05-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="0ca05-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="0ca05-120">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="0ca05-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ca05-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ca05-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0ca05-122">Element</span><span class="sxs-lookup"><span data-stu-id="0ca05-122">Element</span></span>|<span data-ttu-id="0ca05-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ca05-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ca05-124">\<Workflow-></span><span class="sxs-lookup"><span data-stu-id="0ca05-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="0ca05-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId-Eigenschaft** identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="0ca05-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ca05-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ca05-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0ca05-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0ca05-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0ca05-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="0ca05-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
