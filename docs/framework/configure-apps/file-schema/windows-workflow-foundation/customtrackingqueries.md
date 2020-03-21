---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152260"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="75389-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="75389-101">\<customTrackingQueries></span></span>
<span data-ttu-id="75389-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="75389-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="75389-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="75389-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="75389-104">Weitere Informationen zum Nachverfolgen von Profilabfragen finden Sie unter [Nachverfolgungsprofile](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="75389-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="75389-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="75389-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="75389-106">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="75389-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="75389-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Tracking->**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="75389-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="75389-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="75389-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="75389-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Workflow->**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="75389-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="75389-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span><span class="sxs-lookup"><span data-stu-id="75389-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75389-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="75389-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75389-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="75389-112">Attributes and Elements</span></span>  
 <span data-ttu-id="75389-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75389-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75389-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="75389-114">Attributes</span></span>  
 <span data-ttu-id="75389-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="75389-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75389-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75389-116">Child Elements</span></span>  
  
|<span data-ttu-id="75389-117">Element</span><span class="sxs-lookup"><span data-stu-id="75389-117">Element</span></span>|<span data-ttu-id="75389-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75389-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75389-119">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="75389-119">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="75389-120">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="75389-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75389-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75389-121">Parent Elements</span></span>  
  
|<span data-ttu-id="75389-122">Element</span><span class="sxs-lookup"><span data-stu-id="75389-122">Element</span></span>|<span data-ttu-id="75389-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75389-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75389-124">\<Workflow-></span><span class="sxs-lookup"><span data-stu-id="75389-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="75389-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId-Eigenschaft** identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="75389-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75389-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75389-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="75389-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="75389-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="75389-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="75389-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
