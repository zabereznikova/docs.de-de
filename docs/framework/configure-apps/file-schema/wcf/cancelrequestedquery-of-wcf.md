---
title: '&lt;cancelRequestedQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 6b41721dcc0c489377c59bfccdd0b1a617f551b0
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149071"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="d2bad-102">&lt;cancelRequestedQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="d2bad-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>

<span data-ttu-id="d2bad-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="d2bad-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d2bad-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="d2bad-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="d2bad-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d2bad-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="d2bad-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d2bad-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d2bad-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="d2bad-107">\<tracking></span></span>  
<span data-ttu-id="d2bad-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="d2bad-108">\<profiles></span></span>  
<span data-ttu-id="d2bad-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d2bad-109">\<trackingProfile></span></span>  
<span data-ttu-id="d2bad-110">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="d2bad-110">\<workflow></span></span>  
<span data-ttu-id="d2bad-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d2bad-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="d2bad-112">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="d2bad-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2bad-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2bad-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2bad-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d2bad-114">Attributes and elements</span></span>

<span data-ttu-id="d2bad-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d2bad-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d2bad-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="d2bad-116">Attributes</span></span>  
  
|<span data-ttu-id="d2bad-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="d2bad-117">Attribute</span></span>|<span data-ttu-id="d2bad-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2bad-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="d2bad-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="d2bad-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="d2bad-120">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="d2bad-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2bad-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d2bad-121">Child elements</span></span>

<span data-ttu-id="d2bad-122">Keine</span><span class="sxs-lookup"><span data-stu-id="d2bad-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="d2bad-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d2bad-123">Parent elements</span></span>
  
|<span data-ttu-id="d2bad-124">Element</span><span class="sxs-lookup"><span data-stu-id="d2bad-124">Element</span></span>|<span data-ttu-id="d2bad-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2bad-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2bad-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d2bad-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="d2bad-127">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="d2bad-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2bad-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2bad-128">See also</span></span>  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d2bad-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d2bad-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d2bad-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d2bad-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
