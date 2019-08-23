---
title: <state> von <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 7c7326b2fd5ae39ca4c0f39fac05444802fa3d49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947492"
---
# <a name="state-of-states"></a><span data-ttu-id="00ae4-102">\<Status > von \<Zuständen ></span><span class="sxs-lookup"><span data-stu-id="00ae4-102">\<state> of \<states></span></span>
<span data-ttu-id="00ae4-103">Ein Konfigurationselement, das den Zustand der abonnierten Aktivität enthält, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="00ae4-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="00ae4-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="00ae4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="00ae4-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="00ae4-105">\<system.serviceModel></span></span>  
<span data-ttu-id="00ae4-106">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="00ae4-106">\<tracking></span></span>  
<span data-ttu-id="00ae4-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="00ae4-107">\<trackingProfile></span></span>  
<span data-ttu-id="00ae4-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="00ae4-108">\<workflow></span></span>  
<span data-ttu-id="00ae4-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="00ae4-109">\<activityStateQueries></span></span>  
<span data-ttu-id="00ae4-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="00ae4-110">\<activityStateQuery></span></span>  
<span data-ttu-id="00ae4-111">\<Status ></span><span class="sxs-lookup"><span data-stu-id="00ae4-111">\<states></span></span>  
<span data-ttu-id="00ae4-112">\<Status ></span><span class="sxs-lookup"><span data-stu-id="00ae4-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ae4-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="00ae4-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00ae4-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00ae4-114">Attributes and Elements</span></span>  
 <span data-ttu-id="00ae4-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00ae4-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00ae4-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="00ae4-116">Attributes</span></span>  
  
|<span data-ttu-id="00ae4-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="00ae4-117">Attribute</span></span>|<span data-ttu-id="00ae4-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00ae4-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00ae4-119">Name</span><span class="sxs-lookup"><span data-stu-id="00ae4-119">name</span></span>|<span data-ttu-id="00ae4-120">Eine Zeichenfolge, die den Zustand der abonnierten Aktivität angibt, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="00ae4-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00ae4-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00ae4-121">Child Elements</span></span>  
 <span data-ttu-id="00ae4-122">Keine</span><span class="sxs-lookup"><span data-stu-id="00ae4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00ae4-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00ae4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="00ae4-124">Element</span><span class="sxs-lookup"><span data-stu-id="00ae4-124">Element</span></span>|<span data-ttu-id="00ae4-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00ae4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00ae4-126">\<Status ></span><span class="sxs-lookup"><span data-stu-id="00ae4-126">\<states></span></span>](states-of-activitystatequery.md)|<span data-ttu-id="00ae4-127">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="00ae4-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00ae4-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00ae4-128">Remarks</span></span>  
 <span data-ttu-id="00ae4-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="00ae4-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="00ae4-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="00ae4-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="00ae4-131">Sie können die [ \<Argumente >](arguments.md), [ \<Zustände >](states.md) und [ \<Zustände >](states.md) Elemente verwenden, um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="00ae4-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="00ae4-132">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="00ae4-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="00ae4-133">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mithilfe [ \<von activitystatuequery >](activitystatequery.md)abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="00ae4-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00ae4-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00ae4-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="00ae4-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="00ae4-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="00ae4-136">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="00ae4-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
