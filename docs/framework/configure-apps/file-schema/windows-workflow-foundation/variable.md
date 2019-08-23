---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: a8f66f950db1edf8cd6ec21400785fb7e01b878e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947277"
---
# <a name="variable"></a><span data-ttu-id="a0fd1-101">\<Variable ></span><span class="sxs-lookup"><span data-stu-id="a0fd1-101">\<variable></span></span>
<span data-ttu-id="a0fd1-102">Stellt eine Auflistung von Variablen dar, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a0fd1-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="a0fd1-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a0fd1-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a0fd1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a0fd1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a0fd1-105">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="a0fd1-105">\<tracking></span></span>  
<span data-ttu-id="a0fd1-106">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="a0fd1-106">\<profiles></span></span>  
<span data-ttu-id="a0fd1-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a0fd1-107">\<trackingProfile></span></span>  
<span data-ttu-id="a0fd1-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a0fd1-108">\<workflow></span></span>  
<span data-ttu-id="a0fd1-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="a0fd1-109">\<activityStateQueries></span></span>  
<span data-ttu-id="a0fd1-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="a0fd1-110">\<activityStateQuery></span></span>  
<span data-ttu-id="a0fd1-111">\<Variablen ></span><span class="sxs-lookup"><span data-stu-id="a0fd1-111">\<variables></span></span>  
<span data-ttu-id="a0fd1-112">\<Variable ></span><span class="sxs-lookup"><span data-stu-id="a0fd1-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0fd1-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0fd1-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0fd1-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a0fd1-114">Attributes and Elements</span></span>  
 <span data-ttu-id="a0fd1-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0fd1-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0fd1-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0fd1-116">Attributes</span></span>  
  
|<span data-ttu-id="a0fd1-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0fd1-117">Attribute</span></span>|<span data-ttu-id="a0fd1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0fd1-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0fd1-119">Name</span><span class="sxs-lookup"><span data-stu-id="a0fd1-119">name</span></span>|<span data-ttu-id="a0fd1-120">Eine Zeichenfolge, die den Namen der Variablen angibt.</span><span class="sxs-lookup"><span data-stu-id="a0fd1-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0fd1-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0fd1-121">Child Elements</span></span>  
 <span data-ttu-id="a0fd1-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a0fd1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0fd1-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0fd1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a0fd1-124">Element</span><span class="sxs-lookup"><span data-stu-id="a0fd1-124">Element</span></span>|<span data-ttu-id="a0fd1-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0fd1-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0fd1-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="a0fd1-126">\<variable></span></span>](variable.md)|<span data-ttu-id="a0fd1-127">Eine einer Aktivitätszustandsabfrage zugeordnete Variable.</span><span class="sxs-lookup"><span data-stu-id="a0fd1-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0fd1-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0fd1-128">Remarks</span></span>  
 <span data-ttu-id="a0fd1-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a0fd1-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a0fd1-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a0fd1-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a0fd1-131">Sie können die [ \<Argumente >](arguments.md), [ \<Zustände >](states.md) und [ \<Zustände >](states.md) Elemente verwenden, um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="a0fd1-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="a0fd1-132">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a0fd1-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a0fd1-133">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mithilfe [ \<von activitystatuequery >](activitystatequery.md)abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fd1-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0fd1-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0fd1-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a0fd1-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a0fd1-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a0fd1-136">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a0fd1-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
