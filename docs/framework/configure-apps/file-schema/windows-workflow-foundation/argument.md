---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: f2aeb61e2e72f5bd6a696c031279f2c57907166b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946144"
---
# <a name="argument"></a><span data-ttu-id="674fc-101">\<argument></span><span class="sxs-lookup"><span data-stu-id="674fc-101">\<argument></span></span>
<span data-ttu-id="674fc-102">Ein Konfigurationselement, das ein einer Aktivitätszustandsabfrage zugeordnetes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="674fc-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="674fc-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="674fc-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="674fc-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="674fc-104">\<system.serviceModel></span></span>  
<span data-ttu-id="674fc-105">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="674fc-105">\<tracking></span></span>  
<span data-ttu-id="674fc-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="674fc-106">\<trackingProfile></span></span>  
<span data-ttu-id="674fc-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="674fc-107">\<workflow></span></span>  
<span data-ttu-id="674fc-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="674fc-108">\<activityStateQueries></span></span>  
<span data-ttu-id="674fc-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="674fc-109">\<activityStateQuery></span></span>  
<span data-ttu-id="674fc-110">\<arguments></span><span class="sxs-lookup"><span data-stu-id="674fc-110">\<arguments></span></span>  
<span data-ttu-id="674fc-111">\<argument></span><span class="sxs-lookup"><span data-stu-id="674fc-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="674fc-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="674fc-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="674fc-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="674fc-113">Attributes and Elements</span></span>  
 <span data-ttu-id="674fc-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="674fc-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="674fc-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="674fc-115">Attributes</span></span>  
  
|<span data-ttu-id="674fc-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="674fc-116">Attribute</span></span>|<span data-ttu-id="674fc-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="674fc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="674fc-118">Name</span><span class="sxs-lookup"><span data-stu-id="674fc-118">name</span></span>|<span data-ttu-id="674fc-119">Eine Zeichenfolge, die den Namen des Arguments angibt.</span><span class="sxs-lookup"><span data-stu-id="674fc-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="674fc-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="674fc-120">Child Elements</span></span>  
 <span data-ttu-id="674fc-121">Keine</span><span class="sxs-lookup"><span data-stu-id="674fc-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="674fc-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="674fc-122">Parent Elements</span></span>  
  
|<span data-ttu-id="674fc-123">Element</span><span class="sxs-lookup"><span data-stu-id="674fc-123">Element</span></span>|<span data-ttu-id="674fc-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="674fc-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="674fc-125">\<arguments></span><span class="sxs-lookup"><span data-stu-id="674fc-125">\<arguments></span></span>](arguments.md)|<span data-ttu-id="674fc-126">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="674fc-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="674fc-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="674fc-127">Remarks</span></span>  
 <span data-ttu-id="674fc-128">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="674fc-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="674fc-129">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="674fc-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="674fc-130">Sie können die [ \<Argumente >](arguments.md), [ \<Zustände >](states.md) und [ \<Zustände >](states.md) Elemente verwenden, um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="674fc-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="674fc-131">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="674fc-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="674fc-132">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mithilfe [ \<von activitystatuequery >](activitystatequery.md)abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="674fc-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="674fc-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="674fc-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="674fc-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="674fc-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="674fc-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="674fc-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
