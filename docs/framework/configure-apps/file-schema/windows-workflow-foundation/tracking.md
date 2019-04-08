---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 31490c7425572909cc30fe4237af9309754b68e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072244"
---
# <a name="tracking"></a><span data-ttu-id="43ddf-101">\<tracking></span><span class="sxs-lookup"><span data-stu-id="43ddf-101">\<tracking></span></span>
<span data-ttu-id="43ddf-102">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="43ddf-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="43ddf-103">Weitere Informationen workflownachverfolgung und zur Konfiguration finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Konfigurieren der nachverfolgung für einen Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="43ddf-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="43ddf-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="43ddf-104">\<system.serviceModel></span></span>  
<span data-ttu-id="43ddf-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="43ddf-105">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43ddf-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="43ddf-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String" 
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String" 
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String" 
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43ddf-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="43ddf-107">Attributes and Elements</span></span>  
 <span data-ttu-id="43ddf-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="43ddf-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43ddf-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="43ddf-109">Attributes</span></span>  
 <span data-ttu-id="43ddf-110">Keine</span><span class="sxs-lookup"><span data-stu-id="43ddf-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="43ddf-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43ddf-111">Child Elements</span></span>  
  
|<span data-ttu-id="43ddf-112">Element</span><span class="sxs-lookup"><span data-stu-id="43ddf-112">Element</span></span>|<span data-ttu-id="43ddf-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43ddf-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43ddf-114">\<participants></span><span class="sxs-lookup"><span data-stu-id="43ddf-114">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="43ddf-115">Eine Auflistung von Konfigurationselementen, die Teilnehmer, die Nachverfolgungsdatensätze abonnieren.</span><span class="sxs-lookup"><span data-stu-id="43ddf-115">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="43ddf-116">Die Nachverfolgungsteilnehmer enthalten die Logik zur Verarbeitung der Nutzdaten der Nachverfolgungsdatensätze (beispielsweise für das Schreiben in eine Datei).</span><span class="sxs-lookup"><span data-stu-id="43ddf-116">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="43ddf-117">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="43ddf-117">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="43ddf-118">Ein Nachverfolgungsprofil, das die von einer Workflowinstanz ausgegebenen Nachverfolgungsdatensätze filtert.</span><span class="sxs-lookup"><span data-stu-id="43ddf-118">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43ddf-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43ddf-119">Parent Elements</span></span>  
  
|<span data-ttu-id="43ddf-120">Element</span><span class="sxs-lookup"><span data-stu-id="43ddf-120">Element</span></span>|<span data-ttu-id="43ddf-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43ddf-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43ddf-122">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="43ddf-122">system.ServiceModel</span></span>|<span data-ttu-id="43ddf-123">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="43ddf-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43ddf-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43ddf-124">Remarks</span></span>  
 <span data-ttu-id="43ddf-125">Die Nachverfolgung bietet Ihnen die Möglichkeit, die Ausführung eines Workflows zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="43ddf-125">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="43ddf-126">Die Infrastruktur für die Workflownachverfolgung verwendet einen Workflow, um während der Ausführung Datensätze auszugeben, die Schlüsselereignisse festhalten.</span><span class="sxs-lookup"><span data-stu-id="43ddf-126">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="43ddf-127">Nachverfolgungsdatensätze werden zum Beispiel ausgegeben, wenn eine Workflowinstanz startet oder abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="43ddf-127">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="43ddf-128">Die Nachverfolgung kann auch geschäftsrelevante, den Workflowvariablen zugeordnete Daten extrahieren.</span><span class="sxs-lookup"><span data-stu-id="43ddf-128">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="43ddf-129">Wenn zum Beispiel der Workflow ein System zur Verarbeitung von Bestellungen darstellt, kann die Bestellungs-ID zusammen mit dem Nachverfolgungsdatensatz extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="43ddf-129">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="43ddf-130">Im Allgemeinen erleichtert die WF-Nachverfolgung während einer Workflowausführung die Diagnose oder die Geschäftsanalyse.</span><span class="sxs-lookup"><span data-stu-id="43ddf-130">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ddf-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43ddf-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="43ddf-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="43ddf-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
