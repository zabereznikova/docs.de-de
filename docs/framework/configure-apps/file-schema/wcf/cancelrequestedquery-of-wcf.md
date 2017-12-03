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
ms.openlocfilehash: 6fc9df52c691e13802607714977f3aa778cde84e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="373af-102">&lt;cancelRequestedQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="373af-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="373af-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="373af-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="373af-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="373af-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="373af-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="373af-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="373af-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="373af-106">\<system.serviceModel></span></span>  
<span data-ttu-id="373af-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="373af-107">\<tracking></span></span>  
<span data-ttu-id="373af-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="373af-108">\<trackingProfile></span></span>  
<span data-ttu-id="373af-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="373af-109">\<workflow></span></span>  
<span data-ttu-id="373af-110">\<CancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="373af-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="373af-111">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="373af-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="373af-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="373af-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="373af-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="373af-113">Attributes and Elements</span></span>  
 <span data-ttu-id="373af-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="373af-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="373af-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="373af-115">Attributes</span></span>  
  
|<span data-ttu-id="373af-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="373af-116">Attribute</span></span>|<span data-ttu-id="373af-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="373af-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="373af-118">activityName</span><span class="sxs-lookup"><span data-stu-id="373af-118">activityName</span></span>|<span data-ttu-id="373af-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="373af-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="373af-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="373af-120">childActivityName</span></span>|<span data-ttu-id="373af-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="373af-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="373af-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="373af-122">Child Elements</span></span>  
 <span data-ttu-id="373af-123">Keine</span><span class="sxs-lookup"><span data-stu-id="373af-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="373af-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="373af-124">Parent Elements</span></span>  
  
|<span data-ttu-id="373af-125">Element</span><span class="sxs-lookup"><span data-stu-id="373af-125">Element</span></span>|<span data-ttu-id="373af-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="373af-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="373af-127">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="373af-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="373af-128">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="373af-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="373af-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="373af-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="373af-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="373af-130">See Also</span></span>  
 <span data-ttu-id="373af-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="373af-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="373af-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="373af-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>     
 [<span data-ttu-id="373af-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="373af-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="373af-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="373af-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
