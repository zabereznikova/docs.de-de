---
title: <customTrackingQueries>von WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855435"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="f568c-102">\<customTrackingQueries>von WCF</span><span class="sxs-lookup"><span data-stu-id="f568c-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="f568c-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="f568c-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f568c-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="f568c-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="f568c-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f568c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  

## <a name="syntax"></a><span data-ttu-id="f568c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f568c-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f568c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f568c-107">Attributes and elements</span></span>

<span data-ttu-id="f568c-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f568c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f568c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f568c-109">Attributes</span></span>

<span data-ttu-id="f568c-110">Keine</span><span class="sxs-lookup"><span data-stu-id="f568c-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f568c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f568c-111">Child elements</span></span>
  
|<span data-ttu-id="f568c-112">Element</span><span class="sxs-lookup"><span data-stu-id="f568c-112">Element</span></span>|<span data-ttu-id="f568c-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f568c-113">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery-of-wcf.md)|<span data-ttu-id="f568c-114">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="f568c-114">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f568c-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f568c-115">Parent elements</span></span>  
  
|<span data-ttu-id="f568c-116">Element</span><span class="sxs-lookup"><span data-stu-id="f568c-116">Element</span></span>|<span data-ttu-id="f568c-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f568c-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="f568c-118">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="f568c-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f568c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f568c-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f568c-120">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="f568c-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f568c-121">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="f568c-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
