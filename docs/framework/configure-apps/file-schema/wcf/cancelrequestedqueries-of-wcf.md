---
title: '&lt;cancelRequestedQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 4d746290f01e702979d1dd0165ad3fc5299e1b75
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087751"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="a7fcb-102">&lt;cancelRequestedQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="a7fcb-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="a7fcb-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="a7fcb-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a7fcb-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a7fcb-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="a7fcb-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a7fcb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="a7fcb-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a7fcb-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a7fcb-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="a7fcb-107">\<tracking></span></span>  
<span data-ttu-id="a7fcb-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a7fcb-108">\<trackingProfile></span></span>  
<span data-ttu-id="a7fcb-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a7fcb-109">\<workflow></span></span>  
<span data-ttu-id="a7fcb-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="a7fcb-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7fcb-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7fcb-111">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="a7fcb-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a7fcb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a7fcb-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7fcb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7fcb-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7fcb-114">Attributes</span></span>  
 <span data-ttu-id="a7fcb-115">Keine</span><span class="sxs-lookup"><span data-stu-id="a7fcb-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a7fcb-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7fcb-116">Child Elements</span></span>  
  
|<span data-ttu-id="a7fcb-117">Element</span><span class="sxs-lookup"><span data-stu-id="a7fcb-117">Element</span></span>|<span data-ttu-id="a7fcb-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7fcb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7fcb-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="a7fcb-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="a7fcb-120">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a7fcb-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7fcb-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7fcb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a7fcb-122">Element</span><span class="sxs-lookup"><span data-stu-id="a7fcb-122">Element</span></span>|<span data-ttu-id="a7fcb-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7fcb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7fcb-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a7fcb-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="a7fcb-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a7fcb-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7fcb-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7fcb-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="a7fcb-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a7fcb-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a7fcb-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a7fcb-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
