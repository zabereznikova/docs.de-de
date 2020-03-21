---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152208"
---
# <a name="customtrackingquery"></a><span data-ttu-id="6bdab-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="6bdab-101">\<customTrackingQuery></span></span>
<span data-ttu-id="6bdab-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="6bdab-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="6bdab-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="6bdab-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="6bdab-104">Weitere Informationen zum Nachverfolgen von Profilabfragen finden Sie unter [Nachverfolgungsprofile](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6bdab-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6bdab-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bdab-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6bdab-106">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6bdab-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="6bdab-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Tracking->**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="6bdab-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="6bdab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="6bdab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="6bdab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Workflow->**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6bdab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="6bdab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="6bdab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="6bdab-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span><span class="sxs-lookup"><span data-stu-id="6bdab-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bdab-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bdab-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bdab-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6bdab-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6bdab-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6bdab-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bdab-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="6bdab-115">Attributes</span></span>  
  
|<span data-ttu-id="6bdab-116">attribute</span><span class="sxs-lookup"><span data-stu-id="6bdab-116">Attribute</span></span>|<span data-ttu-id="6bdab-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bdab-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6bdab-118">activityName</span><span class="sxs-lookup"><span data-stu-id="6bdab-118">activityName</span></span>|<span data-ttu-id="6bdab-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="6bdab-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="6bdab-120">name</span><span class="sxs-lookup"><span data-stu-id="6bdab-120">name</span></span>|<span data-ttu-id="6bdab-121">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="6bdab-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bdab-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6bdab-122">Child Elements</span></span>  
 <span data-ttu-id="6bdab-123">Keine.</span><span class="sxs-lookup"><span data-stu-id="6bdab-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bdab-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6bdab-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6bdab-125">Element</span><span class="sxs-lookup"><span data-stu-id="6bdab-125">Element</span></span>|<span data-ttu-id="6bdab-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bdab-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bdab-127">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="6bdab-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="6bdab-128">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="6bdab-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bdab-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6bdab-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6bdab-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="6bdab-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6bdab-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="6bdab-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
