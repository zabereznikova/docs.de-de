---
title: '&lt;cancelRequestedQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 38d946a213131e8dcb6f4100d0ad67f7c167f342
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086400"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="11f74-102">&lt;cancelRequestedQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="11f74-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="11f74-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="11f74-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="11f74-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="11f74-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="11f74-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="11f74-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="11f74-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="11f74-106">\<system.serviceModel></span></span>  
<span data-ttu-id="11f74-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="11f74-107">\<tracking></span></span>  
<span data-ttu-id="11f74-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="11f74-108">\<trackingProfile></span></span>  
<span data-ttu-id="11f74-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="11f74-109">\<workflow></span></span>  
<span data-ttu-id="11f74-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="11f74-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="11f74-111">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="11f74-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11f74-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="11f74-112">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="11f74-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="11f74-113">Attributes and Elements</span></span>  
 <span data-ttu-id="11f74-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11f74-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11f74-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="11f74-115">Attributes</span></span>  
  
|<span data-ttu-id="11f74-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="11f74-116">Attribute</span></span>|<span data-ttu-id="11f74-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11f74-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11f74-118">activityName</span><span class="sxs-lookup"><span data-stu-id="11f74-118">activityName</span></span>|<span data-ttu-id="11f74-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="11f74-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="11f74-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="11f74-120">childActivityName</span></span>|<span data-ttu-id="11f74-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="11f74-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11f74-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11f74-122">Child Elements</span></span>  
 <span data-ttu-id="11f74-123">Keine</span><span class="sxs-lookup"><span data-stu-id="11f74-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11f74-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11f74-124">Parent Elements</span></span>  
  
|<span data-ttu-id="11f74-125">Element</span><span class="sxs-lookup"><span data-stu-id="11f74-125">Element</span></span>|<span data-ttu-id="11f74-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11f74-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11f74-127">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="11f74-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="11f74-128">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="11f74-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="11f74-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="11f74-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11f74-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11f74-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>     
 [<span data-ttu-id="11f74-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="11f74-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="11f74-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="11f74-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
