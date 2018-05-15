---
title: '&lt;activityStateQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: b2685da4d5ede9f3d880f6627e86db79b57ee395
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a><span data-ttu-id="fcb1f-102">&lt;activityStateQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="fcb1f-102">&lt;activityStateQueries&gt; of WCF</span></span>
<span data-ttu-id="fcb1f-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="fcb1f-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="fcb1f-104">Beispielsweise empfiehlt es sich zum Nachverfolgen von jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="fcb1f-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="fcb1f-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="fcb1f-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="fcb1f-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="fcb1f-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="fcb1f-107">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fcb1f-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="fcb1f-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fcb1f-108">\<system.serviceModel></span></span>  
<span data-ttu-id="fcb1f-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="fcb1f-109">\<tracking></span></span>  
<span data-ttu-id="fcb1f-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="fcb1f-110">\<trackingProfile></span></span>  
<span data-ttu-id="fcb1f-111">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="fcb1f-111">\<workflow></span></span>  
<span data-ttu-id="fcb1f-112">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="fcb1f-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb1f-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcb1f-113">Syntax</span></span>  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcb1f-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fcb1f-114">Attributes and Elements</span></span>  
 <span data-ttu-id="fcb1f-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fcb1f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcb1f-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="fcb1f-116">Attributes</span></span>  
 <span data-ttu-id="fcb1f-117">Keine</span><span class="sxs-lookup"><span data-stu-id="fcb1f-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fcb1f-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcb1f-118">Child Elements</span></span>  
  
|<span data-ttu-id="fcb1f-119">Element</span><span class="sxs-lookup"><span data-stu-id="fcb1f-119">Element</span></span>|<span data-ttu-id="fcb1f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcb1f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcb1f-121">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="fcb1f-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="fcb1f-122">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="fcb1f-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="fcb1f-123">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="fcb1f-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcb1f-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcb1f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fcb1f-125">Element</span><span class="sxs-lookup"><span data-stu-id="fcb1f-125">Element</span></span>|<span data-ttu-id="fcb1f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcb1f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcb1f-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="fcb1f-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="fcb1f-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="fcb1f-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fcb1f-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcb1f-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>    
 <xref:System.Activities.Tracking.ActivityStateQuery>    
 [<span data-ttu-id="fcb1f-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="fcb1f-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="fcb1f-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="fcb1f-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
