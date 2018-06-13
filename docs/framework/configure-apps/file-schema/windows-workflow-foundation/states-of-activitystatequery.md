---
title: '&lt;states&gt; von &lt;activityStateQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: d26687e9d0f2bee672f6b0c6c38b87fadf6e7888
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756773"
---
# <a name="ltstatesgt-of-ltactivitystatequerygt"></a><span data-ttu-id="795ed-102">&lt;states&gt; von &lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="795ed-102">&lt;states&gt; of &lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="795ed-103">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="795ed-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="795ed-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="795ed-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="795ed-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="795ed-105">\<system.serviceModel></span></span>  
<span data-ttu-id="795ed-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="795ed-106">\<tracking></span></span>  
<span data-ttu-id="795ed-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="795ed-107">\<trackingProfile></span></span>  
<span data-ttu-id="795ed-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="795ed-108">\<workflow></span></span>  
<span data-ttu-id="795ed-109">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="795ed-109">\<activityStateQueries></span></span>  
<span data-ttu-id="795ed-110">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="795ed-110">\<activityStateQuery></span></span>  
<span data-ttu-id="795ed-111">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="795ed-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="795ed-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="795ed-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="795ed-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="795ed-113">Attributes and Elements</span></span>  
 <span data-ttu-id="795ed-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="795ed-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="795ed-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="795ed-115">Attributes</span></span>  
 <span data-ttu-id="795ed-116">Keine</span><span class="sxs-lookup"><span data-stu-id="795ed-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="795ed-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="795ed-117">Child Elements</span></span>  
  
|<span data-ttu-id="795ed-118">Element</span><span class="sxs-lookup"><span data-stu-id="795ed-118">Element</span></span>|<span data-ttu-id="795ed-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="795ed-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="795ed-120">\<State ></span><span class="sxs-lookup"><span data-stu-id="795ed-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="795ed-121">Ein Konfigurationselement, das die Zustände der abonnierten Aktivität enthält, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="795ed-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="795ed-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="795ed-122">Parent Elements</span></span>  
  
|<span data-ttu-id="795ed-123">Element</span><span class="sxs-lookup"><span data-stu-id="795ed-123">Element</span></span>|<span data-ttu-id="795ed-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="795ed-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="795ed-125">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="795ed-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="795ed-126">Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="795ed-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="795ed-127">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="795ed-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="795ed-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="795ed-128">Remarks</span></span>  
 <span data-ttu-id="795ed-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="795ed-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="795ed-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="795ed-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="795ed-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="795ed-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="795ed-132">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="795ed-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="795ed-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="795ed-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>      
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="795ed-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="795ed-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="795ed-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="795ed-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
