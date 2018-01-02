---
title: '&lt;cancelRequestedQuery&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2af49aab76e82a97aeee92b4799b91011f70c509
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="90ba6-102">&lt;cancelRequestedQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="90ba6-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="90ba6-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="90ba6-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="90ba6-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="90ba6-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="90ba6-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="90ba6-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="90ba6-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="90ba6-106">\<system.serviceModel></span></span>  
<span data-ttu-id="90ba6-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="90ba6-107">\<tracking></span></span>  
<span data-ttu-id="90ba6-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="90ba6-108">\<trackingProfile></span></span>  
<span data-ttu-id="90ba6-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="90ba6-109">\<workflow></span></span>  
<span data-ttu-id="90ba6-110">\<CancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="90ba6-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="90ba6-111">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="90ba6-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90ba6-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="90ba6-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90ba6-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90ba6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="90ba6-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90ba6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90ba6-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="90ba6-115">Attributes</span></span>  
  
|<span data-ttu-id="90ba6-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="90ba6-116">Attribute</span></span>|<span data-ttu-id="90ba6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90ba6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90ba6-118">activityName</span><span class="sxs-lookup"><span data-stu-id="90ba6-118">activityName</span></span>|<span data-ttu-id="90ba6-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="90ba6-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="90ba6-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="90ba6-120">childActivityName</span></span>|<span data-ttu-id="90ba6-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="90ba6-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90ba6-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90ba6-122">Child Elements</span></span>  
 <span data-ttu-id="90ba6-123">Keine</span><span class="sxs-lookup"><span data-stu-id="90ba6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90ba6-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90ba6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="90ba6-125">Element</span><span class="sxs-lookup"><span data-stu-id="90ba6-125">Element</span></span>|<span data-ttu-id="90ba6-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90ba6-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90ba6-127">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="90ba6-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="90ba6-128">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="90ba6-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="90ba6-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="90ba6-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90ba6-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90ba6-130">See Also</span></span>  
 <span data-ttu-id="90ba6-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="90ba6-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="90ba6-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="90ba6-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>     
 [<span data-ttu-id="90ba6-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="90ba6-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="90ba6-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="90ba6-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
