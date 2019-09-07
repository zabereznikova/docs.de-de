---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: a43242e2f22c48a57c11f6f03657d7d3de27ff48
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398983"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="87682-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="87682-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="87682-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="87682-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="87682-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="87682-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="87682-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="87682-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="87682-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87682-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87682-106">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="87682-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="87682-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="87682-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="87682-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="87682-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="87682-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="87682-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="87682-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityscheduledqueries->**</span><span class="sxs-lookup"><span data-stu-id="87682-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87682-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="87682-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87682-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="87682-112">Attributes and Elements</span></span>  
 <span data-ttu-id="87682-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87682-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87682-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="87682-114">Attributes</span></span>  
 <span data-ttu-id="87682-115">Keine</span><span class="sxs-lookup"><span data-stu-id="87682-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="87682-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87682-116">Child Elements</span></span>  
  
|<span data-ttu-id="87682-117">Element</span><span class="sxs-lookup"><span data-stu-id="87682-117">Element</span></span>|<span data-ttu-id="87682-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87682-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87682-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="87682-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="87682-120">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="87682-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87682-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87682-121">Parent Elements</span></span>  
  
|<span data-ttu-id="87682-122">Element</span><span class="sxs-lookup"><span data-stu-id="87682-122">Element</span></span>|<span data-ttu-id="87682-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87682-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87682-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="87682-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="87682-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="87682-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87682-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87682-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="87682-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="87682-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="87682-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="87682-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
