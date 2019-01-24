---
title: '&lt;variable&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 185e7e7196f6679ec3d1fae8a2a256b934022ca9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647880"
---
# <a name="ltvariablegt"></a><span data-ttu-id="a1610-102">&lt;variable&gt;</span><span class="sxs-lookup"><span data-stu-id="a1610-102">&lt;variable&gt;</span></span>
<span data-ttu-id="a1610-103">Stellt eine Auflistung von Variablen dar, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a1610-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="a1610-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a1610-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a1610-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a1610-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a1610-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a1610-106">\<tracking></span></span>  
<span data-ttu-id="a1610-107">\<profiles></span><span class="sxs-lookup"><span data-stu-id="a1610-107">\<profiles></span></span>  
<span data-ttu-id="a1610-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a1610-108">\<trackingProfile></span></span>  
<span data-ttu-id="a1610-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a1610-109">\<workflow></span></span>  
<span data-ttu-id="a1610-110">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="a1610-110">\<activityStateQueries></span></span>  
<span data-ttu-id="a1610-111">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="a1610-111">\<activityStateQuery></span></span>  
<span data-ttu-id="a1610-112">\<variables></span><span class="sxs-lookup"><span data-stu-id="a1610-112">\<variables></span></span>  
<span data-ttu-id="a1610-113">\<variable></span><span class="sxs-lookup"><span data-stu-id="a1610-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1610-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1610-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1610-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1610-115">Attributes and Elements</span></span>  
 <span data-ttu-id="a1610-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1610-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1610-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1610-117">Attributes</span></span>  
  
|<span data-ttu-id="a1610-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="a1610-118">Attribute</span></span>|<span data-ttu-id="a1610-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1610-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1610-120">Name</span><span class="sxs-lookup"><span data-stu-id="a1610-120">name</span></span>|<span data-ttu-id="a1610-121">Eine Zeichenfolge, die den Namen der Variablen angibt.</span><span class="sxs-lookup"><span data-stu-id="a1610-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1610-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1610-122">Child Elements</span></span>  
 <span data-ttu-id="a1610-123">Keine</span><span class="sxs-lookup"><span data-stu-id="a1610-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1610-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1610-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a1610-125">Element</span><span class="sxs-lookup"><span data-stu-id="a1610-125">Element</span></span>|<span data-ttu-id="a1610-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1610-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1610-127">\<variable></span><span class="sxs-lookup"><span data-stu-id="a1610-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="a1610-128">Eine einer Aktivitätszustandsabfrage zugeordnete Variable.</span><span class="sxs-lookup"><span data-stu-id="a1610-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1610-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1610-129">Remarks</span></span>  
 <span data-ttu-id="a1610-130">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a1610-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a1610-131">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a1610-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a1610-132">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="a1610-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="a1610-133">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a1610-133">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a1610-134">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="a1610-134">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1610-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1610-135">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a1610-136">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a1610-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a1610-137">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a1610-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
