---
title: '&lt;Argumente&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: 6810e004d74cec1dec3056017eb324ff667d9f1d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152571"
---
# <a name="ltargumentsgt"></a><span data-ttu-id="0b288-102">&lt;Argumente&gt;</span><span class="sxs-lookup"><span data-stu-id="0b288-102">&lt;arguments&gt;</span></span>
<span data-ttu-id="0b288-103">Stellt eine Auflistung von Argumenten dar, die einer Aktivitätszustandsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0b288-103">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="0b288-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0b288-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0b288-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0b288-105">\<system.serviceModel></span></span>  
<span data-ttu-id="0b288-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="0b288-106">\<tracking></span></span>  
<span data-ttu-id="0b288-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0b288-107">\<trackingProfile></span></span>  
<span data-ttu-id="0b288-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="0b288-108">\<workflow></span></span>  
<span data-ttu-id="0b288-109">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="0b288-109">\<activityStateQueries></span></span>  
<span data-ttu-id="0b288-110">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="0b288-110">\<activityStateQuery></span></span>  
<span data-ttu-id="0b288-111">\<Argumente ></span><span class="sxs-lookup"><span data-stu-id="0b288-111">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b288-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b288-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b288-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b288-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0b288-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b288-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b288-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b288-115">Attributes</span></span>  
 <span data-ttu-id="0b288-116">Keine</span><span class="sxs-lookup"><span data-stu-id="0b288-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b288-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b288-117">Child Elements</span></span>  
  
|<span data-ttu-id="0b288-118">Element</span><span class="sxs-lookup"><span data-stu-id="0b288-118">Element</span></span>|<span data-ttu-id="0b288-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b288-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b288-120">\<Argument ></span><span class="sxs-lookup"><span data-stu-id="0b288-120">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="0b288-121">Ein einer Aktivitätszustandsabfrage zugeordnetes Argument.</span><span class="sxs-lookup"><span data-stu-id="0b288-121">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b288-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b288-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0b288-123">Element</span><span class="sxs-lookup"><span data-stu-id="0b288-123">Element</span></span>|<span data-ttu-id="0b288-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b288-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b288-125">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="0b288-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="0b288-126">Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0b288-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0b288-127">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0b288-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b288-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b288-128">Remarks</span></span>  
 <span data-ttu-id="0b288-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="0b288-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="0b288-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="0b288-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="0b288-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="0b288-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="0b288-132">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0b288-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="0b288-133">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="0b288-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0b288-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b288-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="0b288-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0b288-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0b288-136">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="0b288-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
