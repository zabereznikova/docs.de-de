---
title: <customTrackingQueries> von WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 8b317cc289853902592e145e34b6e7bf5f84763b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704166"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="dadc3-102">\<CustomTrackingQueries > von WCF</span><span class="sxs-lookup"><span data-stu-id="dadc3-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="dadc3-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="dadc3-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="dadc3-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="dadc3-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="dadc3-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dadc3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="dadc3-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dadc3-106">\<system.serviceModel></span></span>  
<span data-ttu-id="dadc3-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="dadc3-107">\<tracking></span></span>  
<span data-ttu-id="dadc3-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="dadc3-108">\<profiles></span></span>  
<span data-ttu-id="dadc3-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="dadc3-109">\<trackingProfile></span></span>  
<span data-ttu-id="dadc3-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="dadc3-110">\<workflow></span></span>  
<span data-ttu-id="dadc3-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="dadc3-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dadc3-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="dadc3-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dadc3-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dadc3-113">Attributes and elements</span></span>

<span data-ttu-id="dadc3-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dadc3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dadc3-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="dadc3-115">Attributes</span></span>

<span data-ttu-id="dadc3-116">Keine</span><span class="sxs-lookup"><span data-stu-id="dadc3-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="dadc3-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dadc3-117">Child elements</span></span>
  
|<span data-ttu-id="dadc3-118">Element</span><span class="sxs-lookup"><span data-stu-id="dadc3-118">Element</span></span>|<span data-ttu-id="dadc3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dadc3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dadc3-120">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="dadc3-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="dadc3-121">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="dadc3-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dadc3-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dadc3-122">Parent elements</span></span>  
  
|<span data-ttu-id="dadc3-123">Element</span><span class="sxs-lookup"><span data-stu-id="dadc3-123">Element</span></span>|<span data-ttu-id="dadc3-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dadc3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dadc3-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="dadc3-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="dadc3-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="dadc3-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dadc3-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dadc3-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dadc3-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="dadc3-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dadc3-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="dadc3-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
