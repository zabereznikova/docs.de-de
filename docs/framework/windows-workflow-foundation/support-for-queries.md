---
title: Unterstützung für Abfragen
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: 350644de4a5deb7b8dcb5133c9cc2edb477fd355
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258438"
---
# <a name="support-for-queries"></a><span data-ttu-id="d6b11-102">Unterstützung für Abfragen</span><span class="sxs-lookup"><span data-stu-id="d6b11-102">Support for Queries</span></span>

<span data-ttu-id="d6b11-103">Der SQL-Workflowinstanzspeicher zeichnet einen Satz bekannter Eigenschaften im Speicher auf.</span><span class="sxs-lookup"><span data-stu-id="d6b11-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="d6b11-104">Benutzer können Instanzen auf Grundlage dieser Eigenschaften abfragen.</span><span class="sxs-lookup"><span data-stu-id="d6b11-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="d6b11-105">Die folgende Liste enthält einige dieser bekannten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d6b11-105">The following list contains some of these well-known properties:</span></span>  
  
- <span data-ttu-id="d6b11-106">**Der Name der Website.**</span><span class="sxs-lookup"><span data-stu-id="d6b11-106">**Site Name.**</span></span> <span data-ttu-id="d6b11-107">Der Name der Website, die den Dienst enthält.</span><span class="sxs-lookup"><span data-stu-id="d6b11-107">Name of the Web site that contains the service.</span></span>  
  
- <span data-ttu-id="d6b11-108">**Relative Application Path.**</span><span class="sxs-lookup"><span data-stu-id="d6b11-108">**Relative Application Path.**</span></span> <span data-ttu-id="d6b11-109">Der Pfad der Anwendung relativ zur Website.</span><span class="sxs-lookup"><span data-stu-id="d6b11-109">Path of the application relative to the Web site.</span></span>  
  
- <span data-ttu-id="d6b11-110">**Relative Service Path.**</span><span class="sxs-lookup"><span data-stu-id="d6b11-110">**Relative Service Path.**</span></span> <span data-ttu-id="d6b11-111">Der Pfad des Diensts relativ zur Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d6b11-111">Path of the service relative to the application.</span></span>  
  
- <span data-ttu-id="d6b11-112">**Der Dienst Name.**</span><span class="sxs-lookup"><span data-stu-id="d6b11-112">**Service Name.**</span></span> <span data-ttu-id="d6b11-113">Der Name des Diensts.</span><span class="sxs-lookup"><span data-stu-id="d6b11-113">Name of the service.</span></span>  
  
- <span data-ttu-id="d6b11-114">**Dienst Namespace.**</span><span class="sxs-lookup"><span data-stu-id="d6b11-114">**Service Namespace.**</span></span> <span data-ttu-id="d6b11-115">Der Name des vom Dienst verwendeten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="d6b11-115">Name of the namespace that the service uses.</span></span>  
  
- <span data-ttu-id="d6b11-116">**Current Machine.**</span><span class="sxs-lookup"><span data-stu-id="d6b11-116">**Current Machine.**</span></span>  
  
