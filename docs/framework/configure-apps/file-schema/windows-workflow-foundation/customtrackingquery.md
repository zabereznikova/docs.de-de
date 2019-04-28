---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 92060260075017359d8a5f0500d52e52c2217d3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790181"
---
# <a name="customtrackingquery"></a><span data-ttu-id="a092c-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="a092c-101">\<customTrackingQuery></span></span>
<span data-ttu-id="a092c-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="a092c-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="a092c-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a092c-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="a092c-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a092c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a092c-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a092c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a092c-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a092c-106">\<tracking></span></span>  
<span data-ttu-id="a092c-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a092c-107">\<trackingProfile></span></span>  
<span data-ttu-id="a092c-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a092c-108">\<workflow></span></span>  
<span data-ttu-id="a092c-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="a092c-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="a092c-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="a092c-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a092c-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a092c-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a092c-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a092c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a092c-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a092c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a092c-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a092c-114">Attributes</span></span>  
  
|<span data-ttu-id="a092c-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="a092c-115">Attribute</span></span>|<span data-ttu-id="a092c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a092c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a092c-117">activityName</span><span class="sxs-lookup"><span data-stu-id="a092c-117">activityName</span></span>|<span data-ttu-id="a092c-118">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="a092c-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="a092c-119">Name</span><span class="sxs-lookup"><span data-stu-id="a092c-119">name</span></span>|<span data-ttu-id="a092c-120">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="a092c-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a092c-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a092c-121">Child Elements</span></span>  
 <span data-ttu-id="a092c-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a092c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a092c-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a092c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a092c-124">Element</span><span class="sxs-lookup"><span data-stu-id="a092c-124">Element</span></span>|<span data-ttu-id="a092c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a092c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a092c-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="a092c-126">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="a092c-127">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="a092c-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a092c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a092c-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a092c-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a092c-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a092c-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a092c-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
