---
title: '&lt;faultPropagationQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: fe3dd90a5c6b26537ab461b4bf4993df5be625a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747358"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="2a22f-102">&lt;faultPropagationQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="2a22f-102">&lt;faultPropagationQuery&gt; of WCF</span></span>
<span data-ttu-id="2a22f-103">Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="2a22f-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2a22f-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="2a22f-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="2a22f-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="2a22f-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="2a22f-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="2a22f-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="2a22f-107">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2a22f-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="2a22f-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2a22f-108">\<system.serviceModel></span></span>  
<span data-ttu-id="2a22f-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="2a22f-109">\<tracking></span></span>  
<span data-ttu-id="2a22f-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2a22f-110">\<trackingProfile></span></span>  
<span data-ttu-id="2a22f-111">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="2a22f-111">\<workflow></span></span>  
<span data-ttu-id="2a22f-112">\<FaultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="2a22f-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="2a22f-113">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="2a22f-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a22f-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a22f-114">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a22f-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2a22f-115">Attributes and Elements</span></span>  
 <span data-ttu-id="2a22f-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2a22f-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a22f-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="2a22f-117">Attributes</span></span>  
  
|<span data-ttu-id="2a22f-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="2a22f-118">Attribute</span></span>|<span data-ttu-id="2a22f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a22f-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a22f-120">activityName</span><span class="sxs-lookup"><span data-stu-id="2a22f-120">activityName</span></span>|<span data-ttu-id="2a22f-121">Eine Zeichenfolge, die den Namen der FaultHandler-Aktivität angibt, die den Fehler weitergegeben hat.</span><span class="sxs-lookup"><span data-stu-id="2a22f-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="2a22f-122">Standardwert ist \*, wodurch angegeben wird, dass für alle Aktivitäten Fehlerweitergabedatensätze zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a22f-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="2a22f-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="2a22f-123">faultHandlerActivityName</span></span>|<span data-ttu-id="2a22f-124">Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2a22f-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a22f-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a22f-125">Child Elements</span></span>  
 <span data-ttu-id="2a22f-126">Keine</span><span class="sxs-lookup"><span data-stu-id="2a22f-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a22f-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a22f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2a22f-128">Element</span><span class="sxs-lookup"><span data-stu-id="2a22f-128">Element</span></span>|<span data-ttu-id="2a22f-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a22f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a22f-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="2a22f-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="2a22f-131">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="2a22f-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2a22f-132">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="2a22f-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a22f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a22f-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="2a22f-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="2a22f-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2a22f-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="2a22f-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
