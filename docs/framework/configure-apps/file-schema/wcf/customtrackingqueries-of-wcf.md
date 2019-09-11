---
title: <customTrackingQueries>von WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855435"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="aab85-102">\<customtrackingqueries-> von WCF</span><span class="sxs-lookup"><span data-stu-id="aab85-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="aab85-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="aab85-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="aab85-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="aab85-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="aab85-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="aab85-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="aab85-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aab85-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aab85-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aab85-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aab85-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aab85-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="aab85-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="aab85-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="aab85-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aab85-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="aab85-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aab85-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="aab85-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customtrackingqueries->**</span><span class="sxs-lookup"><span data-stu-id="aab85-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="aab85-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="aab85-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aab85-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aab85-114">Attributes and elements</span></span>

<span data-ttu-id="aab85-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aab85-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aab85-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="aab85-116">Attributes</span></span>

<span data-ttu-id="aab85-117">Keine</span><span class="sxs-lookup"><span data-stu-id="aab85-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="aab85-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aab85-118">Child elements</span></span>
  
|<span data-ttu-id="aab85-119">Element</span><span class="sxs-lookup"><span data-stu-id="aab85-119">Element</span></span>|<span data-ttu-id="aab85-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aab85-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aab85-121">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="aab85-121">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="aab85-122">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="aab85-122">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aab85-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aab85-123">Parent elements</span></span>  
  
|<span data-ttu-id="aab85-124">Element</span><span class="sxs-lookup"><span data-stu-id="aab85-124">Element</span></span>|<span data-ttu-id="aab85-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aab85-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aab85-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="aab85-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="aab85-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="aab85-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aab85-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aab85-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="aab85-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="aab85-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aab85-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="aab85-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
