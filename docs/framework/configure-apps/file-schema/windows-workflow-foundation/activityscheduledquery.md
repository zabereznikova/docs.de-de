---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 207931f68303883c29161cc28a5fc1974d01b6b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148736"
---
# \<activityScheduledQuery>

<span data-ttu-id="eb839-101">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="eb839-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="eb839-102">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="eb839-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="eb839-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="eb839-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="eb839-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb839-104">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb839-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb839-105">Attributes and Elements</span></span>  

 <span data-ttu-id="eb839-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb839-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb839-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb839-107">Attributes</span></span>  
  
|<span data-ttu-id="eb839-108">attribute</span><span class="sxs-lookup"><span data-stu-id="eb839-108">Attribute</span></span>|<span data-ttu-id="eb839-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb839-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb839-110">activityName</span><span class="sxs-lookup"><span data-stu-id="eb839-110">activityName</span></span>|<span data-ttu-id="eb839-111">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="eb839-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="eb839-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="eb839-112">childActivityName</span></span>|<span data-ttu-id="eb839-113">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="eb839-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb839-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb839-114">Child Elements</span></span>  

 <span data-ttu-id="eb839-115">Keine</span><span class="sxs-lookup"><span data-stu-id="eb839-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb839-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb839-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eb839-117">Element</span><span class="sxs-lookup"><span data-stu-id="eb839-117">Element</span></span>|<span data-ttu-id="eb839-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb839-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="eb839-119">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="eb839-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb839-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb839-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="eb839-121">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="eb839-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eb839-122">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="eb839-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
