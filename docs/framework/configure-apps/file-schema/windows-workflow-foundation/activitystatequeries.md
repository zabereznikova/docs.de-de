---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398953"
---
# <a name="activitystatequeries"></a><span data-ttu-id="de5a8-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="de5a8-101">\<activityStateQueries></span></span>
<span data-ttu-id="de5a8-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="de5a8-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="de5a8-103">Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="de5a8-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="de5a8-104">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="de5a8-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="de5a8-105">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="de5a8-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="de5a8-106">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="de5a8-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="de5a8-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="de5a8-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="de5a8-108">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="de5a8-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="de5a8-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="de5a8-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="de5a8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="de5a8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="de5a8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="de5a8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="de5a8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activitystatuequeries->**</span><span class="sxs-lookup"><span data-stu-id="de5a8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de5a8-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="de5a8-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de5a8-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="de5a8-114">Attributes and Elements</span></span>  
 <span data-ttu-id="de5a8-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="de5a8-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de5a8-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="de5a8-116">Attributes</span></span>  
 <span data-ttu-id="de5a8-117">Keine</span><span class="sxs-lookup"><span data-stu-id="de5a8-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="de5a8-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="de5a8-118">Child Elements</span></span>  
  
|<span data-ttu-id="de5a8-119">Element</span><span class="sxs-lookup"><span data-stu-id="de5a8-119">Element</span></span>|<span data-ttu-id="de5a8-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de5a8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de5a8-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="de5a8-121">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="de5a8-122">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="de5a8-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="de5a8-123">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="de5a8-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de5a8-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="de5a8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="de5a8-125">Element</span><span class="sxs-lookup"><span data-stu-id="de5a8-125">Element</span></span>|<span data-ttu-id="de5a8-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de5a8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de5a8-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="de5a8-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="de5a8-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="de5a8-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de5a8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de5a8-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="de5a8-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="de5a8-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="de5a8-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="de5a8-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
