---
title: '&lt;cancelRequestedQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 774012a0a64342bbd21832213a6c41fe41fdaef5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="a914a-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="a914a-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="a914a-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="a914a-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a914a-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a914a-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="a914a-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a914a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a914a-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a914a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a914a-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="a914a-107">\<tracking></span></span>  
<span data-ttu-id="a914a-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a914a-108">\<trackingProfile></span></span>  
<span data-ttu-id="a914a-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a914a-109">\<workflow></span></span>  
<span data-ttu-id="a914a-110">\<CancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="a914a-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a914a-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a914a-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a914a-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a914a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a914a-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a914a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a914a-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a914a-114">Attributes</span></span>  
 <span data-ttu-id="a914a-115">Keine</span><span class="sxs-lookup"><span data-stu-id="a914a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a914a-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a914a-116">Child Elements</span></span>  
  
|<span data-ttu-id="a914a-117">Element</span><span class="sxs-lookup"><span data-stu-id="a914a-117">Element</span></span>|<span data-ttu-id="a914a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a914a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a914a-119">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="a914a-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="a914a-120">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a914a-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a914a-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a914a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a914a-122">Element</span><span class="sxs-lookup"><span data-stu-id="a914a-122">Element</span></span>|<span data-ttu-id="a914a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a914a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a914a-124">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a914a-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="a914a-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a914a-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a914a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a914a-126">See Also</span></span>  
 [<span data-ttu-id="a914a-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a914a-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a914a-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a914a-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
