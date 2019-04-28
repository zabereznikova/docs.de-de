---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: 2b0d982997ab590ce7f0fc4c482b1ddfa6bc758f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790363"
---
# <a name="arguments"></a><span data-ttu-id="d145b-101">\<arguments></span><span class="sxs-lookup"><span data-stu-id="d145b-101">\<arguments></span></span>
<span data-ttu-id="d145b-102">Stellt eine Auflistung von Argumenten dar, die einer Aktivitätszustandsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d145b-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="d145b-103">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d145b-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="d145b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d145b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d145b-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d145b-105">\<tracking></span></span>  
<span data-ttu-id="d145b-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d145b-106">\<trackingProfile></span></span>  
<span data-ttu-id="d145b-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d145b-107">\<workflow></span></span>  
<span data-ttu-id="d145b-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="d145b-108">\<activityStateQueries></span></span>  
<span data-ttu-id="d145b-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="d145b-109">\<activityStateQuery></span></span>  
<span data-ttu-id="d145b-110">\<arguments></span><span class="sxs-lookup"><span data-stu-id="d145b-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d145b-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="d145b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d145b-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d145b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d145b-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d145b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d145b-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="d145b-114">Attributes</span></span>  
 <span data-ttu-id="d145b-115">Keine</span><span class="sxs-lookup"><span data-stu-id="d145b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d145b-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d145b-116">Child Elements</span></span>  
  
|<span data-ttu-id="d145b-117">Element</span><span class="sxs-lookup"><span data-stu-id="d145b-117">Element</span></span>|<span data-ttu-id="d145b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d145b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d145b-119">\<argument></span><span class="sxs-lookup"><span data-stu-id="d145b-119">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="d145b-120">Ein einer Aktivitätszustandsabfrage zugeordnetes Argument.</span><span class="sxs-lookup"><span data-stu-id="d145b-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d145b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d145b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d145b-122">Element</span><span class="sxs-lookup"><span data-stu-id="d145b-122">Element</span></span>|<span data-ttu-id="d145b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d145b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d145b-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="d145b-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="d145b-125">Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="d145b-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d145b-126">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="d145b-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d145b-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d145b-127">Remarks</span></span>  
 <span data-ttu-id="d145b-128">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="d145b-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="d145b-129">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="d145b-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="d145b-130">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="d145b-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="d145b-131">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d145b-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="d145b-132">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="d145b-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d145b-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d145b-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d145b-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d145b-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d145b-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d145b-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
