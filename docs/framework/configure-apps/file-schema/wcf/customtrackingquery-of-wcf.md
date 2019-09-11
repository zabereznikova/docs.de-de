---
title: <customTrackingQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855417"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="edef2-102">\<CustomTrackingQuery-> von WCF</span><span class="sxs-lookup"><span data-stu-id="edef2-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="edef2-103">Stellt eine Abfrage dar, die verwendet wird, um Ereignisse zu verfolgen, die Sie in den Code Aktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="edef2-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="edef2-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="edef2-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="edef2-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="edef2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="edef2-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="edef2-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="edef2-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="edef2-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="edef2-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="edef2-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="edef2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="edef2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="edef2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="edef2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="edef2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="edef2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="edef2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customtrackingqueries->** ](customtrackingqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="edef2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)</span></span>\
<span data-ttu-id="edef2-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<CustomTrackingQuery->**</span><span class="sxs-lookup"><span data-stu-id="edef2-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edef2-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="edef2-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edef2-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="edef2-115">Attributes and elements</span></span>  

<span data-ttu-id="edef2-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="edef2-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edef2-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="edef2-117">Attributes</span></span>  
  
|<span data-ttu-id="edef2-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="edef2-118">Attribute</span></span>|<span data-ttu-id="edef2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edef2-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="edef2-120">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="edef2-120">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="edef2-121">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="edef2-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edef2-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edef2-122">Child elements</span></span>

<span data-ttu-id="edef2-123">Keine</span><span class="sxs-lookup"><span data-stu-id="edef2-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="edef2-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edef2-124">Parent elements</span></span>

|<span data-ttu-id="edef2-125">Element</span><span class="sxs-lookup"><span data-stu-id="edef2-125">Element</span></span>|<span data-ttu-id="edef2-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edef2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edef2-127">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="edef2-127">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="edef2-128">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="edef2-128">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="edef2-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edef2-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="edef2-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="edef2-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="edef2-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="edef2-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
