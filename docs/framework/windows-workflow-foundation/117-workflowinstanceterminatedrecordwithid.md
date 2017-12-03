---
title: 117 - WorkflowInstanceTerminatedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e68539d0-5338-468a-9f75-7e5b09d39a3c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 319b8486f91145022557ceb4e1905e55fdb828df
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="117---workflowinstanceterminatedrecordwithid"></a><span data-ttu-id="99582-102">117 - WorkflowInstanceTerminatedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="99582-102">117 - WorkflowInstanceTerminatedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="99582-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="99582-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99582-104">ID</span><span class="sxs-lookup"><span data-stu-id="99582-104">ID</span></span>|<span data-ttu-id="99582-105">117</span><span class="sxs-lookup"><span data-stu-id="99582-105">117</span></span>|  
|<span data-ttu-id="99582-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="99582-106">Keywords</span></span>|<span data-ttu-id="99582-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="99582-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="99582-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="99582-108">Level</span></span>|<span data-ttu-id="99582-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="99582-109">Error</span></span>|  
|<span data-ttu-id="99582-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="99582-110">Channel</span></span>|<span data-ttu-id="99582-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="99582-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="99582-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99582-112">Description</span></span>  
 <span data-ttu-id="99582-113">Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz WorkflowInstanceTerminatedRecord ausgibt.</span><span class="sxs-lookup"><span data-stu-id="99582-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceTerminatedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="99582-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="99582-114">Message</span></span>  
 <span data-ttu-id="99582-115">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="99582-115">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="99582-116">Details</span><span class="sxs-lookup"><span data-stu-id="99582-116">Details</span></span>  
  
|<span data-ttu-id="99582-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="99582-117">Data Item Name</span></span>|<span data-ttu-id="99582-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="99582-118">Data Item Type</span></span>|<span data-ttu-id="99582-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99582-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="99582-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="99582-120">InstanceId</span></span>|<span data-ttu-id="99582-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="99582-121">xs:GUID</span></span>|<span data-ttu-id="99582-122">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="99582-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="99582-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="99582-123">RecordNumber</span></span>|<span data-ttu-id="99582-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="99582-124">xs:long</span></span>|<span data-ttu-id="99582-125">Die Sequenznummer des ausgegebenen Datensatzes.</span><span class="sxs-lookup"><span data-stu-id="99582-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="99582-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="99582-126">EventTime</span></span>|<span data-ttu-id="99582-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="99582-127">xs:dateTime</span></span>|<span data-ttu-id="99582-128">Die Zeit in UTC, als das Ereignis ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="99582-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="99582-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="99582-129">ActivityDefinitionId</span></span>|<span data-ttu-id="99582-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="99582-130">xs:string</span></span>|<span data-ttu-id="99582-131">Der Name der Stammaktivität im Workflow.</span><span class="sxs-lookup"><span data-stu-id="99582-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="99582-132">Zustand</span><span class="sxs-lookup"><span data-stu-id="99582-132">State</span></span>|<span data-ttu-id="99582-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="99582-133">xs:string</span></span>|<span data-ttu-id="99582-134">Der aktuelle Zustand des Workflows.</span><span class="sxs-lookup"><span data-stu-id="99582-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="99582-135">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="99582-135">Annotations</span></span>|<span data-ttu-id="99582-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="99582-136">xs:string</span></span>|<span data-ttu-id="99582-137">Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="99582-137">The annotations that were added to this event.</span></span> <span data-ttu-id="99582-138">Die Werte werden in einem XML-Element im Format gespeichert \<Elemente >\< Elementname = "AnnotationName" Type = "> AnnotationValue\</item > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="99582-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="99582-139">Wenn keine Anmerkungen angegeben werden, die Zeichenfolge enthält \<Elemente / >.</span><span class="sxs-lookup"><span data-stu-id="99582-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="99582-140">Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt.</span><span class="sxs-lookup"><span data-stu-id="99582-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="99582-141">Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, und klicken Sie dann das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert mit ersetzen \<Elemente >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="99582-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="99582-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="99582-142">ProfileName</span></span>|<span data-ttu-id="99582-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="99582-143">xs:string</span></span>|<span data-ttu-id="99582-144">Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.</span><span class="sxs-lookup"><span data-stu-id="99582-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="99582-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="99582-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="99582-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="99582-146">xs:string</span></span>|<span data-ttu-id="99582-147">Die ID der Workflowdefinition.</span><span class="sxs-lookup"><span data-stu-id="99582-147">The workflow definition id</span></span>|  
|<span data-ttu-id="99582-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="99582-148">AppDomain</span></span>|<span data-ttu-id="99582-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="99582-149">xs:string</span></span>|<span data-ttu-id="99582-150">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="99582-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
