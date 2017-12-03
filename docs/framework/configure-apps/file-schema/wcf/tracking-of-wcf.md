---
title: '&lt;tracking&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6594e466295eb51ff972c5565cfcd31b600a1ab6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="lttrackinggt-of-wcf"></a><span data-ttu-id="ac8cf-102">&lt;tracking&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="ac8cf-102">&lt;tracking&gt; of WCF</span></span>
<span data-ttu-id="ac8cf-103">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="ac8cf-104">Weitere Informationen workflownachverfolgung und zur Konfiguration finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Konfigurieren der nachverfolgung für einen Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="ac8cf-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
 <span data-ttu-id="ac8cf-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ac8cf-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ac8cf-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="ac8cf-106">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac8cf-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac8cf-107">Syntax</span></span>  
  
```xml
   <system.serviceModel>  <tracking>       <participants>       <add name="String"            profileName="String"           type="String" />      </participants>     <trackingProfile name="String">      <workflow activityDefinitionId="String">          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>         <workflowInstanceQueries>            <workflowInstanceQuery>              <states>                 <state name="String"/>              </states>          </workflowInstanceQuery>        </workflowInstanceQueries>      </workflow>    </trackingProfile>           </profiles>  </tracking></system.serviceModel>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac8cf-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ac8cf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ac8cf-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac8cf-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ac8cf-110">Attributes</span></span>  
 <span data-ttu-id="ac8cf-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ac8cf-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac8cf-112">Child Elements</span></span>  
  
|<span data-ttu-id="ac8cf-113">Element</span><span class="sxs-lookup"><span data-stu-id="ac8cf-113">Element</span></span>|<span data-ttu-id="ac8cf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac8cf-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac8cf-115">\<Teilnehmer ></span><span class="sxs-lookup"><span data-stu-id="ac8cf-115">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="ac8cf-116">Eine Auflistung von Konfigurationselementen, die Teilnehmer angibt, die Nachverfolgungsdatensätze abonnieren.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="ac8cf-117">Die Nachverfolgungsteilnehmer enthalten die Logik zur Verarbeitung der Nutzdaten der Nachverfolgungsdatensätze (beispielsweise für das Schreiben in eine Datei).</span><span class="sxs-lookup"><span data-stu-id="ac8cf-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="ac8cf-118">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ac8cf-118">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="ac8cf-119">Ein Nachverfolgungsprofil, das die von einer Workflowinstanz ausgegebenen Nachverfolgungsdatensätze filtert.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac8cf-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac8cf-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ac8cf-121">Element</span><span class="sxs-lookup"><span data-stu-id="ac8cf-121">Element</span></span>|<span data-ttu-id="ac8cf-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac8cf-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac8cf-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ac8cf-123">system.ServiceModel</span></span>|<span data-ttu-id="ac8cf-124">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac8cf-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac8cf-125">Remarks</span></span>  
 <span data-ttu-id="ac8cf-126">Die Nachverfolgung bietet Ihnen die Möglichkeit, die Ausführung eines Workflows zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="ac8cf-127">Die Infrastruktur für die Workflownachverfolgung verwendet einen Workflow, um während der Ausführung Datensätze auszugeben, die Schlüsselereignisse festhalten.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="ac8cf-128">Nachverfolgungsdatensätze werden zum Beispiel ausgegeben, wenn eine Workflowinstanz startet oder abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="ac8cf-129">Die Nachverfolgung kann auch geschäftsrelevante, den Workflowvariablen zugeordnete Daten extrahieren.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="ac8cf-130">Wenn zum Beispiel der Workflow ein System zur Verarbeitung von Bestellungen darstellt, kann die Bestellungs-ID zusammen mit dem Nachverfolgungsdatensatz extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="ac8cf-131">Im Allgemeinen erleichtert die WF-Nachverfolgung während einer Workflowausführung die Diagnose oder die Geschäftsanalyse.</span><span class="sxs-lookup"><span data-stu-id="ac8cf-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac8cf-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac8cf-132">See Also</span></span>  
 <span data-ttu-id="ac8cf-133"><xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ac8cf-133"><xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="ac8cf-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ac8cf-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
