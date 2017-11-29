---
title: '&lt;cancelRequestedQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e1697b245f9ab61cab3e4b26b1756259f0eba9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="9a7f4-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="9a7f4-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="9a7f4-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9a7f4-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="9a7f4-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9a7f4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9a7f4-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9a7f4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9a7f4-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="9a7f4-107">\<tracking></span></span>  
<span data-ttu-id="9a7f4-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9a7f4-108">\<trackingProfile></span></span>  
<span data-ttu-id="9a7f4-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="9a7f4-109">\<workflow></span></span>  
<span data-ttu-id="9a7f4-110">\<CancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="9a7f4-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="9a7f4-111">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="9a7f4-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a7f4-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a7f4-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a7f4-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9a7f4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9a7f4-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a7f4-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="9a7f4-115">Attributes</span></span>  
  
|<span data-ttu-id="9a7f4-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="9a7f4-116">Attribute</span></span>|<span data-ttu-id="9a7f4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a7f4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a7f4-118">activityName</span><span class="sxs-lookup"><span data-stu-id="9a7f4-118">activityName</span></span>|<span data-ttu-id="9a7f4-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="9a7f4-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="9a7f4-120">childActivityName</span></span>|<span data-ttu-id="9a7f4-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a7f4-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a7f4-122">Child Elements</span></span>  
 <span data-ttu-id="9a7f4-123">Keine</span><span class="sxs-lookup"><span data-stu-id="9a7f4-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a7f4-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a7f4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9a7f4-125">Element</span><span class="sxs-lookup"><span data-stu-id="9a7f4-125">Element</span></span>|<span data-ttu-id="9a7f4-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a7f4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a7f4-127">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="9a7f4-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="9a7f4-128">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9a7f4-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a7f4-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a7f4-130">See Also</span></span>  
 <span data-ttu-id="9a7f4-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9a7f4-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="9a7f4-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9a7f4-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="9a7f4-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="9a7f4-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9a7f4-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="9a7f4-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
