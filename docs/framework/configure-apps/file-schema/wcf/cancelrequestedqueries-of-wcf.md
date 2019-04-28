---
title: <cancelRequestedQueries> von WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: a9364fc53c7eb62a240206f6c81bd434b25c3f40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704374"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="eab29-102">\<CancelRequestedQueries > von WCF</span><span class="sxs-lookup"><span data-stu-id="eab29-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="eab29-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="eab29-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="eab29-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="eab29-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="eab29-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="eab29-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="eab29-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eab29-106">\<system.serviceModel></span></span>  
<span data-ttu-id="eab29-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="eab29-107">\<tracking></span></span>  
<span data-ttu-id="eab29-108">\<profiles> \<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="eab29-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="eab29-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="eab29-109">\<workflow></span></span>  
<span data-ttu-id="eab29-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="eab29-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eab29-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="eab29-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eab29-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eab29-112">Attributes and elements</span></span>  

<span data-ttu-id="eab29-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eab29-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eab29-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="eab29-114">Attributes</span></span>

<span data-ttu-id="eab29-115">Keine</span><span class="sxs-lookup"><span data-stu-id="eab29-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="eab29-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eab29-116">Child elements</span></span>
  
|<span data-ttu-id="eab29-117">Element</span><span class="sxs-lookup"><span data-stu-id="eab29-117">Element</span></span>|<span data-ttu-id="eab29-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eab29-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eab29-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="eab29-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="eab29-120">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="eab29-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eab29-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eab29-121">Parent elements</span></span>  
  
|<span data-ttu-id="eab29-122">Element</span><span class="sxs-lookup"><span data-stu-id="eab29-122">Element</span></span>|<span data-ttu-id="eab29-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eab29-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eab29-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="eab29-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="eab29-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="eab29-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eab29-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eab29-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="eab29-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="eab29-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eab29-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="eab29-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
