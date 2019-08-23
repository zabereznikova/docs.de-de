---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: f77a613f4eb0456a0085096aa478d37c78122217
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946314"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="28472-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="28472-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="28472-102">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="28472-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="28472-103">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="28472-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="28472-104">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="28472-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="28472-105">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="28472-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="28472-106">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="28472-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="28472-107">\<System. Service Model > </span><span class="sxs-lookup"><span data-stu-id="28472-107">\<system.serviceModel></span></span>\
<span data-ttu-id="28472-108">\<Nachverfolgung > </span><span class="sxs-lookup"><span data-stu-id="28472-108">\<tracking></span></span>\
<span data-ttu-id="28472-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="28472-109">\<trackingProfile></span></span>\
<span data-ttu-id="28472-110">\<Workflow > </span><span class="sxs-lookup"><span data-stu-id="28472-110">\<workflow></span></span>\
<span data-ttu-id="28472-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="28472-111">\<faultPropagationQueries></span></span>\
<span data-ttu-id="28472-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="28472-112">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="28472-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="28472-113">Syntax</span></span>

```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28472-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="28472-114">Attributes and Elements</span></span>

<span data-ttu-id="28472-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28472-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="28472-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="28472-116">Attributes</span></span>

|<span data-ttu-id="28472-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="28472-117">Attribute</span></span>|<span data-ttu-id="28472-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28472-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="28472-119">activityName</span><span class="sxs-lookup"><span data-stu-id="28472-119">activityName</span></span>|<span data-ttu-id="28472-120">Eine Zeichenfolge, die den Namen der fehlerhandleraktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="28472-120">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="28472-121">Standardwert ist \*, wodurch angegeben wird, dass für alle Aktivitäten Fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="28472-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="28472-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="28472-122">faultHandlerActivityName</span></span>|<span data-ttu-id="28472-123">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="28472-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="28472-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28472-124">Child Elements</span></span>

<span data-ttu-id="28472-125">Keine</span><span class="sxs-lookup"><span data-stu-id="28472-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="28472-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28472-126">Parent Elements</span></span>

|<span data-ttu-id="28472-127">Element</span><span class="sxs-lookup"><span data-stu-id="28472-127">Element</span></span>|<span data-ttu-id="28472-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28472-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28472-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="28472-129">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="28472-130">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="28472-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="28472-131">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="28472-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="28472-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28472-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="28472-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="28472-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="28472-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="28472-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
