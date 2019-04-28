---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5f2e46d5e4cdd64c37219476790b9ff92c606b6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790233"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="3e1f3-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="3e1f3-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="3e1f3-102">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="3e1f3-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3e1f3-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3e1f3-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="3e1f3-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3e1f3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3e1f3-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3e1f3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3e1f3-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3e1f3-106">\<tracking></span></span>  
<span data-ttu-id="3e1f3-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3e1f3-107">\<trackingProfile></span></span>  
<span data-ttu-id="3e1f3-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3e1f3-108">\<workflow></span></span>  
<span data-ttu-id="3e1f3-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="3e1f3-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="3e1f3-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="3e1f3-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e1f3-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e1f3-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e1f3-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3e1f3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3e1f3-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3e1f3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e1f3-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3e1f3-114">Attributes</span></span>  
  
|<span data-ttu-id="3e1f3-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="3e1f3-115">Attribute</span></span>|<span data-ttu-id="3e1f3-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e1f3-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e1f3-117">activityName</span><span class="sxs-lookup"><span data-stu-id="3e1f3-117">activityName</span></span>|<span data-ttu-id="3e1f3-118">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="3e1f3-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="3e1f3-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="3e1f3-119">childActivityName</span></span>|<span data-ttu-id="3e1f3-120">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="3e1f3-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e1f3-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e1f3-121">Child Elements</span></span>  
 <span data-ttu-id="3e1f3-122">Keine</span><span class="sxs-lookup"><span data-stu-id="3e1f3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e1f3-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e1f3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3e1f3-124">Element</span><span class="sxs-lookup"><span data-stu-id="3e1f3-124">Element</span></span>|<span data-ttu-id="3e1f3-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e1f3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e1f3-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="3e1f3-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="3e1f3-127">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="3e1f3-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3e1f3-128">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3e1f3-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e1f3-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e1f3-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3e1f3-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3e1f3-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3e1f3-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3e1f3-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
