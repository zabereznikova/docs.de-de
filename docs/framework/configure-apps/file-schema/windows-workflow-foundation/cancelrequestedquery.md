---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152286"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="f7223-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="f7223-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="f7223-102">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="f7223-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f7223-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="f7223-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="f7223-104">Weitere Informationen zum Nachverfolgen von Profilabfragen finden Sie unter [Nachverfolgung von Profilen](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f7223-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f7223-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7223-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7223-106">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f7223-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="f7223-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Tracking->**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="f7223-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="f7223-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="f7223-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="f7223-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Workflow->**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f7223-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="f7223-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="f7223-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="f7223-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span><span class="sxs-lookup"><span data-stu-id="f7223-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7223-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7223-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7223-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f7223-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f7223-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7223-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7223-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="f7223-115">Attributes</span></span>  
  
|<span data-ttu-id="f7223-116">attribute</span><span class="sxs-lookup"><span data-stu-id="f7223-116">Attribute</span></span>|<span data-ttu-id="f7223-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7223-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7223-118">activityName</span><span class="sxs-lookup"><span data-stu-id="f7223-118">activityName</span></span>|<span data-ttu-id="f7223-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="f7223-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="f7223-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="f7223-120">childActivityName</span></span>|<span data-ttu-id="f7223-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="f7223-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7223-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7223-122">Child Elements</span></span>  
 <span data-ttu-id="f7223-123">Keine.</span><span class="sxs-lookup"><span data-stu-id="f7223-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7223-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7223-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f7223-125">Element</span><span class="sxs-lookup"><span data-stu-id="f7223-125">Element</span></span>|<span data-ttu-id="f7223-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7223-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7223-127">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="f7223-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="f7223-128">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="f7223-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f7223-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="f7223-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7223-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7223-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f7223-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="f7223-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f7223-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="f7223-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
