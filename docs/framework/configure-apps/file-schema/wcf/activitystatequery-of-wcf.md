---
title: '&lt;activityStateQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 6d837946808e0d78e98c9c3010d4690fdfac6fa4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754583"
---
# <a name="ltactivitystatequerygt-of-wcf"></a><span data-ttu-id="76caa-102">&lt;activityStateQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="76caa-102">&lt;activityStateQuery&gt; of WCF</span></span>
<span data-ttu-id="76caa-103">Stellt eine Abfrage dar, die verwendet wird, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="76caa-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="76caa-104">Beispielsweise empfiehlt es sich zum Nachverfolgen von jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="76caa-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="76caa-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="76caa-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="76caa-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="76caa-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="76caa-107">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="76caa-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="76caa-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="76caa-108">\<system.serviceModel></span></span>  
<span data-ttu-id="76caa-109">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="76caa-109">\<tracking></span></span>  
<span data-ttu-id="76caa-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="76caa-110">\<trackingProfile></span></span>  
<span data-ttu-id="76caa-111">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="76caa-111">\<workflow></span></span>  
<span data-ttu-id="76caa-112">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="76caa-112">\<activityStateQueries></span></span>  
<span data-ttu-id="76caa-113">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="76caa-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76caa-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="76caa-114">Syntax</span></span>  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76caa-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="76caa-115">Attributes and Elements</span></span>  
 <span data-ttu-id="76caa-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76caa-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76caa-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="76caa-117">Attributes</span></span>  
  
|<span data-ttu-id="76caa-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="76caa-118">Attribute</span></span>|<span data-ttu-id="76caa-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76caa-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76caa-120">activityName</span><span class="sxs-lookup"><span data-stu-id="76caa-120">activityName</span></span>|<span data-ttu-id="76caa-121">Eine Zeichenfolge, die den Namen der Aktivität angibt, für die <xref:System.Activities.Tracking.ActivityStateRecord>-Instanzen gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="76caa-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76caa-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="76caa-122">Child Elements</span></span>  
  
|<span data-ttu-id="76caa-123">Element</span><span class="sxs-lookup"><span data-stu-id="76caa-123">Element</span></span>|<span data-ttu-id="76caa-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76caa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76caa-125">\<Argumente ></span><span class="sxs-lookup"><span data-stu-id="76caa-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="76caa-126">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="76caa-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="76caa-127">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="76caa-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="76caa-128">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="76caa-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="76caa-129">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="76caa-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="76caa-130">Eine Auflistung von Variablen, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="76caa-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76caa-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="76caa-131">Parent Elements</span></span>  
  
|<span data-ttu-id="76caa-132">Element</span><span class="sxs-lookup"><span data-stu-id="76caa-132">Element</span></span>|<span data-ttu-id="76caa-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76caa-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76caa-134">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="76caa-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="76caa-135">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="76caa-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="76caa-136">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="76caa-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76caa-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76caa-137">Remarks</span></span>  
 <span data-ttu-id="76caa-138">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="76caa-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="76caa-139">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="76caa-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="76caa-140">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="76caa-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="76caa-141">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="76caa-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76caa-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76caa-142">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>    
 <xref:System.Activities.Tracking.ActivityStateQuery>     
 [<span data-ttu-id="76caa-143">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="76caa-143">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="76caa-144">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="76caa-144">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
