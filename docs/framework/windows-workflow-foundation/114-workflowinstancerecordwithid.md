---
title: 114 - WorkflowInstanceRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bd8b4a1-b210-4c07-8156-f19392318c08
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7535a37574f3f42a4de4eea8d1e1cdf67b2a995e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="114---workflowinstancerecordwithid"></a><span data-ttu-id="a89d2-102">114 - WorkflowInstanceRecordWithId</span><span class="sxs-lookup"><span data-stu-id="a89d2-102">114 - WorkflowInstanceRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="a89d2-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a89d2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a89d2-104">ID</span><span class="sxs-lookup"><span data-stu-id="a89d2-104">ID</span></span>|<span data-ttu-id="a89d2-105">114</span><span class="sxs-lookup"><span data-stu-id="a89d2-105">114</span></span>|  
|<span data-ttu-id="a89d2-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a89d2-106">Keywords</span></span>|<span data-ttu-id="a89d2-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="a89d2-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="a89d2-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a89d2-108">Level</span></span>|<span data-ttu-id="a89d2-109">Information</span><span class="sxs-lookup"><span data-stu-id="a89d2-109">Information</span></span>|  
|<span data-ttu-id="a89d2-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a89d2-110">Channel</span></span>|<span data-ttu-id="a89d2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a89d2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a89d2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a89d2-112">Description</span></span>  
 <span data-ttu-id="a89d2-113">Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz für Workflowzustände "WorkflowInstanceRecord" ausgibt: Started (Gestartet), Resumed (Wiederaufgenommen), Persisted (Beibehalten), Idle (Im Leerlauf), Deleted (Gelöscht), Completed (Abgeschlossen), Canceled (Abgebrochen), Unloaded (Entladen), Unsuspended (Fortgesetzt).</span><span class="sxs-lookup"><span data-stu-id="a89d2-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceRecord for workflow states : Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a89d2-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="a89d2-114">Message</span></span>  
 <span data-ttu-id="a89d2-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="a89d2-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="a89d2-116">Details</span><span class="sxs-lookup"><span data-stu-id="a89d2-116">Details</span></span>  
  
|<span data-ttu-id="a89d2-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a89d2-117">Data Item Name</span></span>|<span data-ttu-id="a89d2-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a89d2-118">Data Item Type</span></span>|<span data-ttu-id="a89d2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a89d2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a89d2-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a89d2-120">InstanceId</span></span>|<span data-ttu-id="a89d2-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="a89d2-121">xs:GUID</span></span>|<span data-ttu-id="a89d2-122">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="a89d2-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="a89d2-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="a89d2-123">RecordNumber</span></span>|<span data-ttu-id="a89d2-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="a89d2-124">xs:long</span></span>|<span data-ttu-id="a89d2-125">Die Sequenznummer des ausgegebenen Datensatzes.</span><span class="sxs-lookup"><span data-stu-id="a89d2-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="a89d2-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="a89d2-126">EventTime</span></span>|<span data-ttu-id="a89d2-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="a89d2-127">xs:dateTime</span></span>|<span data-ttu-id="a89d2-128">Die Zeit in UTC, als das Ereignis ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a89d2-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="a89d2-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="a89d2-129">ActivityDefinitionId</span></span>|<span data-ttu-id="a89d2-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a89d2-130">xs:string</span></span>|<span data-ttu-id="a89d2-131">Der Name der Stammaktivität im Workflow.</span><span class="sxs-lookup"><span data-stu-id="a89d2-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="a89d2-132">Zustand</span><span class="sxs-lookup"><span data-stu-id="a89d2-132">State</span></span>|<span data-ttu-id="a89d2-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="a89d2-133">xs:string</span></span>|<span data-ttu-id="a89d2-134">Der aktuelle Zustand des Workflows.</span><span class="sxs-lookup"><span data-stu-id="a89d2-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="a89d2-135">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a89d2-135">Annotations</span></span>|<span data-ttu-id="a89d2-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="a89d2-136">xs:string</span></span>|<span data-ttu-id="a89d2-137">Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="a89d2-137">The annotations that were added to this event.</span></span> <span data-ttu-id="a89d2-138">Die Werte werden in einem XML-Element im Format gespeichert \<Elemente >\< Elementname = "AnnotationName" Type = "> AnnotationValue\</item > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="a89d2-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="a89d2-139">Wenn keine Anmerkungen angegeben werden, die Zeichenfolge enthält \<Elemente / >.</span><span class="sxs-lookup"><span data-stu-id="a89d2-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="a89d2-140">Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a89d2-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="a89d2-141">Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, und klicken Sie dann das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert mit ersetzen \<Elemente >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="a89d2-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="a89d2-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="a89d2-142">ProfileName</span></span>|<span data-ttu-id="a89d2-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="a89d2-143">xs:string</span></span>|<span data-ttu-id="a89d2-144">Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.</span><span class="sxs-lookup"><span data-stu-id="a89d2-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="a89d2-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="a89d2-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="a89d2-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="a89d2-146">xs:string</span></span>|<span data-ttu-id="a89d2-147">Die ID der Workflowdefinition.</span><span class="sxs-lookup"><span data-stu-id="a89d2-147">The workflow definition id</span></span>|  
|<span data-ttu-id="a89d2-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a89d2-148">AppDomain</span></span>|<span data-ttu-id="a89d2-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="a89d2-149">xs:string</span></span>|<span data-ttu-id="a89d2-150">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a89d2-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
