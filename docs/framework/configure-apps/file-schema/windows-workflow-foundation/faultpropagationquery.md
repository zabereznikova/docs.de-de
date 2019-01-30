---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 1a6899eaa04ad16192e07f4bc2ad1abe6e4aedd5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257367"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="a5684-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="a5684-101">\<faultPropagationQuery></span></span>
<span data-ttu-id="a5684-102">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="a5684-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a5684-103">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a5684-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="a5684-104">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="a5684-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="a5684-105">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a5684-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="a5684-106">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a5684-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a5684-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a5684-107">\<system.serviceModel></span></span>  
<span data-ttu-id="a5684-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a5684-108">\<tracking></span></span>  
<span data-ttu-id="a5684-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a5684-109">\<trackingProfile></span></span>  
<span data-ttu-id="a5684-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a5684-110">\<workflow></span></span>  
<span data-ttu-id="a5684-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="a5684-111">\<faultPropagationQueries></span></span>  
<span data-ttu-id="a5684-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="a5684-112">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5684-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5684-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5684-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a5684-114">Attributes and Elements</span></span>  
 <span data-ttu-id="a5684-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a5684-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5684-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="a5684-116">Attributes</span></span>  
  
|<span data-ttu-id="a5684-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="a5684-117">Attribute</span></span>|<span data-ttu-id="a5684-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5684-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5684-119">activityName</span><span class="sxs-lookup"><span data-stu-id="a5684-119">activityName</span></span>|<span data-ttu-id="a5684-120">Eine Zeichenfolge, die den Namen der FaultHandler-Aktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="a5684-120">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="a5684-121">Standardwert ist \*, wodurch angegeben wird, dass für alle Aktivitäten Fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5684-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="a5684-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="a5684-122">faultHandlerActivityName</span></span>|<span data-ttu-id="a5684-123">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a5684-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5684-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5684-124">Child Elements</span></span>  
 <span data-ttu-id="a5684-125">Keine</span><span class="sxs-lookup"><span data-stu-id="a5684-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5684-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5684-126">Parent Elements</span></span>  
  
|<span data-ttu-id="a5684-127">Element</span><span class="sxs-lookup"><span data-stu-id="a5684-127">Element</span></span>|<span data-ttu-id="a5684-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5684-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5684-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="a5684-129">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="a5684-130">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="a5684-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a5684-131">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a5684-131">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5684-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5684-132">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a5684-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a5684-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a5684-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a5684-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
