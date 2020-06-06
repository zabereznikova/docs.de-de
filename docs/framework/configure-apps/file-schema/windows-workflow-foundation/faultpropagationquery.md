---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398719"
---
# \<faultPropagationQuery>

<span data-ttu-id="71662-101">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="71662-101">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="71662-102">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="71662-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="71662-103">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="71662-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="71662-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="71662-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="71662-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="71662-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**

## <a name="syntax"></a><span data-ttu-id="71662-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="71662-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="71662-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="71662-107">Attributes and Elements</span></span>

<span data-ttu-id="71662-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="71662-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="71662-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="71662-109">Attributes</span></span>

|<span data-ttu-id="71662-110">attribute</span><span class="sxs-lookup"><span data-stu-id="71662-110">Attribute</span></span>|<span data-ttu-id="71662-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="71662-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="71662-112">activityName</span><span class="sxs-lookup"><span data-stu-id="71662-112">activityName</span></span>|<span data-ttu-id="71662-113">Eine Zeichenfolge, die den Namen der fehlerhandleraktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="71662-113">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="71662-114">Standardwert ist \*, wodurch angegeben wird, dass für alle Aktivitäten Fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="71662-114">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="71662-115">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="71662-115">faultHandlerActivityName</span></span>|<span data-ttu-id="71662-116">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="71662-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="71662-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="71662-117">Child Elements</span></span>

<span data-ttu-id="71662-118">Keine</span><span class="sxs-lookup"><span data-stu-id="71662-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="71662-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="71662-119">Parent Elements</span></span>

|<span data-ttu-id="71662-120">Element</span><span class="sxs-lookup"><span data-stu-id="71662-120">Element</span></span>|<span data-ttu-id="71662-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71662-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries.md)|<span data-ttu-id="71662-122">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="71662-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="71662-123">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="71662-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="71662-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71662-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="71662-125">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="71662-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="71662-126">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="71662-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
