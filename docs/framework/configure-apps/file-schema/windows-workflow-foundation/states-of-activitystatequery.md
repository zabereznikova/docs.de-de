---
title: <states> von <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 0c8bf5b793684d3e6076114ce9eda7ffe1ef7a81
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398627"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="b34a5-102">\<states> von \<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b34a5-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="b34a5-103">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b34a5-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="b34a5-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b34a5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="b34a5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b34a5-105">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b34a5-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b34a5-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b34a5-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b34a5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b34a5-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b34a5-108">Attributes</span></span>  
 <span data-ttu-id="b34a5-109">Keine</span><span class="sxs-lookup"><span data-stu-id="b34a5-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b34a5-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b34a5-110">Child Elements</span></span>  
  
|<span data-ttu-id="b34a5-111">Element</span><span class="sxs-lookup"><span data-stu-id="b34a5-111">Element</span></span>|<span data-ttu-id="b34a5-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b34a5-112">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](state-of-states.md)|<span data-ttu-id="b34a5-113">Ein Konfigurationselement, das die Zustände der abonnierten Aktivität enthält, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b34a5-113">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b34a5-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b34a5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="b34a5-115">Element</span><span class="sxs-lookup"><span data-stu-id="b34a5-115">Element</span></span>|<span data-ttu-id="b34a5-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b34a5-116">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="b34a5-117">Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="b34a5-117">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b34a5-118">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="b34a5-118">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b34a5-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b34a5-119">Remarks</span></span>  
 <span data-ttu-id="b34a5-120">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="b34a5-120">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="b34a5-121">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="b34a5-121">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="b34a5-122">Sie können die [\<arguments>](arguments.md) Elemente, [\<states>](states.md) und verwenden [\<states>](states.md) , um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="b34a5-122">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="b34a5-123">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b34a5-123">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="b34a5-124">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mit abonniert werden [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="b34a5-124">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b34a5-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b34a5-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b34a5-126">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b34a5-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b34a5-127">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="b34a5-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
