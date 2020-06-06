---
title: <bookmarkResumptionQueries>von WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850129"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="e6225-102">\<bookmarkResumptionQueries>von WCF</span><span class="sxs-lookup"><span data-stu-id="e6225-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="e6225-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="e6225-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e6225-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="e6225-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="e6225-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e6225-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="e6225-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6225-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6225-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e6225-107">Attributes and elements</span></span>  
  
<span data-ttu-id="e6225-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6225-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6225-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e6225-109">Attributes</span></span>  
  
<span data-ttu-id="e6225-110">Keine</span><span class="sxs-lookup"><span data-stu-id="e6225-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6225-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6225-111">Child elements</span></span>  
  
|<span data-ttu-id="e6225-112">Element</span><span class="sxs-lookup"><span data-stu-id="e6225-112">Element</span></span>|<span data-ttu-id="e6225-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6225-113">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="e6225-114">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="e6225-114">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e6225-115">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="e6225-115">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6225-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6225-116">Parent elements</span></span>  
  
|<span data-ttu-id="e6225-117">Element</span><span class="sxs-lookup"><span data-stu-id="e6225-117">Element</span></span>|<span data-ttu-id="e6225-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6225-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="e6225-119">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="e6225-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6225-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6225-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e6225-121">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="e6225-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e6225-122">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="e6225-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
