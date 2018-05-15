---
title: '&lt;cancelRequestedQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 41964561a460babc41de755e213971593047b707
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="0b621-102">&lt;cancelRequestedQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="0b621-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="0b621-103">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0b621-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0b621-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0b621-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="0b621-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0b621-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="0b621-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0b621-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0b621-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="0b621-107">\<tracking></span></span>  
<span data-ttu-id="0b621-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0b621-108">\<trackingProfile></span></span>  
<span data-ttu-id="0b621-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="0b621-109">\<workflow></span></span>  
<span data-ttu-id="0b621-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="0b621-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="0b621-111">\<CancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="0b621-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b621-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b621-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b621-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b621-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0b621-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b621-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b621-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b621-115">Attributes</span></span>  
  
|<span data-ttu-id="0b621-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="0b621-116">Attribute</span></span>|<span data-ttu-id="0b621-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b621-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b621-118">activityName</span><span class="sxs-lookup"><span data-stu-id="0b621-118">activityName</span></span>|<span data-ttu-id="0b621-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="0b621-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="0b621-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="0b621-120">childActivityName</span></span>|<span data-ttu-id="0b621-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="0b621-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b621-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b621-122">Child Elements</span></span>  
 <span data-ttu-id="0b621-123">Keine</span><span class="sxs-lookup"><span data-stu-id="0b621-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b621-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b621-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0b621-125">Element</span><span class="sxs-lookup"><span data-stu-id="0b621-125">Element</span></span>|<span data-ttu-id="0b621-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b621-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b621-127">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="0b621-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="0b621-128">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0b621-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0b621-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0b621-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b621-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b621-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>     
 [<span data-ttu-id="0b621-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0b621-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0b621-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="0b621-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
