---
title: <activityStateQuery>von WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: ce7505896b9c5bb605bb0f67d735cb324f4fd493
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926900"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="c1535-102">\<activitystatus equery-> von WCF</span><span class="sxs-lookup"><span data-stu-id="c1535-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="c1535-103">Stellt eine Abfrage dar, die verwendet wird, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="c1535-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="c1535-104">Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c1535-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="c1535-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="c1535-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="c1535-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="c1535-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="c1535-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c1535-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="c1535-108">\<System. Service Model > \<nach Verfolgungs ></span><span class="sxs-lookup"><span data-stu-id="c1535-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="c1535-109">\<Profile > \<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c1535-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="c1535-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c1535-110">\<workflow></span></span>  
<span data-ttu-id="c1535-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="c1535-111">\<activityStateQueries></span></span>  
<span data-ttu-id="c1535-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="c1535-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1535-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1535-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1535-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1535-114">Attributes and elements</span></span>  

<span data-ttu-id="c1535-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1535-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1535-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1535-116">Attributes</span></span>  
  
|<span data-ttu-id="c1535-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="c1535-117">Attribute</span></span>|<span data-ttu-id="c1535-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1535-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1535-119">activityName</span><span class="sxs-lookup"><span data-stu-id="c1535-119">activityName</span></span>|<span data-ttu-id="c1535-120">Eine Zeichenfolge, die den Namen der Aktivität angibt, für die <xref:System.Activities.Tracking.ActivityStateRecord>-Instanzen gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="c1535-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1535-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1535-121">Child elements</span></span>  
  
|<span data-ttu-id="c1535-122">Element</span><span class="sxs-lookup"><span data-stu-id="c1535-122">Element</span></span>|<span data-ttu-id="c1535-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1535-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1535-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="c1535-124">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="c1535-125">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="c1535-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="c1535-126">\<Status ></span><span class="sxs-lookup"><span data-stu-id="c1535-126">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="c1535-127">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="c1535-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="c1535-128">\<Status ></span><span class="sxs-lookup"><span data-stu-id="c1535-128">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="c1535-129">Eine Auflistung von Variablen, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c1535-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1535-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1535-130">Parent elements</span></span>  
  
|<span data-ttu-id="c1535-131">Element</span><span class="sxs-lookup"><span data-stu-id="c1535-131">Element</span></span>|<span data-ttu-id="c1535-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1535-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1535-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c1535-133">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="c1535-134">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="c1535-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c1535-135">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="c1535-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1535-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1535-136">Remarks</span></span>

<span data-ttu-id="c1535-137">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="c1535-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="c1535-138">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="c1535-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="c1535-139">Sie können die [ \<Argumente >](../windows-workflow-foundation/arguments.md), [ \<Zustände >](../windows-workflow-foundation/states.md) und [ \<Zustände >](../windows-workflow-foundation/states.md) Elemente verwenden, um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren. Das folgende Beispiel zeigt eine Aktivitäts Zustands Abfrage, die Variablen und Argumente extrahiert, wenn der `Closed` nach Verfolgungs Daten Satz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c1535-139">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="c1535-140">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mithilfe [ \<von activitystatuequery >](../windows-workflow-foundation/activitystatequery.md)abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="c1535-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="c1535-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1535-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="c1535-142">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c1535-142">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c1535-143">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="c1535-143">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
