---
title: '&lt;faultPropagationQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: 1da2a95d27756296aab5a205a90fb028508c4b76
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601804"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="55b27-102">&lt;faultPropagationQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="55b27-102">&lt;faultPropagationQuery&gt; of WCF</span></span>

<span data-ttu-id="55b27-103">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="55b27-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="55b27-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="55b27-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="55b27-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="55b27-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="55b27-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="55b27-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="55b27-107">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="55b27-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="55b27-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="55b27-108">\<system.serviceModel></span></span>  
<span data-ttu-id="55b27-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="55b27-109">\<tracking></span></span>  
<span data-ttu-id="55b27-110">\<profiles></span><span class="sxs-lookup"><span data-stu-id="55b27-110">\<profiles></span></span>  
<span data-ttu-id="55b27-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="55b27-111">\<trackingProfile></span></span>  
<span data-ttu-id="55b27-112">\<workflow></span><span class="sxs-lookup"><span data-stu-id="55b27-112">\<workflow></span></span>  
<span data-ttu-id="55b27-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="55b27-113">\<faultPropagationQueries></span></span>  
<span data-ttu-id="55b27-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="55b27-114">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55b27-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="55b27-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55b27-116">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="55b27-116">Attributes and elements</span></span>

<span data-ttu-id="55b27-117">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55b27-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="55b27-118">Attribute</span><span class="sxs-lookup"><span data-stu-id="55b27-118">Attributes</span></span>  
  
|<span data-ttu-id="55b27-119">Attribut</span><span class="sxs-lookup"><span data-stu-id="55b27-119">Attribute</span></span>|<span data-ttu-id="55b27-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55b27-120">Description</span></span>|  
|---------------|-----------------|  
|`faultSourceActivityName`|<span data-ttu-id="55b27-121">Eine Zeichenfolge, die den Namen der FaultHandler-Aktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="55b27-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="55b27-122">Der Standardwert ist \*, was bedeutet, dass für alle Aktivitäten fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="55b27-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|`faultHandlerActivityName`|<span data-ttu-id="55b27-123">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="55b27-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55b27-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55b27-124">Child elements</span></span>

<span data-ttu-id="55b27-125">Keine</span><span class="sxs-lookup"><span data-stu-id="55b27-125">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="55b27-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55b27-126">Parent elements</span></span>  
  
|<span data-ttu-id="55b27-127">Element</span><span class="sxs-lookup"><span data-stu-id="55b27-127">Element</span></span>|<span data-ttu-id="55b27-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55b27-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55b27-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="55b27-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="55b27-130">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="55b27-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="55b27-131">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="55b27-131">This event occurs each time a FaultHandler processes a fault.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="55b27-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55b27-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="55b27-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="55b27-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="55b27-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="55b27-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
