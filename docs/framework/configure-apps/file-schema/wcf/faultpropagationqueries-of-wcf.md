---
title: '&lt;faultPropagationQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 1db99a8d80fad5c0eca93777d87047b43371d048
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50202119"
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="3578e-102">&lt;faultPropagationQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="3578e-102">&lt;faultPropagationQueries&gt; of WCF</span></span>

<span data-ttu-id="3578e-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="3578e-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3578e-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3578e-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="3578e-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="3578e-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="3578e-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3578e-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="3578e-107">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3578e-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3578e-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3578e-108">\<system.serviceModel></span></span>  
<span data-ttu-id="3578e-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="3578e-109">\<tracking></span></span>  
<span data-ttu-id="3578e-110">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="3578e-110">\<profiles></span></span>  
<span data-ttu-id="3578e-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3578e-111">\<trackingProfile></span></span>  
<span data-ttu-id="3578e-112">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="3578e-112">\<workflow></span></span>  
<span data-ttu-id="3578e-113">\<FaultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="3578e-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3578e-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="3578e-114">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="3578e-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3578e-115">Attributes and elements</span></span>

<span data-ttu-id="3578e-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3578e-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3578e-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="3578e-117">Attributes</span></span>

<span data-ttu-id="3578e-118">Keine</span><span class="sxs-lookup"><span data-stu-id="3578e-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="3578e-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3578e-119">Child elements</span></span>

|<span data-ttu-id="3578e-120">Element</span><span class="sxs-lookup"><span data-stu-id="3578e-120">Element</span></span>|<span data-ttu-id="3578e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3578e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3578e-122">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="3578e-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="3578e-123">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="3578e-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3578e-124">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3578e-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3578e-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3578e-125">Parent elements</span></span>  
  
|<span data-ttu-id="3578e-126">Element</span><span class="sxs-lookup"><span data-stu-id="3578e-126">Element</span></span>|<span data-ttu-id="3578e-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3578e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3578e-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3578e-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3578e-129">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="3578e-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3578e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3578e-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3578e-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3578e-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3578e-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3578e-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
