---
title: '&lt;Argument&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: bfcb98085e0b2292d46acfd0a57096219afff606
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltargumentgt"></a><span data-ttu-id="93a44-102">&lt;Argument&gt;</span><span class="sxs-lookup"><span data-stu-id="93a44-102">&lt;argument&gt;</span></span>
<span data-ttu-id="93a44-103">Ein Konfigurationselement, das ein einer Aktivitätszustandsabfrage zugeordnetes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="93a44-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="93a44-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="93a44-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="93a44-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="93a44-105">\<system.serviceModel></span></span>  
<span data-ttu-id="93a44-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="93a44-106">\<tracking></span></span>  
<span data-ttu-id="93a44-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="93a44-107">\<trackingProfile></span></span>  
<span data-ttu-id="93a44-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="93a44-108">\<workflow></span></span>  
<span data-ttu-id="93a44-109">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="93a44-109">\<activityStateQueries></span></span>  
<span data-ttu-id="93a44-110">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="93a44-110">\<activityStateQuery></span></span>  
<span data-ttu-id="93a44-111">\<Argumente ></span><span class="sxs-lookup"><span data-stu-id="93a44-111">\<arguments></span></span>  
<span data-ttu-id="93a44-112">\<Argument ></span><span class="sxs-lookup"><span data-stu-id="93a44-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93a44-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="93a44-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93a44-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="93a44-114">Attributes and Elements</span></span>  
 <span data-ttu-id="93a44-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="93a44-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93a44-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="93a44-116">Attributes</span></span>  
  
|<span data-ttu-id="93a44-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="93a44-117">Attribute</span></span>|<span data-ttu-id="93a44-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93a44-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93a44-119">Name</span><span class="sxs-lookup"><span data-stu-id="93a44-119">name</span></span>|<span data-ttu-id="93a44-120">Eine Zeichenfolge, die den Namen des Arguments angibt.</span><span class="sxs-lookup"><span data-stu-id="93a44-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93a44-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="93a44-121">Child Elements</span></span>  
 <span data-ttu-id="93a44-122">Keine</span><span class="sxs-lookup"><span data-stu-id="93a44-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93a44-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="93a44-123">Parent Elements</span></span>  
  
|<span data-ttu-id="93a44-124">Element</span><span class="sxs-lookup"><span data-stu-id="93a44-124">Element</span></span>|<span data-ttu-id="93a44-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93a44-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93a44-126">\<Argumente ></span><span class="sxs-lookup"><span data-stu-id="93a44-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="93a44-127">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="93a44-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93a44-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93a44-128">Remarks</span></span>  
 <span data-ttu-id="93a44-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="93a44-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="93a44-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="93a44-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="93a44-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="93a44-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="93a44-132">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="93a44-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="93a44-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93a44-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="93a44-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="93a44-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="93a44-135">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="93a44-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
