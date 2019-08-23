---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 79230c65d8eb8c15cef5dce73698448ca7b1e003
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947312"
---
# <a name="tracking"></a><span data-ttu-id="115f9-101">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="115f9-101">\<tracking></span></span>
<span data-ttu-id="115f9-102">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="115f9-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="115f9-103">Weitere Informationen zur Workflow Überwachung und deren Konfiguration finden Sie unter [Workflow Überwachung und](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) -Ablauf Verfolgung und [Konfigurieren der Nachverfolgung für einen Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="115f9-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="115f9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="115f9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="115f9-105">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="115f9-105">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="115f9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="115f9-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="115f9-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="115f9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="115f9-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="115f9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="115f9-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="115f9-109">Attributes</span></span>  
 <span data-ttu-id="115f9-110">Keine</span><span class="sxs-lookup"><span data-stu-id="115f9-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="115f9-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="115f9-111">Child Elements</span></span>  
  
|<span data-ttu-id="115f9-112">Element</span><span class="sxs-lookup"><span data-stu-id="115f9-112">Element</span></span>|<span data-ttu-id="115f9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="115f9-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="115f9-114">\<participants></span><span class="sxs-lookup"><span data-stu-id="115f9-114">\<participants></span></span>](participants.md)|<span data-ttu-id="115f9-115">Eine Auflistung von Konfigurationselementen, die Teilnehmer definieren, die nach Verfolgungs Datensätze abonnieren.</span><span class="sxs-lookup"><span data-stu-id="115f9-115">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="115f9-116">Die Nachverfolgungsteilnehmer enthalten die Logik zur Verarbeitung der Nutzdaten der Nachverfolgungsdatensätze (beispielsweise für das Schreiben in eine Datei).</span><span class="sxs-lookup"><span data-stu-id="115f9-116">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="115f9-117">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="115f9-117">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="115f9-118">Ein Nachverfolgungsprofil, das die von einer Workflowinstanz ausgegebenen Nachverfolgungsdatensätze filtert.</span><span class="sxs-lookup"><span data-stu-id="115f9-118">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="115f9-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="115f9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="115f9-120">Element</span><span class="sxs-lookup"><span data-stu-id="115f9-120">Element</span></span>|<span data-ttu-id="115f9-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="115f9-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="115f9-122">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="115f9-122">system.ServiceModel</span></span>|<span data-ttu-id="115f9-123">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="115f9-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="115f9-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="115f9-124">Remarks</span></span>  
 <span data-ttu-id="115f9-125">Die Nachverfolgung bietet Ihnen die Möglichkeit, die Ausführung eines Workflows zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="115f9-125">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="115f9-126">Die Infrastruktur für die Workflownachverfolgung verwendet einen Workflow, um während der Ausführung Datensätze auszugeben, die Schlüsselereignisse festhalten.</span><span class="sxs-lookup"><span data-stu-id="115f9-126">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="115f9-127">Nachverfolgungsdatensätze werden zum Beispiel ausgegeben, wenn eine Workflowinstanz startet oder abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="115f9-127">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="115f9-128">Die Nachverfolgung kann auch geschäftsrelevante, den Workflowvariablen zugeordnete Daten extrahieren.</span><span class="sxs-lookup"><span data-stu-id="115f9-128">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="115f9-129">Wenn zum Beispiel der Workflow ein System zur Verarbeitung von Bestellungen darstellt, kann die Bestellungs-ID zusammen mit dem Nachverfolgungsdatensatz extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="115f9-129">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="115f9-130">Im Allgemeinen erleichtert die WF-Nachverfolgung während einer Workflowausführung die Diagnose oder die Geschäftsanalyse.</span><span class="sxs-lookup"><span data-stu-id="115f9-130">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="115f9-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="115f9-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="115f9-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="115f9-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
