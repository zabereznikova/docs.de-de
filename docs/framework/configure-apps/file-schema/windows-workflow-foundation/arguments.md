---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: 3e9fc4f286e7aba6406ce61910da9e614e13ffca
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276562"
---
# <a name="arguments"></a><span data-ttu-id="eaa02-101">\<arguments></span><span class="sxs-lookup"><span data-stu-id="eaa02-101">\<arguments></span></span>
<span data-ttu-id="eaa02-102">Stellt eine Auflistung von Argumenten dar, die einer Aktivitätszustandsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="eaa02-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="eaa02-103">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="eaa02-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="eaa02-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eaa02-104">\<system.serviceModel></span></span>  
<span data-ttu-id="eaa02-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="eaa02-105">\<tracking></span></span>  
<span data-ttu-id="eaa02-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="eaa02-106">\<trackingProfile></span></span>  
<span data-ttu-id="eaa02-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="eaa02-107">\<workflow></span></span>  
<span data-ttu-id="eaa02-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="eaa02-108">\<activityStateQueries></span></span>  
<span data-ttu-id="eaa02-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="eaa02-109">\<activityStateQuery></span></span>  
<span data-ttu-id="eaa02-110">\<arguments></span><span class="sxs-lookup"><span data-stu-id="eaa02-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa02-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="eaa02-111">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaa02-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eaa02-112">Attributes and Elements</span></span>  
 <span data-ttu-id="eaa02-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eaa02-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaa02-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="eaa02-114">Attributes</span></span>  
 <span data-ttu-id="eaa02-115">Keine</span><span class="sxs-lookup"><span data-stu-id="eaa02-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eaa02-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eaa02-116">Child Elements</span></span>  
  
|<span data-ttu-id="eaa02-117">Element</span><span class="sxs-lookup"><span data-stu-id="eaa02-117">Element</span></span>|<span data-ttu-id="eaa02-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eaa02-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eaa02-119">\<argument></span><span class="sxs-lookup"><span data-stu-id="eaa02-119">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="eaa02-120">Ein einer Aktivitätszustandsabfrage zugeordnetes Argument.</span><span class="sxs-lookup"><span data-stu-id="eaa02-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eaa02-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eaa02-121">Parent Elements</span></span>  
  
|<span data-ttu-id="eaa02-122">Element</span><span class="sxs-lookup"><span data-stu-id="eaa02-122">Element</span></span>|<span data-ttu-id="eaa02-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eaa02-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eaa02-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="eaa02-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="eaa02-125">Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="eaa02-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="eaa02-126">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="eaa02-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaa02-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eaa02-127">Remarks</span></span>  
 <span data-ttu-id="eaa02-128">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="eaa02-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="eaa02-129">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="eaa02-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="eaa02-130">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="eaa02-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="eaa02-131">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="eaa02-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="eaa02-132">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="eaa02-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eaa02-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eaa02-133">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="eaa02-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="eaa02-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eaa02-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="eaa02-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
