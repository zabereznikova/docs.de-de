---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: a920d60d703fe262bee96d75c420c526d54f88ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210645"
---
# <a name="argument"></a><span data-ttu-id="e6fec-101">\<argument></span><span class="sxs-lookup"><span data-stu-id="e6fec-101">\<argument></span></span>
<span data-ttu-id="e6fec-102">Ein Konfigurationselement, das ein einer Aktivitätszustandsabfrage zugeordnetes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="e6fec-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="e6fec-103">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e6fec-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e6fec-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e6fec-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e6fec-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e6fec-105">\<tracking></span></span>  
<span data-ttu-id="e6fec-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e6fec-106">\<trackingProfile></span></span>  
<span data-ttu-id="e6fec-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="e6fec-107">\<workflow></span></span>  
<span data-ttu-id="e6fec-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="e6fec-108">\<activityStateQueries></span></span>  
<span data-ttu-id="e6fec-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="e6fec-109">\<activityStateQuery></span></span>  
<span data-ttu-id="e6fec-110">\<arguments></span><span class="sxs-lookup"><span data-stu-id="e6fec-110">\<arguments></span></span>  
<span data-ttu-id="e6fec-111">\<argument></span><span class="sxs-lookup"><span data-stu-id="e6fec-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6fec-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6fec-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6fec-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e6fec-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e6fec-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6fec-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6fec-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="e6fec-115">Attributes</span></span>  
  
|<span data-ttu-id="e6fec-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="e6fec-116">Attribute</span></span>|<span data-ttu-id="e6fec-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6fec-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6fec-118">Name</span><span class="sxs-lookup"><span data-stu-id="e6fec-118">name</span></span>|<span data-ttu-id="e6fec-119">Eine Zeichenfolge, die den Namen des Arguments angibt.</span><span class="sxs-lookup"><span data-stu-id="e6fec-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6fec-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6fec-120">Child Elements</span></span>  
 <span data-ttu-id="e6fec-121">Keine</span><span class="sxs-lookup"><span data-stu-id="e6fec-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6fec-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6fec-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e6fec-123">Element</span><span class="sxs-lookup"><span data-stu-id="e6fec-123">Element</span></span>|<span data-ttu-id="e6fec-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6fec-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6fec-125">\<arguments></span><span class="sxs-lookup"><span data-stu-id="e6fec-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="e6fec-126">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="e6fec-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6fec-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6fec-127">Remarks</span></span>  
 <span data-ttu-id="e6fec-128">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="e6fec-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="e6fec-129">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="e6fec-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="e6fec-130">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="e6fec-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="e6fec-131">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e6fec-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="e6fec-132">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="e6fec-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6fec-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6fec-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e6fec-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="e6fec-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e6fec-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="e6fec-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
