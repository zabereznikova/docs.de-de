---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 968cfa8e5402458afd6f13545ed999a472adf2e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151909"
---
# <a name="tracking"></a><span data-ttu-id="0a837-101">\<> verfolgen</span><span class="sxs-lookup"><span data-stu-id="0a837-101">\<tracking></span></span>
<span data-ttu-id="0a837-102">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="0a837-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="0a837-103">Weitere Informationen zur Workflowverfolgung und deren Konfiguration finden Sie unter [Workflowverfolgung und Ablaufverfolgung](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Konfigurieren von Tracking für einen Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="0a837-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="0a837-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0a837-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0a837-105">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0a837-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="0a837-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Tracking->**</span><span class="sxs-lookup"><span data-stu-id="0a837-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a837-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a837-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a837-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a837-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0a837-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a837-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a837-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="0a837-110">Attributes</span></span>  
 <span data-ttu-id="0a837-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="0a837-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a837-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a837-112">Child Elements</span></span>  
  
|<span data-ttu-id="0a837-113">Element</span><span class="sxs-lookup"><span data-stu-id="0a837-113">Element</span></span>|<span data-ttu-id="0a837-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a837-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a837-115">\<Teilnehmer></span><span class="sxs-lookup"><span data-stu-id="0a837-115">\<participants></span></span>](participants.md)|<span data-ttu-id="0a837-116">Eine Auflistung von Konfigurationselementen, die die Teilnehmer angibt, die Nachverfolgungsdatensätze abonniert haben.</span><span class="sxs-lookup"><span data-stu-id="0a837-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="0a837-117">Die Nachverfolgungsteilnehmer enthalten die Logik zur Verarbeitung der Nutzdaten der Nachverfolgungsdatensätze (beispielsweise für das Schreiben in eine Datei).</span><span class="sxs-lookup"><span data-stu-id="0a837-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="0a837-118">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0a837-118">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="0a837-119">Ein Nachverfolgungsprofil, das die von einer Workflowinstanz ausgegebenen Nachverfolgungsdatensätze filtert.</span><span class="sxs-lookup"><span data-stu-id="0a837-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a837-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a837-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0a837-121">Element</span><span class="sxs-lookup"><span data-stu-id="0a837-121">Element</span></span>|<span data-ttu-id="0a837-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a837-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a837-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0a837-123">system.ServiceModel</span></span>|<span data-ttu-id="0a837-124">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="0a837-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a837-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0a837-125">Remarks</span></span>  
 <span data-ttu-id="0a837-126">Die Nachverfolgung bietet Ihnen die Möglichkeit, die Ausführung eines Workflows zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="0a837-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="0a837-127">Die Infrastruktur für die Workflownachverfolgung verwendet einen Workflow, um während der Ausführung Datensätze auszugeben, die Schlüsselereignisse festhalten.</span><span class="sxs-lookup"><span data-stu-id="0a837-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="0a837-128">Nachverfolgungsdatensätze werden zum Beispiel ausgegeben, wenn eine Workflowinstanz startet oder abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="0a837-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="0a837-129">Die Nachverfolgung kann auch geschäftsrelevante, den Workflowvariablen zugeordnete Daten extrahieren.</span><span class="sxs-lookup"><span data-stu-id="0a837-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="0a837-130">Wenn zum Beispiel der Workflow ein System zur Verarbeitung von Bestellungen darstellt, kann die Bestellungs-ID zusammen mit dem Nachverfolgungsdatensatz extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="0a837-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="0a837-131">Im Allgemeinen erleichtert die WF-Nachverfolgung während einer Workflowausführung die Diagnose oder die Geschäftsanalyse.</span><span class="sxs-lookup"><span data-stu-id="0a837-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a837-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a837-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="0a837-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0a837-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
