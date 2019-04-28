---
title: <states> von <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: fa3736fc13f6f40f52d15b8257b7a79f4179d738
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796954"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="29025-102">\<states> of \<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="29025-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="29025-103">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="29025-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="29025-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="29025-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="29025-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="29025-105">\<system.serviceModel></span></span>  
<span data-ttu-id="29025-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="29025-106">\<tracking></span></span>  
<span data-ttu-id="29025-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="29025-107">\<trackingProfile></span></span>  
<span data-ttu-id="29025-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="29025-108">\<workflow></span></span>  
<span data-ttu-id="29025-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="29025-109">\<activityStateQueries></span></span>  
<span data-ttu-id="29025-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="29025-110">\<activityStateQuery></span></span>  
<span data-ttu-id="29025-111">\<states></span><span class="sxs-lookup"><span data-stu-id="29025-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29025-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="29025-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29025-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="29025-113">Attributes and Elements</span></span>  
 <span data-ttu-id="29025-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29025-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29025-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="29025-115">Attributes</span></span>  
 <span data-ttu-id="29025-116">Keine</span><span class="sxs-lookup"><span data-stu-id="29025-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="29025-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="29025-117">Child Elements</span></span>  
  
|<span data-ttu-id="29025-118">Element</span><span class="sxs-lookup"><span data-stu-id="29025-118">Element</span></span>|<span data-ttu-id="29025-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29025-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29025-120">\<state></span><span class="sxs-lookup"><span data-stu-id="29025-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="29025-121">Ein Konfigurationselement, das die Zustände der abonnierten Aktivität enthält, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="29025-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29025-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="29025-122">Parent Elements</span></span>  
  
|<span data-ttu-id="29025-123">Element</span><span class="sxs-lookup"><span data-stu-id="29025-123">Element</span></span>|<span data-ttu-id="29025-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29025-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29025-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="29025-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="29025-126">Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="29025-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="29025-127">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="29025-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29025-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29025-128">Remarks</span></span>  
 <span data-ttu-id="29025-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="29025-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="29025-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="29025-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="29025-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="29025-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="29025-132">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="29025-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="29025-133">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="29025-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29025-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29025-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="29025-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="29025-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="29025-136">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="29025-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
