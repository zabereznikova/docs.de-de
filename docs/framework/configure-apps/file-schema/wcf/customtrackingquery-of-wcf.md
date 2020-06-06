---
title: <customTrackingQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855417"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="b13b3-102">\<customTrackingQuery>von WCF</span><span class="sxs-lookup"><span data-stu-id="b13b3-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="b13b3-103">Stellt eine Abfrage dar, die verwendet wird, um Ereignisse zu verfolgen, die Sie in den Code Aktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="b13b3-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="b13b3-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="b13b3-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="b13b3-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="b13b3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="b13b3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b13b3-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b13b3-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b13b3-107">Attributes and elements</span></span>  

<span data-ttu-id="b13b3-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b13b3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b13b3-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="b13b3-109">Attributes</span></span>  
  
|<span data-ttu-id="b13b3-110">attribute</span><span class="sxs-lookup"><span data-stu-id="b13b3-110">Attribute</span></span>|<span data-ttu-id="b13b3-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b13b3-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="b13b3-112">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="b13b3-112">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="b13b3-113">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="b13b3-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b13b3-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b13b3-114">Child elements</span></span>

<span data-ttu-id="b13b3-115">Keine</span><span class="sxs-lookup"><span data-stu-id="b13b3-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b13b3-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b13b3-116">Parent elements</span></span>

|<span data-ttu-id="b13b3-117">Element</span><span class="sxs-lookup"><span data-stu-id="b13b3-117">Element</span></span>|<span data-ttu-id="b13b3-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b13b3-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQueries>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="b13b3-119">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="b13b3-119">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="b13b3-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b13b3-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b13b3-121">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b13b3-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b13b3-122">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="b13b3-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
