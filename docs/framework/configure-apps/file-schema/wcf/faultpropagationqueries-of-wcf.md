---
title: '&lt;faultPropagationQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 77a38f8474b5e2ac8634d6ea91bc80c6044ff3ed
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144963"
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="bd0c7-102">&lt;faultPropagationQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="bd0c7-102">&lt;faultPropagationQueries&gt; of WCF</span></span>

<span data-ttu-id="bd0c7-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="bd0c7-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="bd0c7-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="bd0c7-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="bd0c7-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="bd0c7-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="bd0c7-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="bd0c7-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="bd0c7-107">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bd0c7-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="bd0c7-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bd0c7-108">\<system.serviceModel></span></span>  
<span data-ttu-id="bd0c7-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="bd0c7-109">\<tracking></span></span>  
<span data-ttu-id="bd0c7-110">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="bd0c7-110">\<profiles></span></span>  
<span data-ttu-id="bd0c7-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="bd0c7-111">\<trackingProfile></span></span>  
<span data-ttu-id="bd0c7-112">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="bd0c7-112">\<workflow></span></span>  
<span data-ttu-id="bd0c7-113">\<FaultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="bd0c7-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0c7-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd0c7-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd0c7-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bd0c7-115">Attributes and elements</span></span>

<span data-ttu-id="bd0c7-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bd0c7-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="bd0c7-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="bd0c7-117">Attributes</span></span>

<span data-ttu-id="bd0c7-118">Keine</span><span class="sxs-lookup"><span data-stu-id="bd0c7-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="bd0c7-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bd0c7-119">Child elements</span></span>

|<span data-ttu-id="bd0c7-120">Element</span><span class="sxs-lookup"><span data-stu-id="bd0c7-120">Element</span></span>|<span data-ttu-id="bd0c7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd0c7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd0c7-122">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="bd0c7-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="bd0c7-123">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="bd0c7-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="bd0c7-124">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="bd0c7-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd0c7-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bd0c7-125">Parent elements</span></span>  
  
|<span data-ttu-id="bd0c7-126">Element</span><span class="sxs-lookup"><span data-stu-id="bd0c7-126">Element</span></span>|<span data-ttu-id="bd0c7-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd0c7-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd0c7-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="bd0c7-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="bd0c7-129">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="bd0c7-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd0c7-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd0c7-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bd0c7-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="bd0c7-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bd0c7-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="bd0c7-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
