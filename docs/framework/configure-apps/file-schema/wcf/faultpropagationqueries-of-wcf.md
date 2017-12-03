---
title: '&lt;faultPropagationQueries&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 771908114f4f4e1cc2588e39e7f3d811c336a05a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="f4a07-102">&lt;faultPropagationQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="f4a07-102">&lt;faultPropagationQueries&gt; of WCF</span></span>
<span data-ttu-id="f4a07-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="f4a07-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f4a07-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f4a07-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f4a07-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="f4a07-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f4a07-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="f4a07-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="f4a07-107">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f4a07-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="f4a07-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f4a07-108">\<system.serviceModel></span></span>  
<span data-ttu-id="f4a07-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="f4a07-109">\<tracking></span></span>  
<span data-ttu-id="f4a07-110">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f4a07-110">\<trackingProfile></span></span>  
<span data-ttu-id="f4a07-111">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="f4a07-111">\<workflow></span></span>  
<span data-ttu-id="f4a07-112">\<FaultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="f4a07-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a07-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4a07-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4a07-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f4a07-114">Attributes and Elements</span></span>  
 <span data-ttu-id="f4a07-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f4a07-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4a07-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="f4a07-116">Attributes</span></span>  
 <span data-ttu-id="f4a07-117">Keine.</span><span class="sxs-lookup"><span data-stu-id="f4a07-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f4a07-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4a07-118">Child Elements</span></span>  
  
|<span data-ttu-id="f4a07-119">Element</span><span class="sxs-lookup"><span data-stu-id="f4a07-119">Element</span></span>|<span data-ttu-id="f4a07-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4a07-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4a07-121">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="f4a07-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="f4a07-122">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="f4a07-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f4a07-123">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f4a07-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f4a07-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4a07-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f4a07-125">Element</span><span class="sxs-lookup"><span data-stu-id="f4a07-125">Element</span></span>|<span data-ttu-id="f4a07-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4a07-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4a07-127">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="f4a07-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f4a07-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="f4a07-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4a07-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4a07-129">See Also</span></span>  
 <span data-ttu-id="f4a07-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f4a07-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f4a07-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f4a07-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="f4a07-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="f4a07-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f4a07-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="f4a07-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
