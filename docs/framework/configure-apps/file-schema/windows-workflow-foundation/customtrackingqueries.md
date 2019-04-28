---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790220"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="3db03-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="3db03-101">\<customTrackingQueries></span></span>
<span data-ttu-id="3db03-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="3db03-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="3db03-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3db03-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="3db03-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3db03-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3db03-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3db03-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3db03-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3db03-106">\<tracking></span></span>  
<span data-ttu-id="3db03-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3db03-107">\<trackingProfile></span></span>  
<span data-ttu-id="3db03-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3db03-108">\<workflow></span></span>  
<span data-ttu-id="3db03-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="3db03-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3db03-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="3db03-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3db03-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3db03-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3db03-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3db03-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3db03-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="3db03-113">Attributes</span></span>  
 <span data-ttu-id="3db03-114">Keine</span><span class="sxs-lookup"><span data-stu-id="3db03-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3db03-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3db03-115">Child Elements</span></span>  
  
|<span data-ttu-id="3db03-116">Element</span><span class="sxs-lookup"><span data-stu-id="3db03-116">Element</span></span>|<span data-ttu-id="3db03-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3db03-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3db03-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="3db03-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="3db03-119">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="3db03-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3db03-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3db03-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3db03-121">Element</span><span class="sxs-lookup"><span data-stu-id="3db03-121">Element</span></span>|<span data-ttu-id="3db03-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3db03-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3db03-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3db03-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3db03-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3db03-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3db03-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3db03-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3db03-126">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3db03-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3db03-127">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3db03-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
