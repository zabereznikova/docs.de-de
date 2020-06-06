---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152286"
---
# \<cancelRequestedQuery>
<span data-ttu-id="8044e-101">Stellt eine Abfrage dar, die verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="8044e-101">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8044e-102">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="8044e-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="8044e-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8044e-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="8044e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8044e-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8044e-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8044e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8044e-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8044e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8044e-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="8044e-107">Attributes</span></span>  
  
|<span data-ttu-id="8044e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="8044e-108">Attribute</span></span>|<span data-ttu-id="8044e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8044e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8044e-110">activityName</span><span class="sxs-lookup"><span data-stu-id="8044e-110">activityName</span></span>|<span data-ttu-id="8044e-111">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="8044e-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="8044e-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="8044e-112">childActivityName</span></span>|<span data-ttu-id="8044e-113">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="8044e-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8044e-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8044e-114">Child Elements</span></span>  
 <span data-ttu-id="8044e-115">Keine</span><span class="sxs-lookup"><span data-stu-id="8044e-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8044e-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8044e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8044e-117">Element</span><span class="sxs-lookup"><span data-stu-id="8044e-117">Element</span></span>|<span data-ttu-id="8044e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8044e-118">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="8044e-119">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="8044e-119">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8044e-120">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="8044e-120">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8044e-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8044e-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8044e-122">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="8044e-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8044e-123">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="8044e-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
