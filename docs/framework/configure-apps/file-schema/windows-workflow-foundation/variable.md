---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: e487e54ac5c70351d00df4275302bc9f4e92292c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270601"
---
# <a name="variable"></a><span data-ttu-id="a0b70-101">\<variable></span><span class="sxs-lookup"><span data-stu-id="a0b70-101">\<variable></span></span>
<span data-ttu-id="a0b70-102">Stellt eine Auflistung von Variablen dar, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a0b70-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="a0b70-103">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a0b70-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a0b70-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a0b70-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a0b70-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a0b70-105">\<tracking></span></span>  
<span data-ttu-id="a0b70-106">\<profiles></span><span class="sxs-lookup"><span data-stu-id="a0b70-106">\<profiles></span></span>  
<span data-ttu-id="a0b70-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a0b70-107">\<trackingProfile></span></span>  
<span data-ttu-id="a0b70-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a0b70-108">\<workflow></span></span>  
<span data-ttu-id="a0b70-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="a0b70-109">\<activityStateQueries></span></span>  
<span data-ttu-id="a0b70-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="a0b70-110">\<activityStateQuery></span></span>  
<span data-ttu-id="a0b70-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="a0b70-111">\<variables></span></span>  
<span data-ttu-id="a0b70-112">\<variable></span><span class="sxs-lookup"><span data-stu-id="a0b70-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b70-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0b70-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0b70-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a0b70-114">Attributes and Elements</span></span>  
 <span data-ttu-id="a0b70-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0b70-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0b70-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0b70-116">Attributes</span></span>  
  
|<span data-ttu-id="a0b70-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0b70-117">Attribute</span></span>|<span data-ttu-id="a0b70-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0b70-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0b70-119">Name</span><span class="sxs-lookup"><span data-stu-id="a0b70-119">name</span></span>|<span data-ttu-id="a0b70-120">Eine Zeichenfolge, die den Namen der Variablen angibt.</span><span class="sxs-lookup"><span data-stu-id="a0b70-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0b70-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0b70-121">Child Elements</span></span>  
 <span data-ttu-id="a0b70-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a0b70-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0b70-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0b70-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a0b70-124">Element</span><span class="sxs-lookup"><span data-stu-id="a0b70-124">Element</span></span>|<span data-ttu-id="a0b70-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0b70-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0b70-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="a0b70-126">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="a0b70-127">Eine einer Aktivitätszustandsabfrage zugeordnete Variable.</span><span class="sxs-lookup"><span data-stu-id="a0b70-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0b70-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0b70-128">Remarks</span></span>  
 <span data-ttu-id="a0b70-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a0b70-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a0b70-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a0b70-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a0b70-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="a0b70-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="a0b70-132">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a0b70-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a0b70-133">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="a0b70-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0b70-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0b70-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a0b70-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a0b70-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a0b70-136">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a0b70-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
