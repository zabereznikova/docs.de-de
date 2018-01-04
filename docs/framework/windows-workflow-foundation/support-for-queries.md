---
title: "Unterstützung für Abfragen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f20e9fbcad31a3924474793d9107d6a3c4aeef27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="support-for-queries"></a><span data-ttu-id="6d5d8-102">Unterstützung für Abfragen</span><span class="sxs-lookup"><span data-stu-id="6d5d8-102">Support for Queries</span></span>
<span data-ttu-id="6d5d8-103">Der SQL-Workflowinstanzspeicher zeichnet einen Satz bekannter Eigenschaften im Speicher auf.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="6d5d8-104">Benutzer können Instanzen auf Grundlage dieser Eigenschaften abfragen.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="6d5d8-105">Die folgende Liste enthält einige dieser bekannten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="6d5d8-105">The following list contains some of these well-known properties:</span></span>  
  
-   <span data-ttu-id="6d5d8-106">**Name der Website.**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-106">**Site Name.**</span></span> <span data-ttu-id="6d5d8-107">Der Name der Website, die den Dienst enthält.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-107">Name of the Web site that contains the service.</span></span>  
  
-   <span data-ttu-id="6d5d8-108">**Relativen Pfad.**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-108">**Relative Application Path.**</span></span> <span data-ttu-id="6d5d8-109">Der Pfad der Anwendung relativ zur Website.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-109">Path of the application relative to the Web site.</span></span>  
  
-   <span data-ttu-id="6d5d8-110">**Relativen Pfad.**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-110">**Relative Service Path.**</span></span> <span data-ttu-id="6d5d8-111">Der Pfad des Diensts relativ zur Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-111">Path of the service relative to the application.</span></span>  
  
-   <span data-ttu-id="6d5d8-112">**Service Name.**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-112">**Service Name.**</span></span> <span data-ttu-id="6d5d8-113">Name des Diensts.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-113">Name of the service.</span></span>  
  
-   <span data-ttu-id="6d5d8-114">**Dienst-Namespace.**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-114">**Service Namespace.**</span></span> <span data-ttu-id="6d5d8-115">Der Name des vom Dienst verwendeten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-115">Name of the namespace that the service uses.</span></span>  
  
-   <span data-ttu-id="6d5d8-116">**Aktuellen Computer.**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-116">**Current Machine.**</span></span>  
  
-   <span data-ttu-id="6d5d8-117">**Letzte Computer**.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-117">**Last Machine**.</span></span> <span data-ttu-id="6d5d8-118">Der Computer, auf dem die Workflowdienstinstanz das letzte Mal ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d5d8-119">Für selbst gehostete Szenarios mit dem Workflowdiensthost werden nur die letzten vier Eigenschaften aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="6d5d8-120">Für Workflowanwendungsszenarios wird nur die letzte Eigenschaft aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="6d5d8-121">Die Workflowlaufzeit stellt Werte für die ersten drei Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="6d5d8-122">Der Workflowdiensthost gibt den Wert für die **Suspend Reason** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="6d5d8-123">Der SQL-Workflowinstanzspeicher selbst gibt Werte für die **Last Updated Machine** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="6d5d8-124">Der SQL-Workflowinstanzspeicher lässt Sie darüber hinaus die benutzerdefinierten Eigenschaften angeben, für die Sie die Werte in der Persistenzdatenbank speichern und die Sie in Abfragen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="6d5d8-125">Weitere Informationen zu benutzerdefinierten Werbeaktionen, finden Sie unter [Store Erweiterbarkeit](../../../docs/framework/windows-workflow-foundation/store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="6d5d8-125">For more information about custom promotions, see [Store Extensibility](../../../docs/framework/windows-workflow-foundation/store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="6d5d8-126">Ansichten</span><span class="sxs-lookup"><span data-stu-id="6d5d8-126">Views</span></span>  
 <span data-ttu-id="6d5d8-127">Der Instanzspeicher enthält die folgenden Ansichten.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-127">The instance store contains the following views.</span></span> <span data-ttu-id="6d5d8-128">Finden Sie unter [Persistenzdatenbankschema](../../../docs/framework/windows-workflow-foundation/persistence-database-schema.md) Weitere Details.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-128">See [Persistence Database Schema](../../../docs/framework/windows-workflow-foundation/persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="6d5d8-129">Die Ansicht "Instances"</span><span class="sxs-lookup"><span data-stu-id="6d5d8-129">The Instances View</span></span>  
 <span data-ttu-id="6d5d8-130">Die Ansicht "Instances" enthält die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="6d5d8-130">The Instances view contains the following fields:</span></span>  
  
1.  <span data-ttu-id="6d5d8-131">**Id**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-131">**Id**</span></span>  
  
2.  <span data-ttu-id="6d5d8-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-132">**PendingTimer**</span></span>  
  
3.  <span data-ttu-id="6d5d8-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-133">**CreationTime**</span></span>  
  
4.  <span data-ttu-id="6d5d8-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-134">**LastUpdatedTime**</span></span>  
  
5.  <span data-ttu-id="6d5d8-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-135">**ServiceDeploymentId**</span></span>  
  
6.  <span data-ttu-id="6d5d8-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-136">**SuspensionExceptionName**</span></span>  
  
7.  <span data-ttu-id="6d5d8-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-137">**SuspensionReason**</span></span>  
  
8.  <span data-ttu-id="6d5d8-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="6d5d8-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="6d5d8-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="6d5d8-141">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="6d5d8-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="6d5d8-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="6d5d8-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="6d5d8-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="6d5d8-146">**"Readwriteprimitivedataproperties"-Spalte**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="6d5d8-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="6d5d8-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="6d5d8-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="6d5d8-150">Die Ansicht "ServiceDeployments"</span><span class="sxs-lookup"><span data-stu-id="6d5d8-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="6d5d8-151">Die Ansicht "ServiceDeployments" enthält die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="6d5d8-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1.  <span data-ttu-id="6d5d8-152">**SiteName**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-152">**SiteName**</span></span>  
  
2.  <span data-ttu-id="6d5d8-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-153">**RelativeServicePath**</span></span>  
  
3.  <span data-ttu-id="6d5d8-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-154">**RelativeApplicationPath**</span></span>  
  
4.  <span data-ttu-id="6d5d8-155">**Dienstname**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-155">**ServiceName**</span></span>  
  
5.  <span data-ttu-id="6d5d8-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="6d5d8-157">Die Ansicht "InstancePromotedProperties"</span><span class="sxs-lookup"><span data-stu-id="6d5d8-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="6d5d8-158">Die Ansicht "InstancePromotedProperties" enthält die folgenden Felder.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="6d5d8-159">Ausführliche Informationen zum höher gestuften Eigenschaften finden Sie unter der [Store Erweiterbarkeit](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="6d5d8-159">For details on promoted properties, see the [Store Extensibility](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) topic.</span></span>  
  
1.  <span data-ttu-id="6d5d8-160">**Instanz-ID**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-160">**InstanceId**</span></span>  
  
2.  <span data-ttu-id="6d5d8-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-161">**EncodingOption**</span></span>  
  
3.  <span data-ttu-id="6d5d8-162">**Mit dem PromotionName**</span><span class="sxs-lookup"><span data-stu-id="6d5d8-162">**PromotionName**</span></span>  
  
4.  <span data-ttu-id="6d5d8-163">**Value#** (ein Wertebereich von **Value1** auf **Value64**).</span><span class="sxs-lookup"><span data-stu-id="6d5d8-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
