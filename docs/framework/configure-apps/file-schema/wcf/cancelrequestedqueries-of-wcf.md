---
title: <cancelRequestedQueries>von WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 0f04fc928358c96ca3112422f1a6ccd039269e47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926245"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="4bd6f-102">\<cancelrequestedqueries-> von WCF</span><span class="sxs-lookup"><span data-stu-id="4bd6f-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="4bd6f-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="4bd6f-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="4bd6f-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="4bd6f-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="4bd6f-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="4bd6f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4bd6f-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4bd6f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4bd6f-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="4bd6f-107">\<tracking></span></span>  
<span data-ttu-id="4bd6f-108">\<Profile > \<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="4bd6f-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="4bd6f-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4bd6f-109">\<workflow></span></span>  
<span data-ttu-id="4bd6f-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="4bd6f-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd6f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bd6f-111">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4bd6f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4bd6f-112">Attributes and elements</span></span>  

<span data-ttu-id="4bd6f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4bd6f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4bd6f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="4bd6f-114">Attributes</span></span>

<span data-ttu-id="4bd6f-115">Keine</span><span class="sxs-lookup"><span data-stu-id="4bd6f-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="4bd6f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4bd6f-116">Child elements</span></span>
  
|<span data-ttu-id="4bd6f-117">Element</span><span class="sxs-lookup"><span data-stu-id="4bd6f-117">Element</span></span>|<span data-ttu-id="4bd6f-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4bd6f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4bd6f-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="4bd6f-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="4bd6f-120">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="4bd6f-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4bd6f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4bd6f-121">Parent elements</span></span>  
  
|<span data-ttu-id="4bd6f-122">Element</span><span class="sxs-lookup"><span data-stu-id="4bd6f-122">Element</span></span>|<span data-ttu-id="4bd6f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4bd6f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4bd6f-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4bd6f-124">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="4bd6f-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="4bd6f-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bd6f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bd6f-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="4bd6f-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="4bd6f-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4bd6f-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="4bd6f-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
