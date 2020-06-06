---
title: <cancelRequestedQueries>von WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850099"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="ef10c-102">\<cancelRequestedQueries>von WCF</span><span class="sxs-lookup"><span data-stu-id="ef10c-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="ef10c-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="ef10c-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ef10c-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ef10c-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="ef10c-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="ef10c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="ef10c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef10c-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef10c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ef10c-107">Attributes and elements</span></span>  

<span data-ttu-id="ef10c-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef10c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef10c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="ef10c-109">Attributes</span></span>

<span data-ttu-id="ef10c-110">Keine</span><span class="sxs-lookup"><span data-stu-id="ef10c-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="ef10c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef10c-111">Child elements</span></span>
  
|<span data-ttu-id="ef10c-112">Element</span><span class="sxs-lookup"><span data-stu-id="ef10c-112">Element</span></span>|<span data-ttu-id="ef10c-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ef10c-113">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="ef10c-114">Eine Abfrage, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="ef10c-114">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef10c-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef10c-115">Parent elements</span></span>  
  
|<span data-ttu-id="ef10c-116">Element</span><span class="sxs-lookup"><span data-stu-id="ef10c-116">Element</span></span>|<span data-ttu-id="ef10c-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ef10c-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="ef10c-118">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="ef10c-118">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef10c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef10c-119">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="ef10c-120">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ef10c-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ef10c-121">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ef10c-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
