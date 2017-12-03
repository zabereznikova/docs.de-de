---
title: '&lt;state&gt; von &lt;states&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5cbe5eda4487d8cbde671dd427bdfc90431d0599
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltstategt-of-ltstatesgt"></a><span data-ttu-id="a719f-102">&lt;state&gt; von &lt;states&gt;</span><span class="sxs-lookup"><span data-stu-id="a719f-102">&lt;state&gt; of &lt;states&gt;</span></span>
<span data-ttu-id="a719f-103">Ein Konfigurationselement, das den Zustand der abonnierten Aktivität enthält, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a719f-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="a719f-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a719f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a719f-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a719f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a719f-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="a719f-106">\<tracking></span></span>  
<span data-ttu-id="a719f-107">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a719f-107">\<trackingProfile></span></span>  
<span data-ttu-id="a719f-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a719f-108">\<workflow></span></span>  
<span data-ttu-id="a719f-109">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="a719f-109">\<activityStateQueries></span></span>  
<span data-ttu-id="a719f-110">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a719f-110">\<activityStateQuery></span></span>  
<span data-ttu-id="a719f-111">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="a719f-111">\<states></span></span>  
<span data-ttu-id="a719f-112">\<State ></span><span class="sxs-lookup"><span data-stu-id="a719f-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a719f-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="a719f-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a719f-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a719f-114">Attributes and Elements</span></span>  
 <span data-ttu-id="a719f-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a719f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a719f-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="a719f-116">Attributes</span></span>  
  
|<span data-ttu-id="a719f-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="a719f-117">Attribute</span></span>|<span data-ttu-id="a719f-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a719f-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a719f-119">Name</span><span class="sxs-lookup"><span data-stu-id="a719f-119">name</span></span>|<span data-ttu-id="a719f-120">Eine Zeichenfolge, die den Zustand der abonnierten Aktivität angibt, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a719f-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a719f-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a719f-121">Child Elements</span></span>  
 <span data-ttu-id="a719f-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a719f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a719f-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a719f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a719f-124">Element</span><span class="sxs-lookup"><span data-stu-id="a719f-124">Element</span></span>|<span data-ttu-id="a719f-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a719f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a719f-126">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="a719f-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="a719f-127">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a719f-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a719f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a719f-128">Remarks</span></span>  
 <span data-ttu-id="a719f-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a719f-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a719f-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a719f-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a719f-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a719f-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a719f-132">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="a719f-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a719f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a719f-133">See Also</span></span>  
 <span data-ttu-id="a719f-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a719f-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="a719f-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a719f-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="a719f-136">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a719f-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a719f-137">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a719f-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
