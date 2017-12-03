---
title: '&lt;Variable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad2a4d3768c26755a9437826c70585a43f967d09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltvariablegt"></a><span data-ttu-id="a9c41-102">&lt;Variable&gt;</span><span class="sxs-lookup"><span data-stu-id="a9c41-102">&lt;variable&gt;</span></span>
<span data-ttu-id="a9c41-103">Stellt eine Auflistung von Variablen dar, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a9c41-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="a9c41-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a9c41-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a9c41-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a9c41-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a9c41-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="a9c41-106">\<tracking></span></span>  
<span data-ttu-id="a9c41-107">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="a9c41-107">\<profiles></span></span>  
<span data-ttu-id="a9c41-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a9c41-108">\<trackingProfile></span></span>  
<span data-ttu-id="a9c41-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a9c41-109">\<workflow></span></span>  
<span data-ttu-id="a9c41-110">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="a9c41-110">\<activityStateQueries></span></span>  
<span data-ttu-id="a9c41-111">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a9c41-111">\<activityStateQuery></span></span>  
<span data-ttu-id="a9c41-112">\<Variablen ></span><span class="sxs-lookup"><span data-stu-id="a9c41-112">\<variables></span></span>  
<span data-ttu-id="a9c41-113">\<Variable ></span><span class="sxs-lookup"><span data-stu-id="a9c41-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c41-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9c41-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9c41-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a9c41-115">Attributes and Elements</span></span>  
 <span data-ttu-id="a9c41-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9c41-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9c41-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="a9c41-117">Attributes</span></span>  
  
|<span data-ttu-id="a9c41-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="a9c41-118">Attribute</span></span>|<span data-ttu-id="a9c41-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9c41-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9c41-120">Name</span><span class="sxs-lookup"><span data-stu-id="a9c41-120">name</span></span>|<span data-ttu-id="a9c41-121">Eine Zeichenfolge, die den Namen der Variablen angibt.</span><span class="sxs-lookup"><span data-stu-id="a9c41-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9c41-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9c41-122">Child Elements</span></span>  
 <span data-ttu-id="a9c41-123">Keine</span><span class="sxs-lookup"><span data-stu-id="a9c41-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9c41-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9c41-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a9c41-125">Element</span><span class="sxs-lookup"><span data-stu-id="a9c41-125">Element</span></span>|<span data-ttu-id="a9c41-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9c41-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9c41-127">\<Variable ></span><span class="sxs-lookup"><span data-stu-id="a9c41-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="a9c41-128">Eine einer Aktivitätszustandsabfrage zugeordnete Variable.</span><span class="sxs-lookup"><span data-stu-id="a9c41-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9c41-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9c41-129">Remarks</span></span>  
 <span data-ttu-id="a9c41-130">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a9c41-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a9c41-131">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a9c41-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a9c41-132">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a9c41-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a9c41-133">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="a9c41-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a9c41-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9c41-134">See Also</span></span>  
 <span data-ttu-id="a9c41-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a9c41-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="a9c41-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a9c41-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="a9c41-137">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a9c41-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a9c41-138">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a9c41-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
