---
title: '&lt;customTrackingQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: aa1e7ff4d53cbd40b168c3cc800a23dbcddc28f5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755889"
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="7eacf-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="7eacf-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="7eacf-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="7eacf-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="7eacf-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="7eacf-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="7eacf-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7eacf-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="7eacf-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7eacf-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7eacf-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="7eacf-107">\<tracking></span></span>  
<span data-ttu-id="7eacf-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7eacf-108">\<trackingProfile></span></span>  
<span data-ttu-id="7eacf-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="7eacf-109">\<workflow></span></span>  
<span data-ttu-id="7eacf-110">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="7eacf-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eacf-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="7eacf-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7eacf-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7eacf-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7eacf-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7eacf-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7eacf-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="7eacf-114">Attributes</span></span>  
 <span data-ttu-id="7eacf-115">Keine</span><span class="sxs-lookup"><span data-stu-id="7eacf-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7eacf-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7eacf-116">Child Elements</span></span>  
  
|<span data-ttu-id="7eacf-117">Element</span><span class="sxs-lookup"><span data-stu-id="7eacf-117">Element</span></span>|<span data-ttu-id="7eacf-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7eacf-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7eacf-119">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="7eacf-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="7eacf-120">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="7eacf-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7eacf-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7eacf-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7eacf-122">Element</span><span class="sxs-lookup"><span data-stu-id="7eacf-122">Element</span></span>|<span data-ttu-id="7eacf-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7eacf-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7eacf-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="7eacf-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="7eacf-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7eacf-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7eacf-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7eacf-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="7eacf-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="7eacf-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="7eacf-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="7eacf-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
