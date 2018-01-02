---
title: '&lt;faultPropagationQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 244ae0db12964e2baf6de15f545cfa40152ee88e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltfaultpropagationquerygt"></a><span data-ttu-id="6c022-102">&lt;faultPropagationQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="6c022-102">&lt;faultPropagationQuery&gt;</span></span>
<span data-ttu-id="6c022-103">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="6c022-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="6c022-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6c022-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="6c022-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="6c022-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="6c022-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="6c022-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="6c022-107">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6c022-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6c022-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6c022-108">\<system.serviceModel></span></span>  
<span data-ttu-id="6c022-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="6c022-109">\<tracking></span></span>  
<span data-ttu-id="6c022-110">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6c022-110">\<trackingProfile></span></span>  
<span data-ttu-id="6c022-111">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="6c022-111">\<workflow></span></span>  
<span data-ttu-id="6c022-112">\<FaultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="6c022-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="6c022-113">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="6c022-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c022-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c022-114">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c022-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6c022-115">Attributes and Elements</span></span>  
 <span data-ttu-id="6c022-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c022-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c022-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c022-117">Attributes</span></span>  
  
|<span data-ttu-id="6c022-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="6c022-118">Attribute</span></span>|<span data-ttu-id="6c022-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c022-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c022-120">activityName</span><span class="sxs-lookup"><span data-stu-id="6c022-120">activityName</span></span>|<span data-ttu-id="6c022-121">Eine Zeichenfolge, die den Namen der FaultHandler-Aktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="6c022-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="6c022-122">Standardwert ist *, wodurch angegeben wird, dass für alle Aktivitäten Fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6c022-122">The default is *, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="6c022-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="6c022-123">faultHandlerActivityName</span></span>|<span data-ttu-id="6c022-124">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6c022-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c022-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c022-125">Child Elements</span></span>  
 <span data-ttu-id="6c022-126">Keine</span><span class="sxs-lookup"><span data-stu-id="6c022-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c022-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c022-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6c022-128">Element</span><span class="sxs-lookup"><span data-stu-id="6c022-128">Element</span></span>|<span data-ttu-id="6c022-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c022-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c022-130">\<FaultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="6c022-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="6c022-131">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="6c022-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="6c022-132">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6c022-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c022-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c022-133">See Also</span></span>  
 <span data-ttu-id="6c022-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6c022-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="6c022-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6c022-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="6c022-136">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="6c022-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="6c022-137">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="6c022-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
