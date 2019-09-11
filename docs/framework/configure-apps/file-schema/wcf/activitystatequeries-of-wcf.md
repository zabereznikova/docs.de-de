---
title: <activityStateQueries>von WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850568"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="b6a12-102">\<activitystatuequeries-> von WCF</span><span class="sxs-lookup"><span data-stu-id="b6a12-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="b6a12-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="b6a12-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="b6a12-104">Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b6a12-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="b6a12-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="b6a12-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="b6a12-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="b6a12-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="b6a12-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b6a12-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="b6a12-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6a12-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6a12-109">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b6a12-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b6a12-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b6a12-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="b6a12-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="b6a12-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="b6a12-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b6a12-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="b6a12-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b6a12-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="b6a12-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activitystatuequeries->**</span><span class="sxs-lookup"><span data-stu-id="b6a12-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6a12-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6a12-115">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="b6a12-116">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6a12-116">Attributes and elements</span></span>

<span data-ttu-id="b6a12-117">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6a12-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b6a12-118">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6a12-118">Attributes</span></span>  

<span data-ttu-id="b6a12-119">Keine</span><span class="sxs-lookup"><span data-stu-id="b6a12-119">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="b6a12-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6a12-120">Child elements</span></span>

|<span data-ttu-id="b6a12-121">Element</span><span class="sxs-lookup"><span data-stu-id="b6a12-121">Element</span></span>|<span data-ttu-id="b6a12-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6a12-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6a12-123">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b6a12-123">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="b6a12-124">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="b6a12-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b6a12-125">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b6a12-125">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b6a12-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6a12-126">Parent elements</span></span>

|<span data-ttu-id="b6a12-127">Element</span><span class="sxs-lookup"><span data-stu-id="b6a12-127">Element</span></span>|<span data-ttu-id="b6a12-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6a12-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6a12-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b6a12-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="b6a12-130">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="b6a12-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b6a12-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6a12-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="b6a12-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b6a12-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b6a12-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="b6a12-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
