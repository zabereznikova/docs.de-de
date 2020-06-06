---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152260"
---
# \<customTrackingQueries>
<span data-ttu-id="1e89b-101">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="1e89b-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="1e89b-102">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="1e89b-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="1e89b-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="1e89b-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="1e89b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e89b-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e89b-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1e89b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1e89b-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e89b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e89b-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="1e89b-107">Attributes</span></span>  
 <span data-ttu-id="1e89b-108">Keine</span><span class="sxs-lookup"><span data-stu-id="1e89b-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1e89b-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e89b-109">Child Elements</span></span>  
  
|<span data-ttu-id="1e89b-110">Element</span><span class="sxs-lookup"><span data-stu-id="1e89b-110">Element</span></span>|<span data-ttu-id="1e89b-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e89b-111">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="1e89b-112">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="1e89b-112">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e89b-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e89b-113">Parent Elements</span></span>  
  
|<span data-ttu-id="1e89b-114">Element</span><span class="sxs-lookup"><span data-stu-id="1e89b-114">Element</span></span>|<span data-ttu-id="1e89b-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e89b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="1e89b-116">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="1e89b-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e89b-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e89b-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1e89b-118">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="1e89b-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1e89b-119">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="1e89b-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
