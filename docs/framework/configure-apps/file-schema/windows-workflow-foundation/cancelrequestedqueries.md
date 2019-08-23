---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 628dbf801cae5f61dc7d518c27df3380dd2d3d23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945950"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="58b96-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="58b96-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="58b96-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="58b96-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="58b96-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="58b96-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="58b96-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="58b96-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="58b96-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="58b96-105">\<system.serviceModel></span></span>  
<span data-ttu-id="58b96-106">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="58b96-106">\<tracking></span></span>  
<span data-ttu-id="58b96-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="58b96-107">\<trackingProfile></span></span>  
<span data-ttu-id="58b96-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="58b96-108">\<workflow></span></span>  
<span data-ttu-id="58b96-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="58b96-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b96-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="58b96-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58b96-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="58b96-111">Attributes and Elements</span></span>  
 <span data-ttu-id="58b96-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58b96-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58b96-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="58b96-113">Attributes</span></span>  
 <span data-ttu-id="58b96-114">Keine</span><span class="sxs-lookup"><span data-stu-id="58b96-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="58b96-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58b96-115">Child Elements</span></span>  
  
|<span data-ttu-id="58b96-116">Element</span><span class="sxs-lookup"><span data-stu-id="58b96-116">Element</span></span>|<span data-ttu-id="58b96-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58b96-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58b96-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="58b96-118">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="58b96-119">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="58b96-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58b96-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58b96-120">Parent Elements</span></span>  
  
|<span data-ttu-id="58b96-121">Element</span><span class="sxs-lookup"><span data-stu-id="58b96-121">Element</span></span>|<span data-ttu-id="58b96-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58b96-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58b96-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="58b96-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="58b96-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="58b96-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58b96-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58b96-125">See also</span></span>

- [<span data-ttu-id="58b96-126">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="58b96-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="58b96-127">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="58b96-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
