---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 968cfa8e5402458afd6f13545ed999a472adf2e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151909"
---
# \<tracking>
<span data-ttu-id="c564b-101">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="c564b-101">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="c564b-102">Weitere Informationen zur Workflow Überwachung und deren Konfiguration finden Sie unter [Workflow Überwachung und](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) -Ablauf Verfolgung und [Konfigurieren der Nachverfolgung für einen Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="c564b-102">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="c564b-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="c564b-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c564b-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c564b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="c564b-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c564b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c564b-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="c564b-106">Attributes</span></span>  
 <span data-ttu-id="c564b-107">Keine</span><span class="sxs-lookup"><span data-stu-id="c564b-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c564b-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c564b-108">Child Elements</span></span>  
  
|<span data-ttu-id="c564b-109">Element</span><span class="sxs-lookup"><span data-stu-id="c564b-109">Element</span></span>|<span data-ttu-id="c564b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c564b-110">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](participants.md)|<span data-ttu-id="c564b-111">Eine Auflistung von Konfigurationselementen, die die Teilnehmer angibt, die Nachverfolgungsdatensätze abonniert haben.</span><span class="sxs-lookup"><span data-stu-id="c564b-111">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="c564b-112">Die Nachverfolgungsteilnehmer enthalten die Logik zur Verarbeitung der Nutzdaten der Nachverfolgungsdatensätze (beispielsweise für das Schreiben in eine Datei).</span><span class="sxs-lookup"><span data-stu-id="c564b-112">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](trackingprofile.md)|<span data-ttu-id="c564b-113">Ein Nachverfolgungsprofil, das die von einer Workflowinstanz ausgegebenen Nachverfolgungsdatensätze filtert.</span><span class="sxs-lookup"><span data-stu-id="c564b-113">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c564b-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c564b-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c564b-115">Element</span><span class="sxs-lookup"><span data-stu-id="c564b-115">Element</span></span>|<span data-ttu-id="c564b-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c564b-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c564b-117">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c564b-117">system.ServiceModel</span></span>|<span data-ttu-id="c564b-118">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="c564b-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c564b-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c564b-119">Remarks</span></span>  
 <span data-ttu-id="c564b-120">Die Nachverfolgung bietet Ihnen die Möglichkeit, die Ausführung eines Workflows zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="c564b-120">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="c564b-121">Die Infrastruktur für die Workflownachverfolgung verwendet einen Workflow, um während der Ausführung Datensätze auszugeben, die Schlüsselereignisse festhalten.</span><span class="sxs-lookup"><span data-stu-id="c564b-121">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="c564b-122">Nachverfolgungsdatensätze werden zum Beispiel ausgegeben, wenn eine Workflowinstanz startet oder abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c564b-122">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="c564b-123">Die Nachverfolgung kann auch geschäftsrelevante, den Workflowvariablen zugeordnete Daten extrahieren.</span><span class="sxs-lookup"><span data-stu-id="c564b-123">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="c564b-124">Wenn zum Beispiel der Workflow ein System zur Verarbeitung von Bestellungen darstellt, kann die Bestellungs-ID zusammen mit dem Nachverfolgungsdatensatz extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="c564b-124">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="c564b-125">Im Allgemeinen erleichtert die WF-Nachverfolgung während einer Workflowausführung die Diagnose oder die Geschäftsanalyse.</span><span class="sxs-lookup"><span data-stu-id="c564b-125">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c564b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c564b-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="c564b-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c564b-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
