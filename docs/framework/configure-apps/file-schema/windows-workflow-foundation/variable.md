---
title: '&lt;Variable&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 7d41d80bfe83cfafca01509d50709e21730bcb97
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltvariablegt"></a><span data-ttu-id="9c75e-102">&lt;Variable&gt;</span><span class="sxs-lookup"><span data-stu-id="9c75e-102">&lt;variable&gt;</span></span>
<span data-ttu-id="9c75e-103">Stellt eine Auflistung von Variablen dar, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9c75e-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="9c75e-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9c75e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9c75e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9c75e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9c75e-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="9c75e-106">\<tracking></span></span>  
<span data-ttu-id="9c75e-107">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="9c75e-107">\<profiles></span></span>  
<span data-ttu-id="9c75e-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9c75e-108">\<trackingProfile></span></span>  
<span data-ttu-id="9c75e-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="9c75e-109">\<workflow></span></span>  
<span data-ttu-id="9c75e-110">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="9c75e-110">\<activityStateQueries></span></span>  
<span data-ttu-id="9c75e-111">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="9c75e-111">\<activityStateQuery></span></span>  
<span data-ttu-id="9c75e-112">\<Variablen ></span><span class="sxs-lookup"><span data-stu-id="9c75e-112">\<variables></span></span>  
<span data-ttu-id="9c75e-113">\<Variable ></span><span class="sxs-lookup"><span data-stu-id="9c75e-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c75e-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c75e-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c75e-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9c75e-115">Attributes and Elements</span></span>  
 <span data-ttu-id="9c75e-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c75e-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c75e-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="9c75e-117">Attributes</span></span>  
  
|<span data-ttu-id="9c75e-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="9c75e-118">Attribute</span></span>|<span data-ttu-id="9c75e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c75e-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c75e-120">Name</span><span class="sxs-lookup"><span data-stu-id="9c75e-120">name</span></span>|<span data-ttu-id="9c75e-121">Eine Zeichenfolge, die den Namen der Variablen angibt.</span><span class="sxs-lookup"><span data-stu-id="9c75e-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c75e-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c75e-122">Child Elements</span></span>  
 <span data-ttu-id="9c75e-123">Keine</span><span class="sxs-lookup"><span data-stu-id="9c75e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c75e-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c75e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9c75e-125">Element</span><span class="sxs-lookup"><span data-stu-id="9c75e-125">Element</span></span>|<span data-ttu-id="9c75e-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c75e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c75e-127">\<Variable ></span><span class="sxs-lookup"><span data-stu-id="9c75e-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="9c75e-128">Eine einer Aktivitätszustandsabfrage zugeordnete Variable.</span><span class="sxs-lookup"><span data-stu-id="9c75e-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c75e-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c75e-129">Remarks</span></span>  
 <span data-ttu-id="9c75e-130">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="9c75e-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="9c75e-131">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="9c75e-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="9c75e-132">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9c75e-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="9c75e-133">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="9c75e-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c75e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c75e-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="9c75e-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="9c75e-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9c75e-136">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="9c75e-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
