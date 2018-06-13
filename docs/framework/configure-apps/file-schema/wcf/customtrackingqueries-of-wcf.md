---
title: '&lt;customTrackingQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 11ad4281d2925a48508c6a3e8258b0b1cd49a326
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749685"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="26de1-102">&lt;customTrackingQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="26de1-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="26de1-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="26de1-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="26de1-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="26de1-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="26de1-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="26de1-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="26de1-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="26de1-106">\<system.serviceModel></span></span>  
<span data-ttu-id="26de1-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="26de1-107">\<tracking></span></span>  
<span data-ttu-id="26de1-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="26de1-108">\<trackingProfile></span></span>  
<span data-ttu-id="26de1-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="26de1-109">\<workflow></span></span>  
<span data-ttu-id="26de1-110">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="26de1-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26de1-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="26de1-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26de1-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="26de1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="26de1-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="26de1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26de1-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="26de1-114">Attributes</span></span>  
 <span data-ttu-id="26de1-115">Keine</span><span class="sxs-lookup"><span data-stu-id="26de1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="26de1-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26de1-116">Child Elements</span></span>  
  
|<span data-ttu-id="26de1-117">Element</span><span class="sxs-lookup"><span data-stu-id="26de1-117">Element</span></span>|<span data-ttu-id="26de1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26de1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26de1-119">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="26de1-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="26de1-120">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="26de1-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26de1-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26de1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="26de1-122">Element</span><span class="sxs-lookup"><span data-stu-id="26de1-122">Element</span></span>|<span data-ttu-id="26de1-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26de1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26de1-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="26de1-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="26de1-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="26de1-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26de1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26de1-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="26de1-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="26de1-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="26de1-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="26de1-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
