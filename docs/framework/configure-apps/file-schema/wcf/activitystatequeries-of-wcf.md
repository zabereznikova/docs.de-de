---
title: <activityStateQueries>von WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 415cd4a75ecab725f91bcd298f8a7966ea6079d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920300"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="cf745-102">\<activitystatuequeries-> von WCF</span><span class="sxs-lookup"><span data-stu-id="cf745-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="cf745-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="cf745-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="cf745-104">Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cf745-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="cf745-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="cf745-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="cf745-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="cf745-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="cf745-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cf745-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="cf745-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cf745-108">\<system.serviceModel></span></span>  
<span data-ttu-id="cf745-109">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="cf745-109">\<tracking></span></span>  
<span data-ttu-id="cf745-110">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="cf745-110">\<profiles></span></span>  
<span data-ttu-id="cf745-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cf745-111">\<trackingProfile></span></span>  
<span data-ttu-id="cf745-112">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cf745-112">\<workflow></span></span>  
<span data-ttu-id="cf745-113">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="cf745-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="cf745-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf745-114">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="cf745-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cf745-115">Attributes and elements</span></span>

<span data-ttu-id="cf745-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf745-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="cf745-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="cf745-117">Attributes</span></span>  

<span data-ttu-id="cf745-118">Keine</span><span class="sxs-lookup"><span data-stu-id="cf745-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="cf745-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf745-119">Child elements</span></span>

|<span data-ttu-id="cf745-120">Element</span><span class="sxs-lookup"><span data-stu-id="cf745-120">Element</span></span>|<span data-ttu-id="cf745-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf745-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cf745-122">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="cf745-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="cf745-123">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="cf745-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="cf745-124">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cf745-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cf745-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf745-125">Parent elements</span></span>

|<span data-ttu-id="cf745-126">Element</span><span class="sxs-lookup"><span data-stu-id="cf745-126">Element</span></span>|<span data-ttu-id="cf745-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf745-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cf745-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cf745-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="cf745-129">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="cf745-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="cf745-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf745-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="cf745-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="cf745-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cf745-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="cf745-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
