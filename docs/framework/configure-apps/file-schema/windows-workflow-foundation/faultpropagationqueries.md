---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 402b938913575adfa9125b981dc2913680f07b73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204041"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="6c4c6-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="6c4c6-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="6c4c6-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="6c4c6-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="6c4c6-103">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6c4c6-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="6c4c6-104">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="6c4c6-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="6c4c6-105">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="6c4c6-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="6c4c6-106">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6c4c6-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6c4c6-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6c4c6-107">\<system.serviceModel></span></span>  
<span data-ttu-id="6c4c6-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6c4c6-108">\<tracking></span></span>  
<span data-ttu-id="6c4c6-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6c4c6-109">\<trackingProfile></span></span>  
<span data-ttu-id="6c4c6-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6c4c6-110">\<workflow></span></span>  
<span data-ttu-id="6c4c6-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="6c4c6-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c4c6-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c4c6-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c4c6-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6c4c6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6c4c6-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c4c6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c4c6-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c4c6-115">Attributes</span></span>  
 <span data-ttu-id="6c4c6-116">Keine</span><span class="sxs-lookup"><span data-stu-id="6c4c6-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c4c6-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c4c6-117">Child Elements</span></span>  
  
|<span data-ttu-id="6c4c6-118">Element</span><span class="sxs-lookup"><span data-stu-id="6c4c6-118">Element</span></span>|<span data-ttu-id="6c4c6-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c4c6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c4c6-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="6c4c6-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="6c4c6-121">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="6c4c6-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="6c4c6-122">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6c4c6-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c4c6-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c4c6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6c4c6-124">Element</span><span class="sxs-lookup"><span data-stu-id="6c4c6-124">Element</span></span>|<span data-ttu-id="6c4c6-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c4c6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c4c6-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6c4c6-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6c4c6-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6c4c6-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c4c6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c4c6-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6c4c6-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="6c4c6-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6c4c6-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="6c4c6-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
