---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 2abb2dc05bfec4419ca49d1517084ebc208e81e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757020"
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="c1ec3-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="c1ec3-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="c1ec3-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="c1ec3-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c1ec3-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="c1ec3-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="c1ec3-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c1ec3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c1ec3-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c1ec3-106">\<system.serviceModel></span></span>  
<span data-ttu-id="c1ec3-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="c1ec3-107">\<tracking></span></span>  
<span data-ttu-id="c1ec3-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c1ec3-108">\<trackingProfile></span></span>  
<span data-ttu-id="c1ec3-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="c1ec3-109">\<workflow></span></span>  
<span data-ttu-id="c1ec3-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="c1ec3-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ec3-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1ec3-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1ec3-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1ec3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c1ec3-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1ec3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1ec3-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1ec3-114">Attributes</span></span>  
 <span data-ttu-id="c1ec3-115">Keine</span><span class="sxs-lookup"><span data-stu-id="c1ec3-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1ec3-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1ec3-116">Child Elements</span></span>  
  
|<span data-ttu-id="c1ec3-117">Element</span><span class="sxs-lookup"><span data-stu-id="c1ec3-117">Element</span></span>|<span data-ttu-id="c1ec3-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1ec3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1ec3-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="c1ec3-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="c1ec3-120">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="c1ec3-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1ec3-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1ec3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c1ec3-122">Element</span><span class="sxs-lookup"><span data-stu-id="c1ec3-122">Element</span></span>|<span data-ttu-id="c1ec3-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1ec3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1ec3-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c1ec3-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="c1ec3-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c1ec3-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1ec3-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1ec3-126">See Also</span></span>  
 [<span data-ttu-id="c1ec3-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c1ec3-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="c1ec3-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="c1ec3-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
