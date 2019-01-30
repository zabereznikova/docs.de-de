---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 0424c01397a95803b9e8502d90a55d1bd4c3b5e6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269392"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="d0df3-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="d0df3-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="d0df3-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="d0df3-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d0df3-103">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d0df3-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="d0df3-104">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="d0df3-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="d0df3-105">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="d0df3-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="d0df3-106">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d0df3-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="d0df3-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d0df3-107">\<system.serviceModel></span></span>  
<span data-ttu-id="d0df3-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d0df3-108">\<tracking></span></span>  
<span data-ttu-id="d0df3-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d0df3-109">\<trackingProfile></span></span>  
<span data-ttu-id="d0df3-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d0df3-110">\<workflow></span></span>  
<span data-ttu-id="d0df3-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="d0df3-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0df3-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0df3-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0df3-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d0df3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d0df3-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d0df3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0df3-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="d0df3-115">Attributes</span></span>  
 <span data-ttu-id="d0df3-116">Keine</span><span class="sxs-lookup"><span data-stu-id="d0df3-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0df3-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d0df3-117">Child Elements</span></span>  
  
|<span data-ttu-id="d0df3-118">Element</span><span class="sxs-lookup"><span data-stu-id="d0df3-118">Element</span></span>|<span data-ttu-id="d0df3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0df3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0df3-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="d0df3-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="d0df3-121">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="d0df3-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d0df3-122">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d0df3-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0df3-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d0df3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d0df3-124">Element</span><span class="sxs-lookup"><span data-stu-id="d0df3-124">Element</span></span>|<span data-ttu-id="d0df3-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0df3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0df3-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d0df3-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d0df3-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d0df3-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0df3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0df3-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d0df3-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d0df3-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d0df3-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d0df3-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
