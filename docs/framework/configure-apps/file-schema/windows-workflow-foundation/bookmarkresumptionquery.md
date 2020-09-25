---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: efd1e4e54223ff9f5d60b4087fbe5b6bebf1af2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189589"
---
# \<bookmarkResumptionQuery>

<span data-ttu-id="d95df-101">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="d95df-101">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d95df-102">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="d95df-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="d95df-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="d95df-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="d95df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d95df-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d95df-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d95df-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d95df-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d95df-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d95df-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d95df-107">Attributes</span></span>  
  
|<span data-ttu-id="d95df-108">attribute</span><span class="sxs-lookup"><span data-stu-id="d95df-108">Attribute</span></span>|<span data-ttu-id="d95df-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d95df-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d95df-110">name</span><span class="sxs-lookup"><span data-stu-id="d95df-110">name</span></span>|<span data-ttu-id="d95df-111">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="d95df-111">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d95df-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d95df-112">Child Elements</span></span>  

 <span data-ttu-id="d95df-113">Keine</span><span class="sxs-lookup"><span data-stu-id="d95df-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d95df-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d95df-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d95df-115">Element</span><span class="sxs-lookup"><span data-stu-id="d95df-115">Element</span></span>|<span data-ttu-id="d95df-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d95df-116">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="d95df-117">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="d95df-117">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d95df-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d95df-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d95df-119">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d95df-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d95df-120">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d95df-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
