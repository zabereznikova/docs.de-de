---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398719"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="ae97c-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="ae97c-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="ae97c-102">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="ae97c-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ae97c-103">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="ae97c-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="ae97c-104">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="ae97c-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="ae97c-105">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ae97c-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="ae97c-106">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ae97c-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="ae97c-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ae97c-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ae97c-108">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ae97c-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="ae97c-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="ae97c-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="ae97c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="ae97c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="ae97c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ae97c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="ae97c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<"fehlerpropagationqueries"->** ](faultpropagationqueries.md)</span><span class="sxs-lookup"><span data-stu-id="ae97c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)</span></span>\
<span data-ttu-id="ae97c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> "fehlerpropagationquery"**</span><span class="sxs-lookup"><span data-stu-id="ae97c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ae97c-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae97c-114">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="ae97c-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ae97c-115">Attributes and Elements</span></span>

<span data-ttu-id="ae97c-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ae97c-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ae97c-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="ae97c-117">Attributes</span></span>

|<span data-ttu-id="ae97c-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="ae97c-118">Attribute</span></span>|<span data-ttu-id="ae97c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae97c-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="ae97c-120">activityName</span><span class="sxs-lookup"><span data-stu-id="ae97c-120">activityName</span></span>|<span data-ttu-id="ae97c-121">Eine Zeichenfolge, die den Namen der fehlerhandleraktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="ae97c-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="ae97c-122">Standardwert ist \*, wodurch angegeben wird, dass für alle Aktivitäten Fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ae97c-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="ae97c-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="ae97c-123">faultHandlerActivityName</span></span>|<span data-ttu-id="ae97c-124">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ae97c-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ae97c-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae97c-125">Child Elements</span></span>

<span data-ttu-id="ae97c-126">Keine</span><span class="sxs-lookup"><span data-stu-id="ae97c-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ae97c-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae97c-127">Parent Elements</span></span>

|<span data-ttu-id="ae97c-128">Element</span><span class="sxs-lookup"><span data-stu-id="ae97c-128">Element</span></span>|<span data-ttu-id="ae97c-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae97c-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ae97c-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="ae97c-130">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="ae97c-131">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="ae97c-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ae97c-132">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="ae97c-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ae97c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae97c-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ae97c-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ae97c-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ae97c-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ae97c-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
