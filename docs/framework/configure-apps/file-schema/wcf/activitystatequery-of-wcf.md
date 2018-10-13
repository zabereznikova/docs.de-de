---
title: '&lt;activityStateQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: a0dae6b90659bd3f53386459513abf92f25b005b
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2018
ms.locfileid: "49308312"
---
# <a name="ltactivitystatequerygt-of-wcf"></a><span data-ttu-id="a4994-102">&lt;activityStateQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="a4994-102">&lt;activityStateQuery&gt; of WCF</span></span>

<span data-ttu-id="a4994-103">Stellt eine Abfrage dar, die verwendet wird, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="a4994-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="a4994-104">Beispielsweise empfiehlt es sich zum Nachverfolgen jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="a4994-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="a4994-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a4994-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="a4994-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4994-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="a4994-107">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a4994-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="a4994-108">\<system.serviceModel > \<tracking ></span><span class="sxs-lookup"><span data-stu-id="a4994-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="a4994-109">\<Profile > \<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a4994-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="a4994-110">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a4994-110">\<workflow></span></span>  
<span data-ttu-id="a4994-111">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="a4994-111">\<activityStateQueries></span></span>  
<span data-ttu-id="a4994-112">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a4994-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4994-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4994-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4994-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a4994-114">Attributes and elements</span></span>  

<span data-ttu-id="a4994-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4994-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4994-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="a4994-116">Attributes</span></span>  
  
|<span data-ttu-id="a4994-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="a4994-117">Attribute</span></span>|<span data-ttu-id="a4994-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4994-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4994-119">activityName</span><span class="sxs-lookup"><span data-stu-id="a4994-119">activityName</span></span>|<span data-ttu-id="a4994-120">Eine Zeichenfolge, die den Namen der Aktivität angibt, für die <xref:System.Activities.Tracking.ActivityStateRecord>-Instanzen gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="a4994-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4994-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4994-121">Child elements</span></span>  
  
|<span data-ttu-id="a4994-122">Element</span><span class="sxs-lookup"><span data-stu-id="a4994-122">Element</span></span>|<span data-ttu-id="a4994-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4994-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4994-124">\<Argumente ></span><span class="sxs-lookup"><span data-stu-id="a4994-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="a4994-125">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="a4994-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="a4994-126">\<Status ></span><span class="sxs-lookup"><span data-stu-id="a4994-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="a4994-127">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4994-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="a4994-128">\<Status ></span><span class="sxs-lookup"><span data-stu-id="a4994-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="a4994-129">Eine Auflistung von Variablen, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a4994-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4994-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4994-130">Parent elements</span></span>  
  
|<span data-ttu-id="a4994-131">Element</span><span class="sxs-lookup"><span data-stu-id="a4994-131">Element</span></span>|<span data-ttu-id="a4994-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4994-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4994-133">\<FaultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="a4994-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="a4994-134">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a4994-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a4994-135">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a4994-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4994-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4994-136">Remarks</span></span>

<span data-ttu-id="a4994-137">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a4994-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a4994-138">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a4994-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a4994-139">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine aktivitätszustandsabfrage, die Variablen und Argumente extrahiert, wenn der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a4994-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a4994-140">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="a4994-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a4994-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4994-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="a4994-142">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a4994-142">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a4994-143">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a4994-143">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
