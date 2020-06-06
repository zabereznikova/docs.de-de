---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398953"
---
# \<activityStateQueries>
<span data-ttu-id="d5b09-101">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="d5b09-101">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="d5b09-102">Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d5b09-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="d5b09-103">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="d5b09-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="d5b09-104">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="d5b09-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="d5b09-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d5b09-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="d5b09-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5b09-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5b09-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d5b09-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d5b09-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5b09-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5b09-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d5b09-109">Attributes</span></span>  
 <span data-ttu-id="d5b09-110">Keine</span><span class="sxs-lookup"><span data-stu-id="d5b09-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d5b09-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5b09-111">Child Elements</span></span>  
  
|<span data-ttu-id="d5b09-112">Element</span><span class="sxs-lookup"><span data-stu-id="d5b09-112">Element</span></span>|<span data-ttu-id="d5b09-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5b09-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="d5b09-114">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="d5b09-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d5b09-115">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d5b09-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5b09-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5b09-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d5b09-117">Element</span><span class="sxs-lookup"><span data-stu-id="d5b09-117">Element</span></span>|<span data-ttu-id="d5b09-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5b09-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="d5b09-119">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="d5b09-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5b09-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5b09-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d5b09-121">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d5b09-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d5b09-122">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d5b09-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
