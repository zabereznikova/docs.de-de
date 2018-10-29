---
title: '&lt;customTrackingQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 060e2b5c8efd51f6245a39bd9562a69f0111fd41
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50202223"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="9cfc0-102">&lt;customTrackingQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="9cfc0-102">&lt;customTrackingQueries&gt; of WCF</span></span>

<span data-ttu-id="9cfc0-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="9cfc0-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="9cfc0-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="9cfc0-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="9cfc0-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9cfc0-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="9cfc0-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9cfc0-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9cfc0-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="9cfc0-107">\<tracking></span></span>  
<span data-ttu-id="9cfc0-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="9cfc0-108">\<profiles></span></span>  
<span data-ttu-id="9cfc0-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9cfc0-109">\<trackingProfile></span></span>  
<span data-ttu-id="9cfc0-110">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="9cfc0-110">\<workflow></span></span>  
<span data-ttu-id="9cfc0-111">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="9cfc0-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cfc0-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cfc0-112">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cfc0-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9cfc0-113">Attributes and elements</span></span>

<span data-ttu-id="9cfc0-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9cfc0-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cfc0-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="9cfc0-115">Attributes</span></span>

<span data-ttu-id="9cfc0-116">Keine</span><span class="sxs-lookup"><span data-stu-id="9cfc0-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="9cfc0-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9cfc0-117">Child elements</span></span>
  
|<span data-ttu-id="9cfc0-118">Element</span><span class="sxs-lookup"><span data-stu-id="9cfc0-118">Element</span></span>|<span data-ttu-id="9cfc0-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cfc0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cfc0-120">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="9cfc0-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="9cfc0-121">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="9cfc0-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9cfc0-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9cfc0-122">Parent elements</span></span>  
  
|<span data-ttu-id="9cfc0-123">Element</span><span class="sxs-lookup"><span data-stu-id="9cfc0-123">Element</span></span>|<span data-ttu-id="9cfc0-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cfc0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cfc0-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9cfc0-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9cfc0-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="9cfc0-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cfc0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cfc0-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="9cfc0-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="9cfc0-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="9cfc0-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="9cfc0-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
