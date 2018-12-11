---
title: '&lt;state&gt; von &lt;states&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: e4eaf1cbe788018b46759efb1e9755d65b19cc60
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148293"
---
# <a name="ltstategt-of-ltstatesgt"></a><span data-ttu-id="a1b2c-102">&lt;state&gt; von &lt;states&gt;</span><span class="sxs-lookup"><span data-stu-id="a1b2c-102">&lt;state&gt; of &lt;states&gt;</span></span>
<span data-ttu-id="a1b2c-103">Ein Konfigurationselement, das den Zustand der abonnierten Aktivität enthält, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1b2c-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="a1b2c-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a1b2c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a1b2c-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a1b2c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a1b2c-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="a1b2c-106">\<tracking></span></span>  
<span data-ttu-id="a1b2c-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a1b2c-107">\<trackingProfile></span></span>  
<span data-ttu-id="a1b2c-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a1b2c-108">\<workflow></span></span>  
<span data-ttu-id="a1b2c-109">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="a1b2c-109">\<activityStateQueries></span></span>  
<span data-ttu-id="a1b2c-110">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a1b2c-110">\<activityStateQuery></span></span>  
<span data-ttu-id="a1b2c-111">\<Status ></span><span class="sxs-lookup"><span data-stu-id="a1b2c-111">\<states></span></span>  
<span data-ttu-id="a1b2c-112">\<Status ></span><span class="sxs-lookup"><span data-stu-id="a1b2c-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1b2c-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1b2c-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1b2c-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1b2c-114">Attributes and Elements</span></span>  
 <span data-ttu-id="a1b2c-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1b2c-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1b2c-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1b2c-116">Attributes</span></span>  
  
|<span data-ttu-id="a1b2c-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="a1b2c-117">Attribute</span></span>|<span data-ttu-id="a1b2c-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1b2c-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1b2c-119">Name</span><span class="sxs-lookup"><span data-stu-id="a1b2c-119">name</span></span>|<span data-ttu-id="a1b2c-120">Eine Zeichenfolge, die den Zustand der abonnierten Aktivität angibt, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1b2c-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1b2c-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1b2c-121">Child Elements</span></span>  
 <span data-ttu-id="a1b2c-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a1b2c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1b2c-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1b2c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a1b2c-124">Element</span><span class="sxs-lookup"><span data-stu-id="a1b2c-124">Element</span></span>|<span data-ttu-id="a1b2c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1b2c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1b2c-126">\<Status ></span><span class="sxs-lookup"><span data-stu-id="a1b2c-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="a1b2c-127">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1b2c-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1b2c-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1b2c-128">Remarks</span></span>  
 <span data-ttu-id="a1b2c-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a1b2c-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a1b2c-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a1b2c-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a1b2c-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="a1b2c-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="a1b2c-132">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a1b2c-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a1b2c-133">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="a1b2c-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1b2c-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1b2c-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="a1b2c-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a1b2c-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a1b2c-136">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a1b2c-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
