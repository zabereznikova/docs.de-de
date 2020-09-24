---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 59a76ea772dc8d06c390e3bca9d531df5f11e5f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148723"
---
# \<customTrackingQuery>

<span data-ttu-id="177bd-101">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="177bd-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="177bd-102">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="177bd-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="177bd-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="177bd-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="177bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="177bd-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="177bd-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="177bd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="177bd-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="177bd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="177bd-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="177bd-107">Attributes</span></span>  
  
|<span data-ttu-id="177bd-108">attribute</span><span class="sxs-lookup"><span data-stu-id="177bd-108">Attribute</span></span>|<span data-ttu-id="177bd-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="177bd-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="177bd-110">activityName</span><span class="sxs-lookup"><span data-stu-id="177bd-110">activityName</span></span>|<span data-ttu-id="177bd-111">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="177bd-111">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="177bd-112">name</span><span class="sxs-lookup"><span data-stu-id="177bd-112">name</span></span>|<span data-ttu-id="177bd-113">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="177bd-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="177bd-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="177bd-114">Child Elements</span></span>  

 <span data-ttu-id="177bd-115">Keine</span><span class="sxs-lookup"><span data-stu-id="177bd-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="177bd-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="177bd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="177bd-117">Element</span><span class="sxs-lookup"><span data-stu-id="177bd-117">Element</span></span>|<span data-ttu-id="177bd-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="177bd-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="177bd-119">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="177bd-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="177bd-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="177bd-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="177bd-121">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="177bd-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="177bd-122">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="177bd-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
