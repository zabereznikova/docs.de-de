---
title: '&lt;activityStateQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 7b872d933d07af329601063b3d769bc43a22007c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568672"
---
# <a name="ltactivitystatequerygt"></a><span data-ttu-id="2cc0a-102">&lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="2cc0a-102">&lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="2cc0a-103">Stellt eine Abfrage dar, die verwendet wird, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="2cc0a-104">Beispielsweise empfiehlt es sich zum Nachverfolgen jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="2cc0a-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="2cc0a-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="2cc0a-107">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2cc0a-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="2cc0a-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2cc0a-108">\<system.serviceModel></span></span>  
<span data-ttu-id="2cc0a-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2cc0a-109">\<tracking></span></span>  
<span data-ttu-id="2cc0a-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2cc0a-110">\<trackingProfile></span></span>  
<span data-ttu-id="2cc0a-111">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2cc0a-111">\<workflow></span></span>  
<span data-ttu-id="2cc0a-112">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="2cc0a-112">\<activityStateQueries></span></span>  
<span data-ttu-id="2cc0a-113">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="2cc0a-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cc0a-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cc0a-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cc0a-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2cc0a-115">Attributes and Elements</span></span>  
 <span data-ttu-id="2cc0a-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cc0a-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="2cc0a-117">Attributes</span></span>  
  
|<span data-ttu-id="2cc0a-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="2cc0a-118">Attribute</span></span>|<span data-ttu-id="2cc0a-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cc0a-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2cc0a-120">activityName</span><span class="sxs-lookup"><span data-stu-id="2cc0a-120">activityName</span></span>|<span data-ttu-id="2cc0a-121">Eine Zeichenfolge, die den Namen der Aktivität angibt, für die <xref:System.Activities.Tracking.ActivityStateRecord>-Instanzen gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cc0a-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cc0a-122">Child Elements</span></span>  
  
|<span data-ttu-id="2cc0a-123">Element</span><span class="sxs-lookup"><span data-stu-id="2cc0a-123">Element</span></span>|<span data-ttu-id="2cc0a-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cc0a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cc0a-125">\<arguments></span><span class="sxs-lookup"><span data-stu-id="2cc0a-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="2cc0a-126">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="2cc0a-127">\<states></span><span class="sxs-lookup"><span data-stu-id="2cc0a-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2cc0a-128">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="2cc0a-129">\<states></span><span class="sxs-lookup"><span data-stu-id="2cc0a-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2cc0a-130">Eine Auflistung von Variablen, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cc0a-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cc0a-131">Parent Elements</span></span>  
  
|<span data-ttu-id="2cc0a-132">Element</span><span class="sxs-lookup"><span data-stu-id="2cc0a-132">Element</span></span>|<span data-ttu-id="2cc0a-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cc0a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cc0a-134">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="2cc0a-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="2cc0a-135">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="2cc0a-136">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cc0a-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cc0a-137">Remarks</span></span>  
 <span data-ttu-id="2cc0a-138">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="2cc0a-139">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="2cc0a-140">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="2cc0a-141">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2cc0a-141">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="2cc0a-142">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="2cc0a-142">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2cc0a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cc0a-143">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2cc0a-144">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="2cc0a-144">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2cc0a-145">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="2cc0a-145">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
