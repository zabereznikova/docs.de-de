---
title: <tracking> von WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: 223a30cd79d346d6ae36ca64fa887a683e6bfc8d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201433"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="b3c0c-102">\<tracking> von WCF</span><span class="sxs-lookup"><span data-stu-id="b3c0c-102">\<tracking> of WCF</span></span>

<span data-ttu-id="b3c0c-103">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="b3c0c-104">Weitere Informationen zur Workflow Überwachung und deren Konfiguration finden Sie unter [Workflow Überwachung und](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) -Ablauf Verfolgung und [Konfigurieren der Nachverfolgung für einen Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b3c0c-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="b3c0c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3c0c-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
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
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3c0c-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b3c0c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b3c0c-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3c0c-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b3c0c-108">Attributes</span></span>  

 <span data-ttu-id="b3c0c-109">Keine</span><span class="sxs-lookup"><span data-stu-id="b3c0c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b3c0c-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3c0c-110">Child Elements</span></span>  
  
|<span data-ttu-id="b3c0c-111">Element</span><span class="sxs-lookup"><span data-stu-id="b3c0c-111">Element</span></span>|<span data-ttu-id="b3c0c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3c0c-112">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="b3c0c-113">Eine Auflistung von Konfigurationselementen, die die Teilnehmer angibt, die Nachverfolgungsdatensätze abonniert haben.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-113">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="b3c0c-114">Die Nachverfolgungsteilnehmer enthalten die Logik zur Verarbeitung der Nutzdaten der Nachverfolgungsdatensätze (beispielsweise für das Schreiben in eine Datei).</span><span class="sxs-lookup"><span data-stu-id="b3c0c-114">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="b3c0c-115">Ein Nachverfolgungsprofil, das die von einer Workflowinstanz ausgegebenen Nachverfolgungsdatensätze filtert.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-115">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3c0c-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3c0c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b3c0c-117">Element</span><span class="sxs-lookup"><span data-stu-id="b3c0c-117">Element</span></span>|<span data-ttu-id="b3c0c-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3c0c-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3c0c-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b3c0c-119">system.ServiceModel</span></span>|<span data-ttu-id="b3c0c-120">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-120">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3c0c-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b3c0c-121">Remarks</span></span>  

 <span data-ttu-id="b3c0c-122">Die Nachverfolgung bietet Ihnen die Möglichkeit, die Ausführung eines Workflows zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-122">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="b3c0c-123">Die Infrastruktur für die Workflownachverfolgung verwendet einen Workflow, um während der Ausführung Datensätze auszugeben, die Schlüsselereignisse festhalten.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-123">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="b3c0c-124">Nachverfolgungsdatensätze werden zum Beispiel ausgegeben, wenn eine Workflowinstanz startet oder abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-124">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="b3c0c-125">Die Nachverfolgung kann auch geschäftsrelevante, den Workflowvariablen zugeordnete Daten extrahieren.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-125">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="b3c0c-126">Wenn zum Beispiel der Workflow ein System zur Verarbeitung von Bestellungen darstellt, kann die Bestellungs-ID zusammen mit dem Nachverfolgungsdatensatz extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-126">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="b3c0c-127">Im Allgemeinen erleichtert die WF-Nachverfolgung während einer Workflowausführung die Diagnose oder die Geschäftsanalyse.</span><span class="sxs-lookup"><span data-stu-id="b3c0c-127">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c0c-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3c0c-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="b3c0c-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b3c0c-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
