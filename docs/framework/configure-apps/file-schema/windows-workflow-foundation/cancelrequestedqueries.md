---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 32a37fb3cc2b93046bea133f351185638b0d7545
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790246"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="11151-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="11151-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="11151-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="11151-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="11151-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="11151-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="11151-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="11151-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="11151-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="11151-105">\<system.serviceModel></span></span>  
<span data-ttu-id="11151-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="11151-106">\<tracking></span></span>  
<span data-ttu-id="11151-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="11151-107">\<trackingProfile></span></span>  
<span data-ttu-id="11151-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="11151-108">\<workflow></span></span>  
<span data-ttu-id="11151-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="11151-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11151-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="11151-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11151-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="11151-111">Attributes and Elements</span></span>  
 <span data-ttu-id="11151-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11151-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11151-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="11151-113">Attributes</span></span>  
 <span data-ttu-id="11151-114">Keine</span><span class="sxs-lookup"><span data-stu-id="11151-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="11151-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11151-115">Child Elements</span></span>  
  
|<span data-ttu-id="11151-116">Element</span><span class="sxs-lookup"><span data-stu-id="11151-116">Element</span></span>|<span data-ttu-id="11151-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11151-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11151-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="11151-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="11151-119">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="11151-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11151-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11151-120">Parent Elements</span></span>  
  
|<span data-ttu-id="11151-121">Element</span><span class="sxs-lookup"><span data-stu-id="11151-121">Element</span></span>|<span data-ttu-id="11151-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11151-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11151-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="11151-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="11151-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11151-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11151-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11151-125">See also</span></span>

- [<span data-ttu-id="11151-126">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="11151-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="11151-127">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="11151-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
