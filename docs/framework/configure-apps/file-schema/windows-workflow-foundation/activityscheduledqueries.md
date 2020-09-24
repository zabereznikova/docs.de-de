---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 936267f7d61dfd09af45ddb96b4406c92c30b3b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148775"
---
# \<activityScheduledQueries>

<span data-ttu-id="14b1f-101">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="14b1f-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="14b1f-102">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="14b1f-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="14b1f-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="14b1f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="14b1f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14b1f-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14b1f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14b1f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="14b1f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14b1f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14b1f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="14b1f-107">Attributes</span></span>  

 <span data-ttu-id="14b1f-108">Keine</span><span class="sxs-lookup"><span data-stu-id="14b1f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14b1f-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14b1f-109">Child Elements</span></span>  
  
|<span data-ttu-id="14b1f-110">Element</span><span class="sxs-lookup"><span data-stu-id="14b1f-110">Element</span></span>|<span data-ttu-id="14b1f-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14b1f-111">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="14b1f-112">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="14b1f-112">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14b1f-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14b1f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="14b1f-114">Element</span><span class="sxs-lookup"><span data-stu-id="14b1f-114">Element</span></span>|<span data-ttu-id="14b1f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14b1f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="14b1f-116">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="14b1f-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14b1f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14b1f-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="14b1f-118">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="14b1f-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="14b1f-119">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="14b1f-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
