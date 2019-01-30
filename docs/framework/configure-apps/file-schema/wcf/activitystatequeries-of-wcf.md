---
title: <activityStateQueries> von WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: c9c78b6929b4550204a22fe2e2786891b516a818
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265323"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="cd448-102">\<ActivityStateQueries > von WCF</span><span class="sxs-lookup"><span data-stu-id="cd448-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="cd448-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="cd448-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="cd448-104">Beispielsweise empfiehlt es sich zum Nachverfolgen jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cd448-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="cd448-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="cd448-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="cd448-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="cd448-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="cd448-107">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cd448-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="cd448-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cd448-108">\<system.serviceModel></span></span>  
<span data-ttu-id="cd448-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="cd448-109">\<tracking></span></span>  
<span data-ttu-id="cd448-110">\<profiles></span><span class="sxs-lookup"><span data-stu-id="cd448-110">\<profiles></span></span>  
<span data-ttu-id="cd448-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cd448-111">\<trackingProfile></span></span>  
<span data-ttu-id="cd448-112">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cd448-112">\<workflow></span></span>  
<span data-ttu-id="cd448-113">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="cd448-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="cd448-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd448-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  

## <a name="attributes-and-elements"></a><span data-ttu-id="cd448-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd448-115">Attributes and elements</span></span>

<span data-ttu-id="cd448-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd448-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="cd448-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd448-117">Attributes</span></span>  

<span data-ttu-id="cd448-118">Keine</span><span class="sxs-lookup"><span data-stu-id="cd448-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="cd448-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd448-119">Child elements</span></span>

|<span data-ttu-id="cd448-120">Element</span><span class="sxs-lookup"><span data-stu-id="cd448-120">Element</span></span>|<span data-ttu-id="cd448-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd448-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cd448-122">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="cd448-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="cd448-123">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="cd448-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="cd448-124">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cd448-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cd448-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd448-125">Parent elements</span></span>

|<span data-ttu-id="cd448-126">Element</span><span class="sxs-lookup"><span data-stu-id="cd448-126">Element</span></span>|<span data-ttu-id="cd448-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd448-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cd448-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cd448-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="cd448-129">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="cd448-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="cd448-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd448-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="cd448-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="cd448-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cd448-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="cd448-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
