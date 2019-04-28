---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 90acda7277fd276f43a619a014fbce103261aa1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790402"
---
# <a name="activitystatequeries"></a><span data-ttu-id="611ea-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="611ea-101">\<activityStateQueries></span></span>
<span data-ttu-id="611ea-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="611ea-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="611ea-103">Beispielsweise empfiehlt es sich zum Nachverfolgen jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="611ea-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="611ea-104">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="611ea-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="611ea-105">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="611ea-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="611ea-106">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="611ea-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="611ea-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="611ea-107">\<system.serviceModel></span></span>  
<span data-ttu-id="611ea-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="611ea-108">\<tracking></span></span>  
<span data-ttu-id="611ea-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="611ea-109">\<trackingProfile></span></span>  
<span data-ttu-id="611ea-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="611ea-110">\<workflow></span></span>  
<span data-ttu-id="611ea-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="611ea-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="611ea-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="611ea-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="611ea-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="611ea-113">Attributes and Elements</span></span>  
 <span data-ttu-id="611ea-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="611ea-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="611ea-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="611ea-115">Attributes</span></span>  
 <span data-ttu-id="611ea-116">Keine</span><span class="sxs-lookup"><span data-stu-id="611ea-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="611ea-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="611ea-117">Child Elements</span></span>  
  
|<span data-ttu-id="611ea-118">Element</span><span class="sxs-lookup"><span data-stu-id="611ea-118">Element</span></span>|<span data-ttu-id="611ea-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="611ea-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="611ea-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="611ea-120">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="611ea-121">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="611ea-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="611ea-122">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="611ea-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="611ea-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="611ea-123">Parent Elements</span></span>  
  
|<span data-ttu-id="611ea-124">Element</span><span class="sxs-lookup"><span data-stu-id="611ea-124">Element</span></span>|<span data-ttu-id="611ea-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="611ea-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="611ea-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="611ea-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="611ea-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="611ea-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="611ea-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="611ea-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="611ea-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="611ea-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="611ea-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="611ea-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
