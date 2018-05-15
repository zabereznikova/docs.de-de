---
title: '&lt;faultPropagationQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 5fd6ffc9560247089c7fbb60b0e5a7d3a417ea6f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltfaultpropagationqueriesgt"></a><span data-ttu-id="00d93-102">&lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="00d93-102">&lt;faultPropagationQueries&gt;</span></span>
<span data-ttu-id="00d93-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="00d93-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="00d93-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="00d93-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="00d93-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="00d93-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="00d93-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="00d93-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="00d93-107">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="00d93-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="00d93-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="00d93-108">\<system.serviceModel></span></span>  
<span data-ttu-id="00d93-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="00d93-109">\<tracking></span></span>  
<span data-ttu-id="00d93-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="00d93-110">\<trackingProfile></span></span>  
<span data-ttu-id="00d93-111">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="00d93-111">\<workflow></span></span>  
<span data-ttu-id="00d93-112">\<FaultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="00d93-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00d93-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="00d93-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00d93-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00d93-114">Attributes and Elements</span></span>  
 <span data-ttu-id="00d93-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00d93-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00d93-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="00d93-116">Attributes</span></span>  
 <span data-ttu-id="00d93-117">Keine</span><span class="sxs-lookup"><span data-stu-id="00d93-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="00d93-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00d93-118">Child Elements</span></span>  
  
|<span data-ttu-id="00d93-119">Element</span><span class="sxs-lookup"><span data-stu-id="00d93-119">Element</span></span>|<span data-ttu-id="00d93-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00d93-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00d93-121">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="00d93-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="00d93-122">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="00d93-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="00d93-123">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="00d93-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00d93-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00d93-124">Parent Elements</span></span>  
  
|<span data-ttu-id="00d93-125">Element</span><span class="sxs-lookup"><span data-stu-id="00d93-125">Element</span></span>|<span data-ttu-id="00d93-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00d93-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00d93-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="00d93-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="00d93-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="00d93-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00d93-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00d93-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="00d93-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="00d93-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="00d93-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="00d93-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
