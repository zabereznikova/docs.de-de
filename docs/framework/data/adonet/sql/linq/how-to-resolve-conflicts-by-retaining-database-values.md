---
title: "Gewusst wie: Auflösen von Parallelitätskonflikten durch Beibehalten von Datenbankwerten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0747a4318fdab76c5fbd920f7291346d4d8ff58d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="fd4d7-102">Gewusst wie: Auflösen von Parallelitätskonflikten durch Beibehalten von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="fd4d7-102">How to: Resolve Conflicts by Retaining Database Values</span></span>
<span data-ttu-id="fd4d7-103">Wenn Sie Unterschiede zwischen den erwarteten und den tatsächlichen Datenbankwerten ausgleichen möchten, bevor Sie versuchen, Ihre Änderungen erneut zu übergeben, können Sie die Datenbankwerte mithilfe von <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> erhalten.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="fd4d7-104">Die aktuellen Werte im Objektmodell werden dann überschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="fd4d7-105">Weitere Informationen finden Sie unter [vollständige Parallelität: Übersicht über](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fd4d7-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd4d7-106">In allen Fällen wird der Datensatz auf dem Client erst durch Abrufen der geänderten Daten aus der Datenbank aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="fd4d7-107">Diese Aktion stellt sicher, dass der nächste Updateversuch nicht bei den gleichen Parallelitätsprüfungen fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd4d7-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd4d7-108">Example</span></span>  
 <span data-ttu-id="fd4d7-109">In diesem Szenario wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn User1 versucht, Änderungen zu übergeben, da User2 zwischenzeitlich die Assistant-Spalte und die Department-Spalte geändert hat.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="fd4d7-110">Die folgende Tabelle zeigt die Situation.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="fd4d7-111">Manager</span><span class="sxs-lookup"><span data-stu-id="fd4d7-111">Manager</span></span>|<span data-ttu-id="fd4d7-112">Assistant</span><span class="sxs-lookup"><span data-stu-id="fd4d7-112">Assistant</span></span>|<span data-ttu-id="fd4d7-113">Department</span><span class="sxs-lookup"><span data-stu-id="fd4d7-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="fd4d7-114">Ursprünglicher Datenbankzustand bei Abfrage durch User1 und User2.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="fd4d7-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="fd4d7-115">Alfreds</span></span>|<span data-ttu-id="fd4d7-116">Maria</span><span class="sxs-lookup"><span data-stu-id="fd4d7-116">Maria</span></span>|<span data-ttu-id="fd4d7-117">Sales</span><span class="sxs-lookup"><span data-stu-id="fd4d7-117">Sales</span></span>|  
|<span data-ttu-id="fd4d7-118">User1 bereitet sich auf die Übergabe dieser Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="fd4d7-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="fd4d7-119">Alfred</span></span>||<span data-ttu-id="fd4d7-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="fd4d7-120">Marketing</span></span>|  
|<span data-ttu-id="fd4d7-121">User2 hat diese Änderungen bereits übergeben.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="fd4d7-122">Mary</span><span class="sxs-lookup"><span data-stu-id="fd4d7-122">Mary</span></span>|<span data-ttu-id="fd4d7-123">Dienst</span><span class="sxs-lookup"><span data-stu-id="fd4d7-123">Service</span></span>|  
  
 <span data-ttu-id="fd4d7-124">User1 entscheidet sich, diesen Konflikt zu beheben, indem die neueren Datenbankwerte die aktuellen Werte im Objektmodell überschreiben.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="fd4d7-125">Wenn User1 den Konflikt durch Verwendung von <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> behebt, entspricht das Ergebnis in der Datenbank der folgenden Tabelle:</span><span class="sxs-lookup"><span data-stu-id="fd4d7-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="fd4d7-126">Manager</span><span class="sxs-lookup"><span data-stu-id="fd4d7-126">Manager</span></span>|<span data-ttu-id="fd4d7-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="fd4d7-127">Assistant</span></span>|<span data-ttu-id="fd4d7-128">Department</span><span class="sxs-lookup"><span data-stu-id="fd4d7-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="fd4d7-129">Neuer Zustand nach Konfliktlösung.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-129">New state after conflict resolution.</span></span>|<span data-ttu-id="fd4d7-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="fd4d7-130">Alfreds</span></span><br /><br /> <span data-ttu-id="fd4d7-131">(Original)</span><span class="sxs-lookup"><span data-stu-id="fd4d7-131">(original)</span></span>|<span data-ttu-id="fd4d7-132">Mary</span><span class="sxs-lookup"><span data-stu-id="fd4d7-132">Mary</span></span><br /><br /> <span data-ttu-id="fd4d7-133">(von User2)</span><span class="sxs-lookup"><span data-stu-id="fd4d7-133">(from User2)</span></span>|<span data-ttu-id="fd4d7-134">Dienst</span><span class="sxs-lookup"><span data-stu-id="fd4d7-134">Service</span></span><br /><br /> <span data-ttu-id="fd4d7-135">(von User2)</span><span class="sxs-lookup"><span data-stu-id="fd4d7-135">(from User2)</span></span>|  
  
 <span data-ttu-id="fd4d7-136">Im folgenden Beispielcode wird gezeigt, wie die aktuellen Werte im Objektmodell mit den Datenbankwerten überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fd4d7-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="fd4d7-137">(Keine Inspektion oder benutzerdefinierte Behandlung einzelner Memberkonflikte.)</span><span class="sxs-lookup"><span data-stu-id="fd4d7-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fd4d7-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd4d7-138">See Also</span></span>  
 [<span data-ttu-id="fd4d7-139">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="fd4d7-139">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
