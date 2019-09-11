---
title: <cancelRequestedQueries>von WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850099"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="836a5-102">\<cancelrequestedqueries-> von WCF</span><span class="sxs-lookup"><span data-stu-id="836a5-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="836a5-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="836a5-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="836a5-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="836a5-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="836a5-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="836a5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="836a5-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="836a5-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="836a5-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="836a5-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="836a5-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="836a5-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="836a5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="836a5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="836a5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="836a5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="836a5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="836a5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="836a5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cancelrequestedqueries->**</span><span class="sxs-lookup"><span data-stu-id="836a5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="836a5-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="836a5-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="836a5-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="836a5-114">Attributes and elements</span></span>  

<span data-ttu-id="836a5-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="836a5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="836a5-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="836a5-116">Attributes</span></span>

<span data-ttu-id="836a5-117">Keine</span><span class="sxs-lookup"><span data-stu-id="836a5-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="836a5-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="836a5-118">Child elements</span></span>
  
|<span data-ttu-id="836a5-119">Element</span><span class="sxs-lookup"><span data-stu-id="836a5-119">Element</span></span>|<span data-ttu-id="836a5-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="836a5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="836a5-121">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="836a5-121">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="836a5-122">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="836a5-122">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="836a5-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="836a5-123">Parent elements</span></span>  
  
|<span data-ttu-id="836a5-124">Element</span><span class="sxs-lookup"><span data-stu-id="836a5-124">Element</span></span>|<span data-ttu-id="836a5-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="836a5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="836a5-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="836a5-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="836a5-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="836a5-127">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="836a5-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="836a5-128">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="836a5-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="836a5-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="836a5-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="836a5-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
