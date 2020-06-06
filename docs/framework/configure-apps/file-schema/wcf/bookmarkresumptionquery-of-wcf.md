---
title: <bookmarkResumptionQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 8cb254599a9742305ec958fd77174f4c4b8a57c2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834007"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="756cf-102">\<bookmarkResumptionQuery>von WCF</span><span class="sxs-lookup"><span data-stu-id="756cf-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="756cf-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="756cf-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="756cf-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="756cf-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="756cf-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="756cf-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="756cf-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="756cf-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="756cf-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="756cf-107">Attributes and elements</span></span>

<span data-ttu-id="756cf-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="756cf-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="756cf-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="756cf-109">Attributes</span></span>  
  
|<span data-ttu-id="756cf-110">attribute</span><span class="sxs-lookup"><span data-stu-id="756cf-110">Attribute</span></span>|<span data-ttu-id="756cf-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="756cf-111">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="756cf-112">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="756cf-112">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="756cf-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="756cf-113">Child elements</span></span>

<span data-ttu-id="756cf-114">Keine</span><span class="sxs-lookup"><span data-stu-id="756cf-114">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="756cf-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="756cf-115">Parent elements</span></span>  
  
|<span data-ttu-id="756cf-116">Element</span><span class="sxs-lookup"><span data-stu-id="756cf-116">Element</span></span>|<span data-ttu-id="756cf-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="756cf-117">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="756cf-118">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="756cf-118">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="756cf-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="756cf-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="756cf-120">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="756cf-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="756cf-121">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="756cf-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
