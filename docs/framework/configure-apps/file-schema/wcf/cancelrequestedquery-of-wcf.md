---
title: <cancelRequestedQuery>von WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 7952520edbf799e5fab6864e50962c6ec2860928
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919648"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="35a66-102">\<CancelRequestedQuery-> von WCF</span><span class="sxs-lookup"><span data-stu-id="35a66-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="35a66-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="35a66-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="35a66-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="35a66-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="35a66-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="35a66-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="35a66-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="35a66-106">\<system.serviceModel></span></span>  
<span data-ttu-id="35a66-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="35a66-107">\<tracking></span></span>  
<span data-ttu-id="35a66-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="35a66-108">\<profiles></span></span>  
<span data-ttu-id="35a66-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="35a66-109">\<trackingProfile></span></span>  
<span data-ttu-id="35a66-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="35a66-110">\<workflow></span></span>  
<span data-ttu-id="35a66-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="35a66-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="35a66-112">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="35a66-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a66-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="35a66-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35a66-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="35a66-114">Attributes and elements</span></span>

<span data-ttu-id="35a66-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="35a66-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="35a66-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="35a66-116">Attributes</span></span>  
  
|<span data-ttu-id="35a66-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="35a66-117">Attribute</span></span>|<span data-ttu-id="35a66-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35a66-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="35a66-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="35a66-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="35a66-120">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="35a66-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35a66-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35a66-121">Child elements</span></span>

<span data-ttu-id="35a66-122">Keine</span><span class="sxs-lookup"><span data-stu-id="35a66-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="35a66-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35a66-123">Parent elements</span></span>
  
|<span data-ttu-id="35a66-124">Element</span><span class="sxs-lookup"><span data-stu-id="35a66-124">Element</span></span>|<span data-ttu-id="35a66-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35a66-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35a66-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="35a66-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="35a66-127">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="35a66-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35a66-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35a66-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="35a66-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="35a66-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="35a66-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="35a66-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
