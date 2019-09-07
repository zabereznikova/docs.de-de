---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 3e48256ab1127d45e95c557aa9c2434419d9ea59
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397595"
---
# <a name="variables"></a><span data-ttu-id="8dc3b-101">\<Variablen ></span><span class="sxs-lookup"><span data-stu-id="8dc3b-101">\<variables></span></span>
<span data-ttu-id="8dc3b-102">Stellt eine Auflistung von Variablen dar, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="8dc3b-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8dc3b-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8dc3b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8dc3b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8dc3b-105">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8dc3b-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="8dc3b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="8dc3b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="8dc3b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="8dc3b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="8dc3b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8dc3b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="8dc3b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activitystatuequeries->** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="8dc3b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="8dc3b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activitystatus equery->** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="8dc3b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="8dc3b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Variablen >**</span><span class="sxs-lookup"><span data-stu-id="8dc3b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variables>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc3b-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="8dc3b-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8dc3b-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8dc3b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8dc3b-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8dc3b-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="8dc3b-115">Attributes</span></span>  
 <span data-ttu-id="8dc3b-116">Keine</span><span class="sxs-lookup"><span data-stu-id="8dc3b-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8dc3b-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8dc3b-117">Child Elements</span></span>  
  
|<span data-ttu-id="8dc3b-118">Element</span><span class="sxs-lookup"><span data-stu-id="8dc3b-118">Element</span></span>|<span data-ttu-id="8dc3b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dc3b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8dc3b-120">\<variable></span><span class="sxs-lookup"><span data-stu-id="8dc3b-120">\<variable></span></span>](variable.md)|<span data-ttu-id="8dc3b-121">Eine einer Aktivitätszustandsabfrage zugeordnete Variable.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8dc3b-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8dc3b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8dc3b-123">Element</span><span class="sxs-lookup"><span data-stu-id="8dc3b-123">Element</span></span>|<span data-ttu-id="8dc3b-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dc3b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8dc3b-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="8dc3b-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="8dc3b-126">Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8dc3b-127">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dc3b-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8dc3b-128">Remarks</span></span>  
 <span data-ttu-id="8dc3b-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="8dc3b-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="8dc3b-131">Sie können die [ \<Argumente >](arguments.md), [ \<Zustände >](states.md) und [ \<Zustände >](states.md) Elemente verwenden, um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="8dc3b-132">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="8dc3b-133">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mithilfe [ \<von activitystatuequery >](activitystatequery.md)abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="8dc3b-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8dc3b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8dc3b-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8dc3b-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="8dc3b-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8dc3b-136">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="8dc3b-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
