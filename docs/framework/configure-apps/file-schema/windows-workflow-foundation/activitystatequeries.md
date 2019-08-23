---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 6e91078a24a950c6de027d57e3883e38f19447d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945454"
---
# <a name="activitystatequeries"></a><span data-ttu-id="61a48-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="61a48-101">\<activityStateQueries></span></span>
<span data-ttu-id="61a48-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="61a48-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="61a48-103">Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="61a48-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="61a48-104">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="61a48-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="61a48-105">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="61a48-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="61a48-106">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="61a48-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="61a48-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="61a48-107">\<system.serviceModel></span></span>  
<span data-ttu-id="61a48-108">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="61a48-108">\<tracking></span></span>  
<span data-ttu-id="61a48-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="61a48-109">\<trackingProfile></span></span>  
<span data-ttu-id="61a48-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="61a48-110">\<workflow></span></span>  
<span data-ttu-id="61a48-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="61a48-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a48-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="61a48-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61a48-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="61a48-113">Attributes and Elements</span></span>  
 <span data-ttu-id="61a48-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61a48-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61a48-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="61a48-115">Attributes</span></span>  
 <span data-ttu-id="61a48-116">Keine</span><span class="sxs-lookup"><span data-stu-id="61a48-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="61a48-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61a48-117">Child Elements</span></span>  
  
|<span data-ttu-id="61a48-118">Element</span><span class="sxs-lookup"><span data-stu-id="61a48-118">Element</span></span>|<span data-ttu-id="61a48-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61a48-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61a48-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="61a48-120">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="61a48-121">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="61a48-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="61a48-122">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="61a48-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61a48-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61a48-123">Parent Elements</span></span>  
  
|<span data-ttu-id="61a48-124">Element</span><span class="sxs-lookup"><span data-stu-id="61a48-124">Element</span></span>|<span data-ttu-id="61a48-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61a48-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61a48-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="61a48-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="61a48-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="61a48-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61a48-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61a48-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="61a48-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="61a48-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="61a48-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="61a48-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
