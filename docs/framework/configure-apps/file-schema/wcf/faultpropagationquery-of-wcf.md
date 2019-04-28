---
title: <faultPropagationQuery> von WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: e5793852d49a052d05f6cb2f4efbe166d67afc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701046"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="2170a-102">\<faultPropagationQuery> of WCF</span><span class="sxs-lookup"><span data-stu-id="2170a-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="2170a-103">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="2170a-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2170a-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="2170a-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="2170a-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="2170a-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="2170a-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="2170a-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="2170a-107">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2170a-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="2170a-108">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="2170a-108">\<system.serviceModel>\\</span></span>
<span data-ttu-id="2170a-109">\<tracking>\\</span><span class="sxs-lookup"><span data-stu-id="2170a-109">\<tracking>\\</span></span>
<span data-ttu-id="2170a-110">\<Profile > \\</span><span class="sxs-lookup"><span data-stu-id="2170a-110">\<profiles>\\</span></span>
<span data-ttu-id="2170a-111">\<trackingProfile>\\</span><span class="sxs-lookup"><span data-stu-id="2170a-111">\<trackingProfile>\\</span></span>
<span data-ttu-id="2170a-112">\<workflow>\\</span><span class="sxs-lookup"><span data-stu-id="2170a-112">\<workflow>\\</span></span>
<span data-ttu-id="2170a-113">\<faultPropagationQueries>\\</span><span class="sxs-lookup"><span data-stu-id="2170a-113">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="2170a-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="2170a-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="2170a-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="2170a-115">Syntax</span></span>

```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2170a-116">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2170a-116">Attributes and elements</span></span>

<span data-ttu-id="2170a-117">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2170a-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2170a-118">Attribute</span><span class="sxs-lookup"><span data-stu-id="2170a-118">Attributes</span></span>

|<span data-ttu-id="2170a-119">Attribut</span><span class="sxs-lookup"><span data-stu-id="2170a-119">Attribute</span></span>|<span data-ttu-id="2170a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2170a-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="2170a-121">Eine Zeichenfolge, die den Namen der fehlerhandleraktivität gibt an, die den Fehler weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="2170a-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="2170a-122">Der Standardwert ist \*, was bedeutet, dass für alle Aktivitäten fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2170a-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="2170a-123">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2170a-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2170a-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2170a-124">Child elements</span></span>

<span data-ttu-id="2170a-125">Keine</span><span class="sxs-lookup"><span data-stu-id="2170a-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2170a-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2170a-126">Parent elements</span></span>

|<span data-ttu-id="2170a-127">Element</span><span class="sxs-lookup"><span data-stu-id="2170a-127">Element</span></span>|<span data-ttu-id="2170a-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2170a-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2170a-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="2170a-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="2170a-130">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="2170a-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2170a-131">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="2170a-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="2170a-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2170a-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2170a-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="2170a-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2170a-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="2170a-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
