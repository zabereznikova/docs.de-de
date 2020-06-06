---
title: <activityScheduledQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850465"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="e0d8c-102">\<activityScheduledQuery>von WCF</span><span class="sxs-lookup"><span data-stu-id="e0d8c-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="e0d8c-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="e0d8c-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="e0d8c-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="e0d8c-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="e0d8c-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="e0d8c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="e0d8c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0d8c-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0d8c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0d8c-107">Attributes and elements</span></span>  

<span data-ttu-id="e0d8c-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0d8c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0d8c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0d8c-109">Attributes</span></span>  
  
|<span data-ttu-id="e0d8c-110">attribute</span><span class="sxs-lookup"><span data-stu-id="e0d8c-110">Attribute</span></span>|<span data-ttu-id="e0d8c-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e0d8c-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="e0d8c-112">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="e0d8c-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="e0d8c-113">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="e0d8c-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0d8c-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0d8c-114">Child elements</span></span>

<span data-ttu-id="e0d8c-115">Keine</span><span class="sxs-lookup"><span data-stu-id="e0d8c-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="e0d8c-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0d8c-116">Parent elements</span></span>  
  
|<span data-ttu-id="e0d8c-117">Element</span><span class="sxs-lookup"><span data-stu-id="e0d8c-117">Element</span></span>|<span data-ttu-id="e0d8c-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0d8c-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQueries>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="e0d8c-119">Eine Auflistung von Abfragen, die verwendet werden, um eine Aktivität zu verfolgen, die für die Ausführung durch eine übergeordnete Aktivität geplant ist.</span><span class="sxs-lookup"><span data-stu-id="e0d8c-119">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0d8c-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0d8c-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="e0d8c-121">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="e0d8c-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e0d8c-122">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="e0d8c-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
