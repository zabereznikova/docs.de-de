---
title: '&lt;customTrackingQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 757bbe500ec3edccef465b7ff23b2c974e4a5011
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598840"
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="82159-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="82159-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="82159-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="82159-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="82159-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="82159-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="82159-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="82159-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="82159-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="82159-106">\<system.serviceModel></span></span>  
<span data-ttu-id="82159-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="82159-107">\<tracking></span></span>  
<span data-ttu-id="82159-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="82159-108">\<trackingProfile></span></span>  
<span data-ttu-id="82159-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="82159-109">\<workflow></span></span>  
<span data-ttu-id="82159-110">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="82159-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82159-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="82159-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82159-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="82159-112">Attributes and Elements</span></span>  
 <span data-ttu-id="82159-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82159-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82159-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="82159-114">Attributes</span></span>  
 <span data-ttu-id="82159-115">Keine</span><span class="sxs-lookup"><span data-stu-id="82159-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82159-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82159-116">Child Elements</span></span>  
  
|<span data-ttu-id="82159-117">Element</span><span class="sxs-lookup"><span data-stu-id="82159-117">Element</span></span>|<span data-ttu-id="82159-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82159-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82159-119">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="82159-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="82159-120">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="82159-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82159-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82159-121">Parent Elements</span></span>  
  
|<span data-ttu-id="82159-122">Element</span><span class="sxs-lookup"><span data-stu-id="82159-122">Element</span></span>|<span data-ttu-id="82159-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82159-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82159-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="82159-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="82159-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="82159-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82159-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82159-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="82159-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="82159-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="82159-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="82159-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
