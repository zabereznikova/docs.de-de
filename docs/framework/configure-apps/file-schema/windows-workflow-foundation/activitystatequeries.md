---
title: '&lt;activityStateQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: bfd19e00e79a95eb717ca9131e92b5ff5c600d5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511981"
---
# <a name="ltactivitystatequeriesgt"></a><span data-ttu-id="3c125-102">&lt;activityStateQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="3c125-102">&lt;activityStateQueries&gt;</span></span>
<span data-ttu-id="3c125-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="3c125-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="3c125-104">Beispielsweise empfiehlt es sich zum Nachverfolgen jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="3c125-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="3c125-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3c125-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="3c125-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="3c125-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="3c125-107">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3c125-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3c125-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3c125-108">\<system.serviceModel></span></span>  
<span data-ttu-id="3c125-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3c125-109">\<tracking></span></span>  
<span data-ttu-id="3c125-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3c125-110">\<trackingProfile></span></span>  
<span data-ttu-id="3c125-111">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3c125-111">\<workflow></span></span>  
<span data-ttu-id="3c125-112">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="3c125-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c125-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c125-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c125-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3c125-114">Attributes and Elements</span></span>  
 <span data-ttu-id="3c125-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3c125-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c125-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="3c125-116">Attributes</span></span>  
 <span data-ttu-id="3c125-117">Keine</span><span class="sxs-lookup"><span data-stu-id="3c125-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c125-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c125-118">Child Elements</span></span>  
  
|<span data-ttu-id="3c125-119">Element</span><span class="sxs-lookup"><span data-stu-id="3c125-119">Element</span></span>|<span data-ttu-id="3c125-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c125-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c125-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="3c125-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="3c125-122">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="3c125-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3c125-123">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3c125-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c125-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c125-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3c125-125">Element</span><span class="sxs-lookup"><span data-stu-id="3c125-125">Element</span></span>|<span data-ttu-id="3c125-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c125-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c125-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3c125-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3c125-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3c125-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c125-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c125-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3c125-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3c125-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3c125-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3c125-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
