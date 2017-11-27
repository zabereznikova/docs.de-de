---
title: '&lt;activityStateQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9bcf80d215f9b889c59ab6e68d07ca656ffe93b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivitystatequeriesgt"></a><span data-ttu-id="3020e-102">&lt;activityStateQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="3020e-102">&lt;activityStateQueries&gt;</span></span>
<span data-ttu-id="3020e-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="3020e-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="3020e-104">Beispielsweise empfiehlt es sich zum Nachverfolgen von jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="3020e-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="3020e-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3020e-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="3020e-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="3020e-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="3020e-107">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3020e-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3020e-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3020e-108">\<system.serviceModel></span></span>  
<span data-ttu-id="3020e-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="3020e-109">\<tracking></span></span>  
<span data-ttu-id="3020e-110">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3020e-110">\<trackingProfile></span></span>  
<span data-ttu-id="3020e-111">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="3020e-111">\<workflow></span></span>  
<span data-ttu-id="3020e-112">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="3020e-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3020e-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="3020e-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3020e-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3020e-114">Attributes and Elements</span></span>  
 <span data-ttu-id="3020e-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3020e-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3020e-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="3020e-116">Attributes</span></span>  
 <span data-ttu-id="3020e-117">Keine.</span><span class="sxs-lookup"><span data-stu-id="3020e-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3020e-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3020e-118">Child Elements</span></span>  
  
|<span data-ttu-id="3020e-119">Element</span><span class="sxs-lookup"><span data-stu-id="3020e-119">Element</span></span>|<span data-ttu-id="3020e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3020e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3020e-121">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="3020e-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="3020e-122">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="3020e-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3020e-123">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3020e-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3020e-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3020e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3020e-125">Element</span><span class="sxs-lookup"><span data-stu-id="3020e-125">Element</span></span>|<span data-ttu-id="3020e-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3020e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3020e-127">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="3020e-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3020e-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3020e-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3020e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3020e-129">See Also</span></span>  
 <span data-ttu-id="3020e-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3020e-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3020e-131"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3020e-131"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3020e-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3020e-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3020e-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3020e-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
