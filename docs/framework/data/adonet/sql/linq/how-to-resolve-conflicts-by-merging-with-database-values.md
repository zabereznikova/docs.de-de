---
title: "Gewusst wie: Auflösen von Parallelitätskonflikten durch Zusammenführen von Datenbankwerten"
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
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ee1016a6dc20e58bfafc434617a36f8f8703a3bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="9c5ad-102">Gewusst wie: Auflösen von Parallelitätskonflikten durch Zusammenführen von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="9c5ad-102">How to: Resolve Conflicts by Merging with Database Values</span></span>
<span data-ttu-id="9c5ad-103">Wenn Sie vor dem erneuten Übergeben Ihrer Änderungen die Unterschiede zwischen erwarteten und tatsächlichen Datenbankwerten ausgleichen möchten, können Sie mit <xref:System.Data.Linq.RefreshMode.KeepChanges> Datenbankwerte mit den aktuellen Clientmemberwerten zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="9c5ad-104">Weitere Informationen finden Sie unter [vollständige Parallelität: Übersicht über](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9c5ad-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c5ad-105">In allen Fällen wird der Datensatz auf dem Client erst durch Abrufen der geänderten Daten aus der Datenbank aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="9c5ad-106">Diese Aktion stellt sicher, dass der nächste Updateversuch nicht bei den gleichen Parallelitätsprüfungen fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c5ad-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c5ad-107">Example</span></span>  
 <span data-ttu-id="9c5ad-108">In diesem Szenario wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn User1 versucht, Änderungen zu übergeben, da User2 zwischenzeitlich die Assistant-Spalte und die Department-Spalte geändert hat.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-108">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="9c5ad-109">Die folgende Tabelle zeigt die Situation.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="9c5ad-110">Manager</span><span class="sxs-lookup"><span data-stu-id="9c5ad-110">Manager</span></span>|<span data-ttu-id="9c5ad-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="9c5ad-111">Assistant</span></span>|<span data-ttu-id="9c5ad-112">Department</span><span class="sxs-lookup"><span data-stu-id="9c5ad-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="9c5ad-113">Ursprünglicher Datenbankzustand bei Abfrage durch User1 und User2.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="9c5ad-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="9c5ad-114">Alfreds</span></span>|<span data-ttu-id="9c5ad-115">Maria</span><span class="sxs-lookup"><span data-stu-id="9c5ad-115">Maria</span></span>|<span data-ttu-id="9c5ad-116">Sales</span><span class="sxs-lookup"><span data-stu-id="9c5ad-116">Sales</span></span>|  
|<span data-ttu-id="9c5ad-117">User1 bereitet sich auf die Übergabe dieser Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="9c5ad-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="9c5ad-118">Alfred</span></span>||<span data-ttu-id="9c5ad-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="9c5ad-119">Marketing</span></span>|  
|<span data-ttu-id="9c5ad-120">User2 hat diese Änderungen bereits übergeben.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="9c5ad-121">Mary</span><span class="sxs-lookup"><span data-stu-id="9c5ad-121">Mary</span></span>|<span data-ttu-id="9c5ad-122">Dienst</span><span class="sxs-lookup"><span data-stu-id="9c5ad-122">Service</span></span>|  
  
 <span data-ttu-id="9c5ad-123">User1 entscheidet sich, diesen Konflikt durch das Zusammenführen von Datenbankwerten mit den aktuellen Clientmemberwerten zu lösen.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-123">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="9c5ad-124">Im Ergebnis werden die Datenbankwerte nur dann überschrieben, wenn der aktuelle Änderungssatz diese Werte ebenfalls verändert hat.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-124">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="9c5ad-125">Wenn User1 den Konflikt durch Verwendung von <xref:System.Data.Linq.RefreshMode.KeepChanges> behebt, entspricht das Ergebnis in der Datenbank der folgenden Tabelle:</span><span class="sxs-lookup"><span data-stu-id="9c5ad-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="9c5ad-126">Manager</span><span class="sxs-lookup"><span data-stu-id="9c5ad-126">Manager</span></span>|<span data-ttu-id="9c5ad-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="9c5ad-127">Assistant</span></span>|<span data-ttu-id="9c5ad-128">Department</span><span class="sxs-lookup"><span data-stu-id="9c5ad-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="9c5ad-129">Neuer Zustand nach Konfliktlösung.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-129">New state after conflict resolution.</span></span>|<span data-ttu-id="9c5ad-130">Alfred</span><span class="sxs-lookup"><span data-stu-id="9c5ad-130">Alfred</span></span><br /><br /> <span data-ttu-id="9c5ad-131">(von User1)</span><span class="sxs-lookup"><span data-stu-id="9c5ad-131">(from User1)</span></span>|<span data-ttu-id="9c5ad-132">Mary</span><span class="sxs-lookup"><span data-stu-id="9c5ad-132">Mary</span></span><br /><br /> <span data-ttu-id="9c5ad-133">(von User2)</span><span class="sxs-lookup"><span data-stu-id="9c5ad-133">(from User2)</span></span>|<span data-ttu-id="9c5ad-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="9c5ad-134">Marketing</span></span><br /><br /> <span data-ttu-id="9c5ad-135">(von User1)</span><span class="sxs-lookup"><span data-stu-id="9c5ad-135">(from User1)</span></span>|  
  
 <span data-ttu-id="9c5ad-136">Im folgenden Beispielcode wird gezeigt, wie Datenbankwerte mit den aktuellen Clientmemberwerten zusammengeführt werden (sofern der Client den Wert nicht ebenfalls geändert hat).</span><span class="sxs-lookup"><span data-stu-id="9c5ad-136">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="9c5ad-137">Keine Inspektion oder benutzerdefinierte Behandlung einzelner Memberkonflikte.</span><span class="sxs-lookup"><span data-stu-id="9c5ad-137">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9c5ad-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c5ad-138">See Also</span></span>  
 [<span data-ttu-id="9c5ad-139">Vorgehensweise: Auflösen von Parallelitätskonflikten durch Überschreiben von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="9c5ad-139">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 [<span data-ttu-id="9c5ad-140">Vorgehensweise: Auflösen von Parallelitätskonflikten durch Beibehalten von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="9c5ad-140">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 [<span data-ttu-id="9c5ad-141">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="9c5ad-141">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
