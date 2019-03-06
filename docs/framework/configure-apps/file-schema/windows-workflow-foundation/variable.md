---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: e487e54ac5c70351d00df4275302bc9f4e92292c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366529"
---
# <a name="variable"></a><span data-ttu-id="6ec49-101">\<variable></span><span class="sxs-lookup"><span data-stu-id="6ec49-101">\<variable></span></span>
<span data-ttu-id="6ec49-102">Stellt eine Auflistung von Variablen dar, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6ec49-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="6ec49-103">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6ec49-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6ec49-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6ec49-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6ec49-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6ec49-105">\<tracking></span></span>  
<span data-ttu-id="6ec49-106">\<profiles></span><span class="sxs-lookup"><span data-stu-id="6ec49-106">\<profiles></span></span>  
<span data-ttu-id="6ec49-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6ec49-107">\<trackingProfile></span></span>  
<span data-ttu-id="6ec49-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6ec49-108">\<workflow></span></span>  
<span data-ttu-id="6ec49-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="6ec49-109">\<activityStateQueries></span></span>  
<span data-ttu-id="6ec49-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="6ec49-110">\<activityStateQuery></span></span>  
<span data-ttu-id="6ec49-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="6ec49-111">\<variables></span></span>  
<span data-ttu-id="6ec49-112">\<variable></span><span class="sxs-lookup"><span data-stu-id="6ec49-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec49-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ec49-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ec49-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6ec49-114">Attributes and Elements</span></span>  
 <span data-ttu-id="6ec49-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6ec49-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ec49-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="6ec49-116">Attributes</span></span>  
  
|<span data-ttu-id="6ec49-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="6ec49-117">Attribute</span></span>|<span data-ttu-id="6ec49-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ec49-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ec49-119">Name</span><span class="sxs-lookup"><span data-stu-id="6ec49-119">name</span></span>|<span data-ttu-id="6ec49-120">Eine Zeichenfolge, die den Namen der Variablen angibt.</span><span class="sxs-lookup"><span data-stu-id="6ec49-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ec49-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ec49-121">Child Elements</span></span>  
 <span data-ttu-id="6ec49-122">Keine</span><span class="sxs-lookup"><span data-stu-id="6ec49-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ec49-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ec49-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6ec49-124">Element</span><span class="sxs-lookup"><span data-stu-id="6ec49-124">Element</span></span>|<span data-ttu-id="6ec49-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ec49-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ec49-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="6ec49-126">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="6ec49-127">Eine einer Aktivitätszustandsabfrage zugeordnete Variable.</span><span class="sxs-lookup"><span data-stu-id="6ec49-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ec49-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ec49-128">Remarks</span></span>  
 <span data-ttu-id="6ec49-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="6ec49-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="6ec49-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="6ec49-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="6ec49-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="6ec49-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="6ec49-132">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6ec49-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="6ec49-133">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="6ec49-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6ec49-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ec49-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6ec49-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="6ec49-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6ec49-136">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="6ec49-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
