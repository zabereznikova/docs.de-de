---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152208"
---
# \<customTrackingQuery>
<span data-ttu-id="673b0-101">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="673b0-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="673b0-102">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="673b0-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="673b0-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="673b0-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="673b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="673b0-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="673b0-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="673b0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="673b0-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="673b0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="673b0-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="673b0-107">Attributes</span></span>  
  
|<span data-ttu-id="673b0-108">attribute</span><span class="sxs-lookup"><span data-stu-id="673b0-108">Attribute</span></span>|<span data-ttu-id="673b0-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="673b0-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="673b0-110">activityName</span><span class="sxs-lookup"><span data-stu-id="673b0-110">activityName</span></span>|<span data-ttu-id="673b0-111">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="673b0-111">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="673b0-112">name</span><span class="sxs-lookup"><span data-stu-id="673b0-112">name</span></span>|<span data-ttu-id="673b0-113">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="673b0-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="673b0-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="673b0-114">Child Elements</span></span>  
 <span data-ttu-id="673b0-115">Keine</span><span class="sxs-lookup"><span data-stu-id="673b0-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="673b0-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="673b0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="673b0-117">Element</span><span class="sxs-lookup"><span data-stu-id="673b0-117">Element</span></span>|<span data-ttu-id="673b0-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="673b0-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="673b0-119">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="673b0-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="673b0-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="673b0-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="673b0-121">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="673b0-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="673b0-122">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="673b0-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
