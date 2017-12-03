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
ms.openlocfilehash: 457cc3aaa921016e553eb40bcee72af5de3c7179
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="d635f-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="d635f-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="d635f-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="d635f-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d635f-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="d635f-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="d635f-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d635f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d635f-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d635f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d635f-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="d635f-107">\<tracking></span></span>  
<span data-ttu-id="d635f-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d635f-108">\<trackingProfile></span></span>  
<span data-ttu-id="d635f-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="d635f-109">\<workflow></span></span>  
<span data-ttu-id="d635f-110">\<CancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="d635f-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d635f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="d635f-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d635f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d635f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d635f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d635f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d635f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="d635f-114">Attributes</span></span>  
 <span data-ttu-id="d635f-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="d635f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d635f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d635f-116">Child Elements</span></span>  
  
|<span data-ttu-id="d635f-117">Element</span><span class="sxs-lookup"><span data-stu-id="d635f-117">Element</span></span>|<span data-ttu-id="d635f-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d635f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d635f-119">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="d635f-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="d635f-120">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="d635f-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d635f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d635f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d635f-122">Element</span><span class="sxs-lookup"><span data-stu-id="d635f-122">Element</span></span>|<span data-ttu-id="d635f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d635f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d635f-124">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="d635f-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d635f-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d635f-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d635f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d635f-126">See Also</span></span>  
 [<span data-ttu-id="d635f-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d635f-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d635f-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d635f-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
