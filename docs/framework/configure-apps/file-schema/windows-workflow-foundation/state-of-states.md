---
title: '&lt;state&gt; von &lt;states&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 8893f6acfc7ec4d6989be2c647b0584093a534a1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756851"
---
# <a name="ltstategt-of-ltstatesgt"></a><span data-ttu-id="17185-102">&lt;state&gt; von &lt;states&gt;</span><span class="sxs-lookup"><span data-stu-id="17185-102">&lt;state&gt; of &lt;states&gt;</span></span>
<span data-ttu-id="17185-103">Ein Konfigurationselement, das den Zustand der abonnierten Aktivität enthält, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="17185-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="17185-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="17185-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="17185-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="17185-105">\<system.serviceModel></span></span>  
<span data-ttu-id="17185-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="17185-106">\<tracking></span></span>  
<span data-ttu-id="17185-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="17185-107">\<trackingProfile></span></span>  
<span data-ttu-id="17185-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="17185-108">\<workflow></span></span>  
<span data-ttu-id="17185-109">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="17185-109">\<activityStateQueries></span></span>  
<span data-ttu-id="17185-110">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="17185-110">\<activityStateQuery></span></span>  
<span data-ttu-id="17185-111">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="17185-111">\<states></span></span>  
<span data-ttu-id="17185-112">\<State ></span><span class="sxs-lookup"><span data-stu-id="17185-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17185-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="17185-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17185-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="17185-114">Attributes and Elements</span></span>  
 <span data-ttu-id="17185-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="17185-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17185-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="17185-116">Attributes</span></span>  
  
|<span data-ttu-id="17185-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="17185-117">Attribute</span></span>|<span data-ttu-id="17185-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17185-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17185-119">Name</span><span class="sxs-lookup"><span data-stu-id="17185-119">name</span></span>|<span data-ttu-id="17185-120">Eine Zeichenfolge, die den Zustand der abonnierten Aktivität angibt, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="17185-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17185-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="17185-121">Child Elements</span></span>  
 <span data-ttu-id="17185-122">Keine</span><span class="sxs-lookup"><span data-stu-id="17185-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17185-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="17185-123">Parent Elements</span></span>  
  
|<span data-ttu-id="17185-124">Element</span><span class="sxs-lookup"><span data-stu-id="17185-124">Element</span></span>|<span data-ttu-id="17185-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17185-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17185-126">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="17185-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="17185-127">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="17185-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17185-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17185-128">Remarks</span></span>  
 <span data-ttu-id="17185-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="17185-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="17185-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="17185-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="17185-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="17185-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="17185-132">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="17185-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17185-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17185-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="17185-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="17185-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="17185-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="17185-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
