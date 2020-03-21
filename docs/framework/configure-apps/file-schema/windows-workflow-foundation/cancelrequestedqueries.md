---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 89297b3a7d64f4300a735d8512230d441836c634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152306"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="c7d8b-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="c7d8b-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="c7d8b-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="c7d8b-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c7d8b-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="c7d8b-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="c7d8b-104">Weitere Informationen zum Nachverfolgen von Profilabfragen finden Sie unter [Nachverfolgungsprofile](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c7d8b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c7d8b-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7d8b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c7d8b-106">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c7d8b-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="c7d8b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Tracking->**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="c7d8b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="c7d8b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="c7d8b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="c7d8b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Workflow->**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c7d8b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="c7d8b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span><span class="sxs-lookup"><span data-stu-id="c7d8b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d8b-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7d8b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7d8b-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c7d8b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c7d8b-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7d8b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7d8b-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="c7d8b-114">Attributes</span></span>  
 <span data-ttu-id="c7d8b-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="c7d8b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c7d8b-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7d8b-116">Child Elements</span></span>  
  
|<span data-ttu-id="c7d8b-117">Element</span><span class="sxs-lookup"><span data-stu-id="c7d8b-117">Element</span></span>|<span data-ttu-id="c7d8b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7d8b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7d8b-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="c7d8b-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="c7d8b-120">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="c7d8b-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7d8b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7d8b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c7d8b-122">Element</span><span class="sxs-lookup"><span data-stu-id="c7d8b-122">Element</span></span>|<span data-ttu-id="c7d8b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7d8b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7d8b-124">\<Workflow-></span><span class="sxs-lookup"><span data-stu-id="c7d8b-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="c7d8b-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId-Eigenschaft** identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="c7d8b-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7d8b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7d8b-126">See also</span></span>

- [<span data-ttu-id="c7d8b-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c7d8b-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c7d8b-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="c7d8b-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
