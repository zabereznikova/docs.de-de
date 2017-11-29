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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3db57b3332638092fc9f16de5199b65c4efafebd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltvariablegt"></a><span data-ttu-id="9b545-102">&lt;Variable&gt;</span><span class="sxs-lookup"><span data-stu-id="9b545-102">&lt;variable&gt;</span></span>
<span data-ttu-id="9b545-103">Stellt eine Auflistung von Variablen dar, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9b545-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="9b545-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9b545-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9b545-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9b545-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9b545-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="9b545-106">\<tracking></span></span>  
<span data-ttu-id="9b545-107">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="9b545-107">\<profiles></span></span>  
<span data-ttu-id="9b545-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9b545-108">\<trackingProfile></span></span>  
<span data-ttu-id="9b545-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="9b545-109">\<workflow></span></span>  
<span data-ttu-id="9b545-110">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="9b545-110">\<activityStateQueries></span></span>  
<span data-ttu-id="9b545-111">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="9b545-111">\<activityStateQuery></span></span>  
<span data-ttu-id="9b545-112">\<Variablen ></span><span class="sxs-lookup"><span data-stu-id="9b545-112">\<variables></span></span>  
<span data-ttu-id="9b545-113">\<Variable ></span><span class="sxs-lookup"><span data-stu-id="9b545-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b545-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b545-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b545-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9b545-115">Attributes and Elements</span></span>  
 <span data-ttu-id="9b545-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b545-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b545-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="9b545-117">Attributes</span></span>  
  
|<span data-ttu-id="9b545-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="9b545-118">Attribute</span></span>|<span data-ttu-id="9b545-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b545-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b545-120">Name</span><span class="sxs-lookup"><span data-stu-id="9b545-120">name</span></span>|<span data-ttu-id="9b545-121">Eine Zeichenfolge, die den Namen der Variablen angibt.</span><span class="sxs-lookup"><span data-stu-id="9b545-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b545-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b545-122">Child Elements</span></span>  
 <span data-ttu-id="9b545-123">Keine</span><span class="sxs-lookup"><span data-stu-id="9b545-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b545-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b545-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9b545-125">Element</span><span class="sxs-lookup"><span data-stu-id="9b545-125">Element</span></span>|<span data-ttu-id="9b545-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b545-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b545-127">\<Variable ></span><span class="sxs-lookup"><span data-stu-id="9b545-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="9b545-128">Eine einer Aktivitätszustandsabfrage zugeordnete Variable.</span><span class="sxs-lookup"><span data-stu-id="9b545-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b545-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b545-129">Remarks</span></span>  
 <span data-ttu-id="9b545-130">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="9b545-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="9b545-131">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="9b545-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="9b545-132">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9b545-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="9b545-133">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="9b545-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b545-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b545-134">See Also</span></span>  
 <span data-ttu-id="9b545-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9b545-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="9b545-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9b545-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="9b545-137">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="9b545-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9b545-138">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="9b545-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
