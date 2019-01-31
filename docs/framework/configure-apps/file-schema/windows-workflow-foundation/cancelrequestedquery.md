---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 049ca79355f13fd4ffacedbb7501d760361f0a81
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282021"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="8e162-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="8e162-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="8e162-102">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="8e162-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8e162-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="8e162-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="8e162-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8e162-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8e162-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8e162-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8e162-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="8e162-106">\<tracking></span></span>  
<span data-ttu-id="8e162-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8e162-107">\<trackingProfile></span></span>  
<span data-ttu-id="8e162-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8e162-108">\<workflow></span></span>  
<span data-ttu-id="8e162-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="8e162-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="8e162-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="8e162-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e162-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e162-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e162-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8e162-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8e162-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e162-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e162-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="8e162-114">Attributes</span></span>  
  
|<span data-ttu-id="8e162-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="8e162-115">Attribute</span></span>|<span data-ttu-id="8e162-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e162-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e162-117">activityName</span><span class="sxs-lookup"><span data-stu-id="8e162-117">activityName</span></span>|<span data-ttu-id="8e162-118">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="8e162-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="8e162-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="8e162-119">childActivityName</span></span>|<span data-ttu-id="8e162-120">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="8e162-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e162-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e162-121">Child Elements</span></span>  
 <span data-ttu-id="8e162-122">Keine</span><span class="sxs-lookup"><span data-stu-id="8e162-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e162-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e162-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8e162-124">Element</span><span class="sxs-lookup"><span data-stu-id="8e162-124">Element</span></span>|<span data-ttu-id="8e162-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e162-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e162-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="8e162-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="8e162-127">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="8e162-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8e162-128">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="8e162-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e162-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e162-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8e162-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="8e162-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8e162-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="8e162-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
