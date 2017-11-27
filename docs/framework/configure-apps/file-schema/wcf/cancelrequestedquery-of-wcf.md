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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab16fe138701d180f528b5ec07e106acd53023b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="62b4a-102">&lt;cancelRequestedQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="62b4a-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="62b4a-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="62b4a-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="62b4a-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="62b4a-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="62b4a-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="62b4a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="62b4a-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="62b4a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="62b4a-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="62b4a-107">\<tracking></span></span>  
<span data-ttu-id="62b4a-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="62b4a-108">\<trackingProfile></span></span>  
<span data-ttu-id="62b4a-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="62b4a-109">\<workflow></span></span>  
<span data-ttu-id="62b4a-110">\<CancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="62b4a-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="62b4a-111">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="62b4a-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62b4a-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="62b4a-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="62b4a-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62b4a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="62b4a-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62b4a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62b4a-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="62b4a-115">Attributes</span></span>  
  
|<span data-ttu-id="62b4a-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="62b4a-116">Attribute</span></span>|<span data-ttu-id="62b4a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62b4a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62b4a-118">activityName</span><span class="sxs-lookup"><span data-stu-id="62b4a-118">activityName</span></span>|<span data-ttu-id="62b4a-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="62b4a-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="62b4a-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="62b4a-120">childActivityName</span></span>|<span data-ttu-id="62b4a-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="62b4a-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62b4a-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62b4a-122">Child Elements</span></span>  
 <span data-ttu-id="62b4a-123">Keine</span><span class="sxs-lookup"><span data-stu-id="62b4a-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62b4a-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62b4a-124">Parent Elements</span></span>  
  
|<span data-ttu-id="62b4a-125">Element</span><span class="sxs-lookup"><span data-stu-id="62b4a-125">Element</span></span>|<span data-ttu-id="62b4a-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62b4a-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62b4a-127">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="62b4a-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="62b4a-128">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="62b4a-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="62b4a-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="62b4a-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62b4a-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62b4a-130">See Also</span></span>  
 <span data-ttu-id="62b4a-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="62b4a-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="62b4a-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="62b4a-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>     
 [<span data-ttu-id="62b4a-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="62b4a-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="62b4a-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="62b4a-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
