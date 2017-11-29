---
title: '&lt;Argument&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61e93aa956aee16469fa0d276e749d08049e1cd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltargumentgt"></a><span data-ttu-id="53c58-102">&lt;Argument&gt;</span><span class="sxs-lookup"><span data-stu-id="53c58-102">&lt;argument&gt;</span></span>
<span data-ttu-id="53c58-103">Ein Konfigurationselement, das ein einer Aktivitätszustandsabfrage zugeordnetes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="53c58-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="53c58-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="53c58-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="53c58-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="53c58-105">\<system.serviceModel></span></span>  
<span data-ttu-id="53c58-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="53c58-106">\<tracking></span></span>  
<span data-ttu-id="53c58-107">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="53c58-107">\<trackingProfile></span></span>  
<span data-ttu-id="53c58-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="53c58-108">\<workflow></span></span>  
<span data-ttu-id="53c58-109">\<ActivityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="53c58-109">\<activityStateQueries></span></span>  
<span data-ttu-id="53c58-110">\<ActivityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="53c58-110">\<activityStateQuery></span></span>  
<span data-ttu-id="53c58-111">\<Argumente ></span><span class="sxs-lookup"><span data-stu-id="53c58-111">\<arguments></span></span>  
<span data-ttu-id="53c58-112">\<Argument ></span><span class="sxs-lookup"><span data-stu-id="53c58-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53c58-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="53c58-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53c58-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="53c58-114">Attributes and Elements</span></span>  
 <span data-ttu-id="53c58-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="53c58-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53c58-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="53c58-116">Attributes</span></span>  
  
|<span data-ttu-id="53c58-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="53c58-117">Attribute</span></span>|<span data-ttu-id="53c58-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53c58-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53c58-119">Name</span><span class="sxs-lookup"><span data-stu-id="53c58-119">name</span></span>|<span data-ttu-id="53c58-120">Eine Zeichenfolge, die den Namen des Arguments angibt.</span><span class="sxs-lookup"><span data-stu-id="53c58-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53c58-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53c58-121">Child Elements</span></span>  
 <span data-ttu-id="53c58-122">Keine</span><span class="sxs-lookup"><span data-stu-id="53c58-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53c58-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53c58-123">Parent Elements</span></span>  
  
|<span data-ttu-id="53c58-124">Element</span><span class="sxs-lookup"><span data-stu-id="53c58-124">Element</span></span>|<span data-ttu-id="53c58-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53c58-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53c58-126">\<Argumente ></span><span class="sxs-lookup"><span data-stu-id="53c58-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="53c58-127">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="53c58-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53c58-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53c58-128">Remarks</span></span>  
 <span data-ttu-id="53c58-129">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="53c58-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="53c58-130">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="53c58-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="53c58-131">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="53c58-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="53c58-132">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="53c58-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="53c58-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53c58-133">See Also</span></span>  
 <span data-ttu-id="53c58-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="53c58-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="53c58-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="53c58-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="53c58-136">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="53c58-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="53c58-137">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="53c58-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
