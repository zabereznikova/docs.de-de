---
title: '&lt;cancelRequestedQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: a3d24536589288ce9585901f3d955075bc856c97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520307"
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="983f8-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="983f8-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="983f8-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="983f8-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="983f8-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="983f8-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="983f8-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="983f8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="983f8-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="983f8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="983f8-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="983f8-107">\<tracking></span></span>  
<span data-ttu-id="983f8-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="983f8-108">\<trackingProfile></span></span>  
<span data-ttu-id="983f8-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="983f8-109">\<workflow></span></span>  
<span data-ttu-id="983f8-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="983f8-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="983f8-111">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="983f8-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983f8-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="983f8-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="983f8-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="983f8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="983f8-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="983f8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="983f8-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="983f8-115">Attributes</span></span>  
  
|<span data-ttu-id="983f8-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="983f8-116">Attribute</span></span>|<span data-ttu-id="983f8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="983f8-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="983f8-118">activityName</span><span class="sxs-lookup"><span data-stu-id="983f8-118">activityName</span></span>|<span data-ttu-id="983f8-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="983f8-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="983f8-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="983f8-120">childActivityName</span></span>|<span data-ttu-id="983f8-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="983f8-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="983f8-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="983f8-122">Child Elements</span></span>  
 <span data-ttu-id="983f8-123">Keine</span><span class="sxs-lookup"><span data-stu-id="983f8-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="983f8-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="983f8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="983f8-125">Element</span><span class="sxs-lookup"><span data-stu-id="983f8-125">Element</span></span>|<span data-ttu-id="983f8-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="983f8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="983f8-127">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="983f8-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="983f8-128">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="983f8-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="983f8-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="983f8-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="983f8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="983f8-130">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="983f8-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="983f8-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="983f8-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="983f8-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
