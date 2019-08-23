---
title: <faultPropagationQueries>von WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: aeb964fc8c96c8cb9aeb316bb95f9565fc4a7f18
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918942"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="5ae0f-102">\<"fehlerpropagationqueries"-> von WCF</span><span class="sxs-lookup"><span data-stu-id="5ae0f-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="5ae0f-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5ae0f-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="5ae0f-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="5ae0f-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="5ae0f-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5ae0f-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="5ae0f-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5ae0f-108">\<system.serviceModel></span></span>  
<span data-ttu-id="5ae0f-109">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="5ae0f-109">\<tracking></span></span>  
<span data-ttu-id="5ae0f-110">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="5ae0f-110">\<profiles></span></span>  
<span data-ttu-id="5ae0f-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5ae0f-111">\<trackingProfile></span></span>  
<span data-ttu-id="5ae0f-112">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5ae0f-112">\<workflow></span></span>  
<span data-ttu-id="5ae0f-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="5ae0f-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ae0f-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ae0f-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ae0f-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5ae0f-115">Attributes and elements</span></span>

<span data-ttu-id="5ae0f-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5ae0f-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="5ae0f-117">Attributes</span></span>

<span data-ttu-id="5ae0f-118">Keine</span><span class="sxs-lookup"><span data-stu-id="5ae0f-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="5ae0f-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5ae0f-119">Child elements</span></span>

|<span data-ttu-id="5ae0f-120">Element</span><span class="sxs-lookup"><span data-stu-id="5ae0f-120">Element</span></span>|<span data-ttu-id="5ae0f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ae0f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ae0f-122">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="5ae0f-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="5ae0f-123">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5ae0f-124">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ae0f-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5ae0f-125">Parent elements</span></span>  
  
|<span data-ttu-id="5ae0f-126">Element</span><span class="sxs-lookup"><span data-stu-id="5ae0f-126">Element</span></span>|<span data-ttu-id="5ae0f-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ae0f-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ae0f-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5ae0f-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="5ae0f-129">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="5ae0f-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ae0f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ae0f-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5ae0f-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="5ae0f-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5ae0f-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="5ae0f-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
