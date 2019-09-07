---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 695fccf88ac0d8a672e710ccc632ea58dd2fc693
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398769"
---
# <a name="customtrackingquery"></a><span data-ttu-id="9efbe-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="9efbe-101">\<customTrackingQuery></span></span>
<span data-ttu-id="9efbe-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="9efbe-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="9efbe-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="9efbe-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="9efbe-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="9efbe-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9efbe-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9efbe-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9efbe-106">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9efbe-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9efbe-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="9efbe-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="9efbe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="9efbe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="9efbe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9efbe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="9efbe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customtrackingqueries->** ](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="9efbe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="9efbe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<CustomTrackingQuery->**</span><span class="sxs-lookup"><span data-stu-id="9efbe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9efbe-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="9efbe-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9efbe-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9efbe-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9efbe-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9efbe-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9efbe-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="9efbe-115">Attributes</span></span>  
  
|<span data-ttu-id="9efbe-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="9efbe-116">Attribute</span></span>|<span data-ttu-id="9efbe-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9efbe-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9efbe-118">activityName</span><span class="sxs-lookup"><span data-stu-id="9efbe-118">activityName</span></span>|<span data-ttu-id="9efbe-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="9efbe-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="9efbe-120">Name</span><span class="sxs-lookup"><span data-stu-id="9efbe-120">name</span></span>|<span data-ttu-id="9efbe-121">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="9efbe-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9efbe-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9efbe-122">Child Elements</span></span>  
 <span data-ttu-id="9efbe-123">Keine</span><span class="sxs-lookup"><span data-stu-id="9efbe-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9efbe-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9efbe-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9efbe-125">Element</span><span class="sxs-lookup"><span data-stu-id="9efbe-125">Element</span></span>|<span data-ttu-id="9efbe-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9efbe-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9efbe-127">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="9efbe-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="9efbe-128">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="9efbe-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9efbe-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9efbe-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9efbe-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="9efbe-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9efbe-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="9efbe-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
