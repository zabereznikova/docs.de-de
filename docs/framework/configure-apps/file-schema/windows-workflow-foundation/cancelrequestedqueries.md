---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 32a37fb3cc2b93046bea133f351185638b0d7545
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163162"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="05104-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="05104-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="05104-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="05104-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="05104-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="05104-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="05104-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="05104-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="05104-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="05104-105">\<system.serviceModel></span></span>  
<span data-ttu-id="05104-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="05104-106">\<tracking></span></span>  
<span data-ttu-id="05104-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="05104-107">\<trackingProfile></span></span>  
<span data-ttu-id="05104-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="05104-108">\<workflow></span></span>  
<span data-ttu-id="05104-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="05104-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05104-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="05104-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05104-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="05104-111">Attributes and Elements</span></span>  
 <span data-ttu-id="05104-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05104-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05104-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="05104-113">Attributes</span></span>  
 <span data-ttu-id="05104-114">Keine</span><span class="sxs-lookup"><span data-stu-id="05104-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05104-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05104-115">Child Elements</span></span>  
  
|<span data-ttu-id="05104-116">Element</span><span class="sxs-lookup"><span data-stu-id="05104-116">Element</span></span>|<span data-ttu-id="05104-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05104-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05104-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="05104-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="05104-119">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="05104-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05104-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05104-120">Parent Elements</span></span>  
  
|<span data-ttu-id="05104-121">Element</span><span class="sxs-lookup"><span data-stu-id="05104-121">Element</span></span>|<span data-ttu-id="05104-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05104-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05104-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="05104-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="05104-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="05104-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05104-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05104-125">See also</span></span>

- [<span data-ttu-id="05104-126">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="05104-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="05104-127">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="05104-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
