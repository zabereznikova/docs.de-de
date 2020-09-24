---
title: <activityScheduledQueries> von WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 86f196437b2230d6541570aa8994d99e7b340f66
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151193"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="c4236-102">\<activityScheduledQueries> von WCF</span><span class="sxs-lookup"><span data-stu-id="c4236-102">\<activityScheduledQueries> of WCF</span></span>

<span data-ttu-id="c4236-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="c4236-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="c4236-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="c4236-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="c4236-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="c4236-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="c4236-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4236-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4236-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c4236-107">Attributes and elements</span></span>  

<span data-ttu-id="c4236-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4236-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4236-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="c4236-109">Attributes</span></span>  

<span data-ttu-id="c4236-110">Keine</span><span class="sxs-lookup"><span data-stu-id="c4236-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c4236-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c4236-111">Child elements</span></span>  
  
|<span data-ttu-id="c4236-112">Element</span><span class="sxs-lookup"><span data-stu-id="c4236-112">Element</span></span>|<span data-ttu-id="c4236-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4236-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="c4236-114">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="c4236-114">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4236-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c4236-115">Parent elements</span></span>  
  
|<span data-ttu-id="c4236-116">Element</span><span class="sxs-lookup"><span data-stu-id="c4236-116">Element</span></span>|<span data-ttu-id="c4236-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4236-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="c4236-118">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="c4236-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4236-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4236-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="c4236-120">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c4236-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c4236-121">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="c4236-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
