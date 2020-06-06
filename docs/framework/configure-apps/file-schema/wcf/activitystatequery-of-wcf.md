---
title: <activityStateQuery>von WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 49c507424e813067e1dad9b08167d9661acef36f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70991217"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="58751-102">\<activityStateQuery>von WCF</span><span class="sxs-lookup"><span data-stu-id="58751-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="58751-103">Stellt eine Abfrage dar, die verwendet wird, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="58751-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="58751-104">Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="58751-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="58751-105">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="58751-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="58751-106">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="58751-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="58751-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="58751-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="58751-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="58751-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58751-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="58751-109">Attributes and elements</span></span>  

<span data-ttu-id="58751-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58751-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58751-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="58751-111">Attributes</span></span>  
  
|<span data-ttu-id="58751-112">attribute</span><span class="sxs-lookup"><span data-stu-id="58751-112">Attribute</span></span>|<span data-ttu-id="58751-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="58751-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58751-114">activityName</span><span class="sxs-lookup"><span data-stu-id="58751-114">activityName</span></span>|<span data-ttu-id="58751-115">Eine Zeichenfolge, die den Namen der Aktivität angibt, für die <xref:System.Activities.Tracking.ActivityStateRecord>-Instanzen gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="58751-115">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58751-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58751-116">Child elements</span></span>  
  
|<span data-ttu-id="58751-117">Element</span><span class="sxs-lookup"><span data-stu-id="58751-117">Element</span></span>|<span data-ttu-id="58751-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58751-118">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="58751-119">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="58751-119">A collection of arguments associated with this activity query.</span></span>|  
|[\<states>](../windows-workflow-foundation/states.md)|<span data-ttu-id="58751-120">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="58751-120">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[\<states>](../windows-workflow-foundation/states.md)|<span data-ttu-id="58751-121">Eine Auflistung von Variablen, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="58751-121">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58751-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58751-122">Parent elements</span></span>  
  
|<span data-ttu-id="58751-123">Element</span><span class="sxs-lookup"><span data-stu-id="58751-123">Element</span></span>|<span data-ttu-id="58751-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58751-124">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="58751-125">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="58751-125">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="58751-126">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="58751-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58751-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="58751-127">Remarks</span></span>

<span data-ttu-id="58751-128">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="58751-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="58751-129">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="58751-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="58751-130">Sie können die [\<arguments>](../windows-workflow-foundation/arguments.md) Elemente, [\<states>](../windows-workflow-foundation/states.md) und verwenden [\<states>](../windows-workflow-foundation/states.md) , um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="58751-130">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="58751-131">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="58751-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="58751-132">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mit abonniert werden [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="58751-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="58751-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58751-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="58751-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="58751-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="58751-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="58751-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
