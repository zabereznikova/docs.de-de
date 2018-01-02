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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c9ad0f766256d6507775c2cca1b9d54b474abc7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="ba5fd-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ba5fd-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="ba5fd-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="ba5fd-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ba5fd-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ba5fd-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="ba5fd-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ba5fd-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ba5fd-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ba5fd-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ba5fd-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="ba5fd-107">\<tracking></span></span>  
<span data-ttu-id="ba5fd-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ba5fd-108">\<trackingProfile></span></span>  
<span data-ttu-id="ba5fd-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="ba5fd-109">\<workflow></span></span>  
<span data-ttu-id="ba5fd-110">\<CancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="ba5fd-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="ba5fd-111">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="ba5fd-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba5fd-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba5fd-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba5fd-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba5fd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ba5fd-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba5fd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba5fd-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba5fd-115">Attributes</span></span>  
  
|<span data-ttu-id="ba5fd-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="ba5fd-116">Attribute</span></span>|<span data-ttu-id="ba5fd-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba5fd-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba5fd-118">activityName</span><span class="sxs-lookup"><span data-stu-id="ba5fd-118">activityName</span></span>|<span data-ttu-id="ba5fd-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="ba5fd-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="ba5fd-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="ba5fd-120">childActivityName</span></span>|<span data-ttu-id="ba5fd-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="ba5fd-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba5fd-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba5fd-122">Child Elements</span></span>  
 <span data-ttu-id="ba5fd-123">Keine</span><span class="sxs-lookup"><span data-stu-id="ba5fd-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba5fd-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba5fd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ba5fd-125">Element</span><span class="sxs-lookup"><span data-stu-id="ba5fd-125">Element</span></span>|<span data-ttu-id="ba5fd-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba5fd-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba5fd-127">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="ba5fd-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="ba5fd-128">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="ba5fd-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ba5fd-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ba5fd-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba5fd-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba5fd-130">See Also</span></span>  
 <span data-ttu-id="ba5fd-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ba5fd-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="ba5fd-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ba5fd-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="ba5fd-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ba5fd-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ba5fd-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ba5fd-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
