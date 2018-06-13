---
title: '&lt;faultPropagationQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 3c8038c133eb7f7a8d47c950037332fa68aa065e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756071"
---
# <a name="ltfaultpropagationquerygt"></a><span data-ttu-id="0b7de-102">&lt;faultPropagationQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="0b7de-102">&lt;faultPropagationQuery&gt;</span></span>
<span data-ttu-id="0b7de-103">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="0b7de-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0b7de-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0b7de-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="0b7de-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="0b7de-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="0b7de-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0b7de-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="0b7de-107">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0b7de-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0b7de-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0b7de-108">\<system.serviceModel></span></span>  
<span data-ttu-id="0b7de-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="0b7de-109">\<tracking></span></span>  
<span data-ttu-id="0b7de-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0b7de-110">\<trackingProfile></span></span>  
<span data-ttu-id="0b7de-111">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="0b7de-111">\<workflow></span></span>  
<span data-ttu-id="0b7de-112">\<FaultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="0b7de-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="0b7de-113">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="0b7de-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b7de-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b7de-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b7de-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b7de-115">Attributes and Elements</span></span>  
 <span data-ttu-id="0b7de-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b7de-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b7de-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b7de-117">Attributes</span></span>  
  
|<span data-ttu-id="0b7de-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="0b7de-118">Attribute</span></span>|<span data-ttu-id="0b7de-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b7de-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b7de-120">activityName</span><span class="sxs-lookup"><span data-stu-id="0b7de-120">activityName</span></span>|<span data-ttu-id="0b7de-121">Eine Zeichenfolge, die den Namen der FaultHandler-Aktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="0b7de-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="0b7de-122">Standardwert ist \*, wodurch angegeben wird, dass für alle Aktivitäten Fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0b7de-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="0b7de-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="0b7de-123">faultHandlerActivityName</span></span>|<span data-ttu-id="0b7de-124">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0b7de-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b7de-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b7de-125">Child Elements</span></span>  
 <span data-ttu-id="0b7de-126">Keine</span><span class="sxs-lookup"><span data-stu-id="0b7de-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b7de-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b7de-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0b7de-128">Element</span><span class="sxs-lookup"><span data-stu-id="0b7de-128">Element</span></span>|<span data-ttu-id="0b7de-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b7de-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b7de-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="0b7de-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="0b7de-131">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="0b7de-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0b7de-132">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0b7de-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b7de-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b7de-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="0b7de-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0b7de-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0b7de-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="0b7de-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
