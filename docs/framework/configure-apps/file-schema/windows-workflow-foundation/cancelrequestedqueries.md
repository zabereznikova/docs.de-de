---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 5bc2e3ffeb93bdfcd45638d6b50e218c03706f42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520684"
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="ebc44-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="ebc44-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="ebc44-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="ebc44-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ebc44-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ebc44-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="ebc44-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ebc44-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ebc44-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ebc44-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ebc44-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ebc44-107">\<tracking></span></span>  
<span data-ttu-id="ebc44-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ebc44-108">\<trackingProfile></span></span>  
<span data-ttu-id="ebc44-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ebc44-109">\<workflow></span></span>  
<span data-ttu-id="ebc44-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="ebc44-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc44-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebc44-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebc44-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ebc44-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ebc44-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebc44-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebc44-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="ebc44-114">Attributes</span></span>  
 <span data-ttu-id="ebc44-115">Keine</span><span class="sxs-lookup"><span data-stu-id="ebc44-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ebc44-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebc44-116">Child Elements</span></span>  
  
|<span data-ttu-id="ebc44-117">Element</span><span class="sxs-lookup"><span data-stu-id="ebc44-117">Element</span></span>|<span data-ttu-id="ebc44-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebc44-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ebc44-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="ebc44-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="ebc44-120">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="ebc44-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ebc44-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebc44-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ebc44-122">Element</span><span class="sxs-lookup"><span data-stu-id="ebc44-122">Element</span></span>|<span data-ttu-id="ebc44-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebc44-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ebc44-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ebc44-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ebc44-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ebc44-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebc44-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebc44-126">See also</span></span>
- [<span data-ttu-id="ebc44-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ebc44-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ebc44-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ebc44-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
