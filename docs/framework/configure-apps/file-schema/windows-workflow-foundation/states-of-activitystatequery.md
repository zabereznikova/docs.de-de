---
title: '&lt;states&gt; von &lt;activityStateQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4df89af05ae341a981c3b4f34ba919bb445d724e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltstatesgt-of-ltactivitystatequerygt"></a><span data-ttu-id="a226e-102">&lt;states&gt; von &lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="a226e-102">&lt;states&gt; of &lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="a226e-103">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a226e-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="a226e-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a226e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a226e-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a226e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a226e-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="a226e-106">\<tracking></span></span>  
<span data-ttu-id="a226e-107">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a226e-107">\<trackingProfile></span></span>  
<span data-ttu-id="a226e-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a226e-108">\<workflow></span></span>  
<span data-ttu-id="a226e-109">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="a226e-109">\<activityStateQueries></span></span>  
<span data-ttu-id="a226e-110">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a226e-110">\<activityStateQuery></span></span>  
<span data-ttu-id="a226e-111">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="a226e-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a226e-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="a226e-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a226e-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a226e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a226e-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a226e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a226e-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="a226e-115">Attributes</span></span>  
 <span data-ttu-id="a226e-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="a226e-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a226e-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a226e-117">Child Elements</span></span>  
  
|<span data-ttu-id="a226e-118">Element</span><span class="sxs-lookup"><span data-stu-id="a226e-118">Element</span></span>|<span data-ttu-id="a226e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a226e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a226e-120">\<State ></span><span class="sxs-lookup"><span data-stu-id="a226e-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="a226e-121">Ein Konfigurationselement, das die Zustände der abonnierten Aktivität enthält, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a226e-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a226e-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a226e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a226e-123">Element</span><span class="sxs-lookup"><span data-stu-id="a226e-123">Element</span></span>|<span data-ttu-id="a226e-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a226e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a226e-125">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a226e-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="a226e-126">Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a226e-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a226e-127">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a226e-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a226e-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a226e-128">Remarks</span></span>  
 <span data-ttu-id="a226e-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a226e-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a226e-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a226e-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a226e-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a226e-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a226e-132">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="a226e-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a226e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a226e-133">See Also</span></span>  
 <span data-ttu-id="a226e-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a226e-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>      
 <span data-ttu-id="a226e-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a226e-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="a226e-136">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a226e-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a226e-137">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a226e-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