- <span data-ttu-id="d6b11-117">**Letzter Computer**.</span><span class="sxs-lookup"><span data-stu-id="d6b11-117">**Last Machine**.</span></span> <span data-ttu-id="d6b11-118">Der Computer, auf dem die Workflowdienstinstanz das letzte Mal ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6b11-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6b11-119">Für selbst gehostete Szenarios mit dem Workflowdiensthost werden nur die letzten vier Eigenschaften aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d6b11-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="d6b11-120">Für Workflowanwendungsszenarios wird nur die letzte Eigenschaft aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d6b11-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="d6b11-121">Die Workflowlaufzeit stellt Werte für die ersten drei Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="d6b11-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="d6b11-122">Der Workflow Dienst Host gibt den Wert für die Eigenschaft " **Suspend Reason** " an.</span><span class="sxs-lookup"><span data-stu-id="d6b11-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="d6b11-123">Der SQL-workflowinstanzspeicher selbst stellt Werte für die **zuletzt aktualisierte Computer** Eigenschaft bereit.</span><span class="sxs-lookup"><span data-stu-id="d6b11-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="d6b11-124">Der SQL-Workflowinstanzspeicher lässt Sie darüber hinaus die benutzerdefinierten Eigenschaften angeben, für die Sie die Werte in der Persistenzdatenbank speichern und die Sie in Abfragen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d6b11-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="d6b11-125">Weitere Informationen zu benutzerdefinierten Aktionen finden Sie unter [Store-Erweiterbarkeit](store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="d6b11-125">For more information about custom promotions, see [Store Extensibility](store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="d6b11-126">Sichten</span><span class="sxs-lookup"><span data-stu-id="d6b11-126">Views</span></span>  

 <span data-ttu-id="d6b11-127">Der Instanzspeicher enthält die folgenden Ansichten.</span><span class="sxs-lookup"><span data-stu-id="d6b11-127">The instance store contains the following views.</span></span> <span data-ttu-id="d6b11-128">Weitere Informationen finden Sie unter [persistenzdatenbankschema](persistence-database-schema.md) .</span><span class="sxs-lookup"><span data-stu-id="d6b11-128">See [Persistence Database Schema](persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="d6b11-129">Die Ansicht "Instances"</span><span class="sxs-lookup"><span data-stu-id="d6b11-129">The Instances View</span></span>  

 <span data-ttu-id="d6b11-130">Die Ansicht "Instances" enthält die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="d6b11-130">The Instances view contains the following fields:</span></span>  
  
1. <span data-ttu-id="d6b11-131">**Id**</span><span class="sxs-lookup"><span data-stu-id="d6b11-131">**Id**</span></span>  
  
2. <span data-ttu-id="d6b11-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="d6b11-132">**PendingTimer**</span></span>  
  
3. <span data-ttu-id="d6b11-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="d6b11-133">**CreationTime**</span></span>  
  
4. <span data-ttu-id="d6b11-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="d6b11-134">**LastUpdatedTime**</span></span>  
  
5. <span data-ttu-id="d6b11-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="d6b11-135">**ServiceDeploymentId**</span></span>  
  
6. <span data-ttu-id="d6b11-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="d6b11-136">**SuspensionExceptionName**</span></span>  
  
7. <span data-ttu-id="d6b11-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="d6b11-137">**SuspensionReason**</span></span>  
  
8. <span data-ttu-id="d6b11-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="d6b11-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="d6b11-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="d6b11-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="d6b11-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="d6b11-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="d6b11-141">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="d6b11-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="d6b11-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="d6b11-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="d6b11-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="d6b11-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="d6b11-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="d6b11-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="d6b11-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="d6b11-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="d6b11-146">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="d6b11-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="d6b11-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="d6b11-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="d6b11-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="d6b11-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="d6b11-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="d6b11-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="d6b11-150">Die Ansicht "ServiceDeployments"</span><span class="sxs-lookup"><span data-stu-id="d6b11-150">The ServiceDeployments view</span></span>  

 <span data-ttu-id="d6b11-151">Die Ansicht "ServiceDeployments" enthält die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="d6b11-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1. <span data-ttu-id="d6b11-152">**Sitename**</span><span class="sxs-lookup"><span data-stu-id="d6b11-152">**SiteName**</span></span>  
  
2. <span data-ttu-id="d6b11-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="d6b11-153">**RelativeServicePath**</span></span>  
  
3. <span data-ttu-id="d6b11-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="d6b11-154">**RelativeApplicationPath**</span></span>  
  
4. <span data-ttu-id="d6b11-155">**Service Name**</span><span class="sxs-lookup"><span data-stu-id="d6b11-155">**ServiceName**</span></span>  
  
5. <span data-ttu-id="d6b11-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="d6b11-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="d6b11-157">Die Ansicht "InstancePromotedProperties"</span><span class="sxs-lookup"><span data-stu-id="d6b11-157">The InstancePromotedProperties view</span></span>  

 <span data-ttu-id="d6b11-158">Die Ansicht "InstancePromotedProperties" enthält die folgenden Felder.</span><span class="sxs-lookup"><span data-stu-id="d6b11-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="d6b11-159">Ausführliche Informationen zu höher gestuften Eigenschaften finden Sie im Thema [Store-Erweiterbarkeit](store-extensibility.md) .</span><span class="sxs-lookup"><span data-stu-id="d6b11-159">For details on promoted properties, see the [Store Extensibility](store-extensibility.md) topic.</span></span>  
  
1. <span data-ttu-id="d6b11-160">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="d6b11-160">**InstanceId**</span></span>  
  
2. <span data-ttu-id="d6b11-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="d6b11-161">**EncodingOption**</span></span>  
  
3. <span data-ttu-id="d6b11-162">**PromotionName**</span><span class="sxs-lookup"><span data-stu-id="d6b11-162">**PromotionName**</span></span>  
  
4. <span data-ttu-id="d6b11-163">**Wert #** (ein Bereich von Feldern von **value1** bis **Value64**).</span><span class="sxs-lookup"><span data-stu-id="d6b11-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
