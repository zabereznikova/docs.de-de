---
title: <faultPropagationQuery>von WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855333"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="3aa1f-102">\<faultPropagationQuery>von WCF</span><span class="sxs-lookup"><span data-stu-id="3aa1f-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="3aa1f-103">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3aa1f-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="3aa1f-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="3aa1f-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="3aa1f-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3aa1f-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**  

## <a name="syntax"></a><span data-ttu-id="3aa1f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="3aa1f-108">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="3aa1f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3aa1f-109">Attributes and elements</span></span>

<span data-ttu-id="3aa1f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3aa1f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="3aa1f-111">Attributes</span></span>

|<span data-ttu-id="3aa1f-112">attribute</span><span class="sxs-lookup"><span data-stu-id="3aa1f-112">Attribute</span></span>|<span data-ttu-id="3aa1f-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3aa1f-113">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="3aa1f-114">Eine Zeichenfolge, die den Namen der fehlerhandleraktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-114">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="3aa1f-115">Der Standardwert ist \* , womit angegeben wird, dass für alle Aktivitäten fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-115">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="3aa1f-116">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3aa1f-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3aa1f-117">Child elements</span></span>

<span data-ttu-id="3aa1f-118">Keine</span><span class="sxs-lookup"><span data-stu-id="3aa1f-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3aa1f-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3aa1f-119">Parent elements</span></span>

|<span data-ttu-id="3aa1f-120">Element</span><span class="sxs-lookup"><span data-stu-id="3aa1f-120">Element</span></span>|<span data-ttu-id="3aa1f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3aa1f-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="3aa1f-122">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3aa1f-123">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3aa1f-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3aa1f-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3aa1f-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3aa1f-125">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3aa1f-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3aa1f-126">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3aa1f-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
