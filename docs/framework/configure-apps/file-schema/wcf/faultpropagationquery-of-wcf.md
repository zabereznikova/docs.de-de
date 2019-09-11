---
title: <faultPropagationQuery>von WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855333"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="aa9d6-102">\<"fehlerpropagationquery"-> von WCF</span><span class="sxs-lookup"><span data-stu-id="aa9d6-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="aa9d6-103">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="aa9d6-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="aa9d6-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="aa9d6-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="aa9d6-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="aa9d6-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="aa9d6-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa9d6-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aa9d6-109">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aa9d6-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aa9d6-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa9d6-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="aa9d6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="aa9d6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="aa9d6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa9d6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="aa9d6-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa9d6-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="aa9d6-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<"fehlerpropagationqueries"->** ](faultpropagationqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa9d6-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)</span></span>\
<span data-ttu-id="aa9d6-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> "fehlerpropagationquery"**</span><span class="sxs-lookup"><span data-stu-id="aa9d6-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="aa9d6-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa9d6-116">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="aa9d6-117">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aa9d6-117">Attributes and elements</span></span>

<span data-ttu-id="aa9d6-118">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-118">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa9d6-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="aa9d6-119">Attributes</span></span>

|<span data-ttu-id="aa9d6-120">Attribut</span><span class="sxs-lookup"><span data-stu-id="aa9d6-120">Attribute</span></span>|<span data-ttu-id="aa9d6-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa9d6-121">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="aa9d6-122">Eine Zeichenfolge, die den Namen der fehlerhandleraktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-122">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="aa9d6-123">Der Standardwert \*ist, womit angegeben wird, dass für alle Aktivitäten fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-123">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="aa9d6-124">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="aa9d6-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa9d6-125">Child elements</span></span>

<span data-ttu-id="aa9d6-126">Keine</span><span class="sxs-lookup"><span data-stu-id="aa9d6-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="aa9d6-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa9d6-127">Parent elements</span></span>

|<span data-ttu-id="aa9d6-128">Element</span><span class="sxs-lookup"><span data-stu-id="aa9d6-128">Element</span></span>|<span data-ttu-id="aa9d6-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa9d6-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa9d6-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="aa9d6-130">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="aa9d6-131">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="aa9d6-132">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="aa9d6-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="aa9d6-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa9d6-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="aa9d6-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="aa9d6-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aa9d6-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="aa9d6-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
