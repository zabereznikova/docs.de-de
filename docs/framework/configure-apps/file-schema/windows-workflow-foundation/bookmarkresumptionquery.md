---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: e43ba66e2c3ccfbb723b1eea8ef6774ad3f9f2aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140035"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="32b05-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="32b05-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="32b05-102">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="32b05-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="32b05-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="32b05-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="32b05-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="32b05-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="32b05-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="32b05-105">\<system.serviceModel></span></span>  
<span data-ttu-id="32b05-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="32b05-106">\<tracking></span></span>  
<span data-ttu-id="32b05-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="32b05-107">\<trackingProfile></span></span>  
<span data-ttu-id="32b05-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="32b05-108">\<workflow></span></span>  
<span data-ttu-id="32b05-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="32b05-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="32b05-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="32b05-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b05-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="32b05-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32b05-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="32b05-112">Attributes and Elements</span></span>  
 <span data-ttu-id="32b05-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32b05-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32b05-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="32b05-114">Attributes</span></span>  
  
|<span data-ttu-id="32b05-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="32b05-115">Attribute</span></span>|<span data-ttu-id="32b05-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32b05-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32b05-117">Name</span><span class="sxs-lookup"><span data-stu-id="32b05-117">name</span></span>|<span data-ttu-id="32b05-118">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="32b05-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32b05-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32b05-119">Child Elements</span></span>  
 <span data-ttu-id="32b05-120">Keine</span><span class="sxs-lookup"><span data-stu-id="32b05-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32b05-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32b05-121">Parent Elements</span></span>  
  
|<span data-ttu-id="32b05-122">Element</span><span class="sxs-lookup"><span data-stu-id="32b05-122">Element</span></span>|<span data-ttu-id="32b05-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32b05-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32b05-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="32b05-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="32b05-125">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="32b05-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32b05-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32b05-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="32b05-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="32b05-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="32b05-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="32b05-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
