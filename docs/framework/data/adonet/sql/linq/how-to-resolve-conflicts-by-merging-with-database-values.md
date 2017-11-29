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
ms.openlocfilehash: 8e5114052951950c5866d80c974555678b1d040a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="470cc-102">Gewusst wie: Auflösen von Parallelitätskonflikten durch Zusammenführen von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="470cc-102">How to: Resolve Conflicts by Merging with Database Values</span></span>
<span data-ttu-id="470cc-103">Wenn Sie vor dem erneuten Übergeben Ihrer Änderungen die Unterschiede zwischen erwarteten und tatsächlichen Datenbankwerten ausgleichen möchten, können Sie mit <xref:System.Data.Linq.RefreshMode.KeepChanges> Datenbankwerte mit den aktuellen Clientmemberwerten zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="470cc-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="470cc-104">Weitere Informationen finden Sie unter [vollständige Parallelität: Übersicht über](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="470cc-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="470cc-105">In allen Fällen wird der Datensatz auf dem Client erst durch Abrufen der geänderten Daten aus der Datenbank aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="470cc-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="470cc-106">Diese Aktion stellt sicher, dass der nächste Updateversuch nicht bei den gleichen Parallelitätsprüfungen fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="470cc-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="470cc-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="470cc-107">Example</span></span>  
 <span data-ttu-id="470cc-108">In diesem Szenario wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn User1 versucht, Änderungen zu übergeben, da User2 zwischenzeitlich die Assistant-Spalte und die Department-Spalte geändert hat.</span><span class="sxs-lookup"><span data-stu-id="470cc-108">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="470cc-109">Die folgende Tabelle zeigt die Situation.</span><span class="sxs-lookup"><span data-stu-id="470cc-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="470cc-110">Manager</span><span class="sxs-lookup"><span data-stu-id="470cc-110">Manager</span></span>|<span data-ttu-id="470cc-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="470cc-111">Assistant</span></span>|<span data-ttu-id="470cc-112">Department</span><span class="sxs-lookup"><span data-stu-id="470cc-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="470cc-113">Ursprünglicher Datenbankzustand bei Abfrage durch User1 und User2.</span><span class="sxs-lookup"><span data-stu-id="470cc-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="470cc-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="470cc-114">Alfreds</span></span>|<span data-ttu-id="470cc-115">Maria</span><span class="sxs-lookup"><span data-stu-id="470cc-115">Maria</span></span>|<span data-ttu-id="470cc-116">Sales</span><span class="sxs-lookup"><span data-stu-id="470cc-116">Sales</span></span>|  
|<span data-ttu-id="470cc-117">User1 bereitet sich auf die Übergabe dieser Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="470cc-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="470cc-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="470cc-118">Alfred</span></span>||<span data-ttu-id="470cc-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="470cc-119">Marketing</span></span>|  
|<span data-ttu-id="470cc-120">User2 hat diese Änderungen bereits übergeben.</span><span class="sxs-lookup"><span data-stu-id="470cc-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="470cc-121">Mary</span><span class="sxs-lookup"><span data-stu-id="470cc-121">Mary</span></span>|<span data-ttu-id="470cc-122">Dienst</span><span class="sxs-lookup"><span data-stu-id="470cc-122">Service</span></span>|  
  
 <span data-ttu-id="470cc-123">User1 entscheidet sich, diesen Konflikt durch das Zusammenführen von Datenbankwerten mit den aktuellen Clientmemberwerten zu lösen.</span><span class="sxs-lookup"><span data-stu-id="470cc-123">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="470cc-124">Im Ergebnis werden die Datenbankwerte nur dann überschrieben, wenn der aktuelle Änderungssatz diese Werte ebenfalls verändert hat.</span><span class="sxs-lookup"><span data-stu-id="470cc-124">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="470cc-125">Wenn User1 den Konflikt durch Verwendung von <xref:System.Data.Linq.RefreshMode.KeepChanges> behebt, entspricht das Ergebnis in der Datenbank der folgenden Tabelle:</span><span class="sxs-lookup"><span data-stu-id="470cc-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="470cc-126">Manager</span><span class="sxs-lookup"><span data-stu-id="470cc-126">Manager</span></span>|<span data-ttu-id="470cc-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="470cc-127">Assistant</span></span>|<span data-ttu-id="470cc-128">Department</span><span class="sxs-lookup"><span data-stu-id="470cc-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="470cc-129">Neuer Zustand nach Konfliktlösung.</span><span class="sxs-lookup"><span data-stu-id="470cc-129">New state after conflict resolution.</span></span>|<span data-ttu-id="470cc-130">Alfred</span><span class="sxs-lookup"><span data-stu-id="470cc-130">Alfred</span></span><br /><br /> <span data-ttu-id="470cc-131">(von User1)</span><span class="sxs-lookup"><span data-stu-id="470cc-131">(from User1)</span></span>|<span data-ttu-id="470cc-132">Mary</span><span class="sxs-lookup"><span data-stu-id="470cc-132">Mary</span></span><br /><br /> <span data-ttu-id="470cc-133">(von User2)</span><span class="sxs-lookup"><span data-stu-id="470cc-133">(from User2)</span></span>|<span data-ttu-id="470cc-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="470cc-134">Marketing</span></span><br /><br /> <span data-ttu-id="470cc-135">(von User1)</span><span class="sxs-lookup"><span data-stu-id="470cc-135">(from User1)</span></span>|  
  
 <span data-ttu-id="470cc-136">Im folgenden Beispielcode wird gezeigt, wie Datenbankwerte mit den aktuellen Clientmemberwerten zusammengeführt werden (sofern der Client den Wert nicht ebenfalls geändert hat).</span><span class="sxs-lookup"><span data-stu-id="470cc-136">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="470cc-137">Keine Inspektion oder benutzerdefinierte Behandlung einzelner Memberkonflikte.</span><span class="sxs-lookup"><span data-stu-id="470cc-137">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="470cc-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="470cc-138">See Also</span></span>  
 [<span data-ttu-id="470cc-139">Vorgehensweise: Lösen von Konflikten durch Überschreiben von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="470cc-139">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 [<span data-ttu-id="470cc-140">Vorgehensweise: Auflösen von Parallelitätskonflikten durch Beibehalten von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="470cc-140">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 [<span data-ttu-id="470cc-141">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="470cc-141">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
