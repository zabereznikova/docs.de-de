---
title: '&lt;cancelRequestedQueries&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f31663d44774f84feab76f22f19400a955a3cf8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="6c4cb-102">&lt;cancelRequestedQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="6c4cb-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="6c4cb-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="6c4cb-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="6c4cb-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="6c4cb-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="6c4cb-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6c4cb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="6c4cb-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6c4cb-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6c4cb-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="6c4cb-107">\<tracking></span></span>  
<span data-ttu-id="6c4cb-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6c4cb-108">\<trackingProfile></span></span>  
<span data-ttu-id="6c4cb-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="6c4cb-109">\<workflow></span></span>  
<span data-ttu-id="6c4cb-110">\<CancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="6c4cb-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c4cb-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c4cb-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6c4cb-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6c4cb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6c4cb-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c4cb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c4cb-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c4cb-114">Attributes</span></span>  
 <span data-ttu-id="6c4cb-115">Keine</span><span class="sxs-lookup"><span data-stu-id="6c4cb-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c4cb-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c4cb-116">Child Elements</span></span>  
  
|<span data-ttu-id="6c4cb-117">Element</span><span class="sxs-lookup"><span data-stu-id="6c4cb-117">Element</span></span>|<span data-ttu-id="6c4cb-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c4cb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c4cb-119">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="6c4cb-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="6c4cb-120">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="6c4cb-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c4cb-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c4cb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6c4cb-122">Element</span><span class="sxs-lookup"><span data-stu-id="6c4cb-122">Element</span></span>|<span data-ttu-id="6c4cb-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c4cb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c4cb-124">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="6c4cb-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6c4cb-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="6c4cb-125">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c4cb-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c4cb-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="6c4cb-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="6c4cb-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="6c4cb-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="6c4cb-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
