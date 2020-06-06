---
title: <activityStateQueries>von WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850568"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="454a3-102">\<activityStateQueries>von WCF</span><span class="sxs-lookup"><span data-stu-id="454a3-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="454a3-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="454a3-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="454a3-104">Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="454a3-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="454a3-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="454a3-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="454a3-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="454a3-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="454a3-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="454a3-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="454a3-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="454a3-108">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="454a3-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="454a3-109">Attributes and elements</span></span>

<span data-ttu-id="454a3-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="454a3-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="454a3-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="454a3-111">Attributes</span></span>  

<span data-ttu-id="454a3-112">Keine</span><span class="sxs-lookup"><span data-stu-id="454a3-112">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="454a3-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="454a3-113">Child elements</span></span>

|<span data-ttu-id="454a3-114">Element</span><span class="sxs-lookup"><span data-stu-id="454a3-114">Element</span></span>|<span data-ttu-id="454a3-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="454a3-115">Description</span></span>|
|-------------|-----------------|
|[\<activityStateQuery>](activitystatequery-of-wcf.md)|<span data-ttu-id="454a3-116">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="454a3-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="454a3-117">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="454a3-117">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="454a3-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="454a3-118">Parent elements</span></span>

|<span data-ttu-id="454a3-119">Element</span><span class="sxs-lookup"><span data-stu-id="454a3-119">Element</span></span>|<span data-ttu-id="454a3-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="454a3-120">Description</span></span>|
|-------------|-----------------|
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="454a3-121">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="454a3-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="454a3-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="454a3-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="454a3-123">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="454a3-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="454a3-124">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="454a3-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
