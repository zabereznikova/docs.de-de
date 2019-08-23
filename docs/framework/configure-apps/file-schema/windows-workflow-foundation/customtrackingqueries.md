---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 429940b2ed69d8be497626f634a21adca540b529
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945833"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="ed9c3-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ed9c3-101">\<customTrackingQueries></span></span>
<span data-ttu-id="ed9c3-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="ed9c3-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ed9c3-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ed9c3-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="ed9c3-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="ed9c3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ed9c3-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ed9c3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ed9c3-106">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="ed9c3-106">\<tracking></span></span>  
<span data-ttu-id="ed9c3-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ed9c3-107">\<trackingProfile></span></span>  
<span data-ttu-id="ed9c3-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ed9c3-108">\<workflow></span></span>  
<span data-ttu-id="ed9c3-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ed9c3-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed9c3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed9c3-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed9c3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ed9c3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ed9c3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed9c3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed9c3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ed9c3-113">Attributes</span></span>  
 <span data-ttu-id="ed9c3-114">Keine</span><span class="sxs-lookup"><span data-stu-id="ed9c3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ed9c3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed9c3-115">Child Elements</span></span>  
  
|<span data-ttu-id="ed9c3-116">Element</span><span class="sxs-lookup"><span data-stu-id="ed9c3-116">Element</span></span>|<span data-ttu-id="ed9c3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed9c3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed9c3-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ed9c3-118">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="ed9c3-119">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="ed9c3-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed9c3-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed9c3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ed9c3-121">Element</span><span class="sxs-lookup"><span data-stu-id="ed9c3-121">Element</span></span>|<span data-ttu-id="ed9c3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed9c3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed9c3-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ed9c3-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="ed9c3-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="ed9c3-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed9c3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed9c3-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ed9c3-126">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ed9c3-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ed9c3-127">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ed9c3-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
