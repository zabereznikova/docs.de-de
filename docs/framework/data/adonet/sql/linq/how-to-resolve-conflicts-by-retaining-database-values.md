---
title: 'Vorgehensweise: Auflösen von Parallelitätskonflikten durch Beibehalten von Datenbankwerten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: b6f9b0308bcbf53a89ae0690ed44db0a364aef0c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191696"
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="a08b0-102">Vorgehensweise: Auflösen von Parallelitätskonflikten durch Beibehalten von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="a08b0-102">How to: Resolve Conflicts by Retaining Database Values</span></span>

<span data-ttu-id="a08b0-103">Wenn Sie Unterschiede zwischen den erwarteten und den tatsächlichen Datenbankwerten abstimmen möchten, bevor Sie versuchen, Ihre Änderungen erneut zu übergeben, können Sie die Datenbankwerte mithilfe von <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> erhalten.</span><span class="sxs-lookup"><span data-stu-id="a08b0-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="a08b0-104">Die aktuellen Werte im Objektmodell werden dann überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a08b0-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="a08b0-105">Weitere Informationen finden Sie unter vollständige Parallelität [: Übersicht](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a08b0-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a08b0-106">In allen Fällen wird der Datensatz auf dem Client erst durch Abrufen der geänderten Daten aus der Datenbank aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="a08b0-107">Diese Aktion stellt sicher, dass der nächste Updateversuch nicht bei den gleichen Parallelitätsprüfungen fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="a08b0-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a08b0-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a08b0-108">Example</span></span>  

 <span data-ttu-id="a08b0-109">In diesem Szenario wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn User1 versucht, Änderungen zu übergeben, da User2 zwischenzeitlich die Assistant-Spalte und die Department-Spalte geändert hat.</span><span class="sxs-lookup"><span data-stu-id="a08b0-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="a08b0-110">Die folgende Tabelle zeigt die Situation.</span><span class="sxs-lookup"><span data-stu-id="a08b0-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="a08b0-111">Manager</span><span class="sxs-lookup"><span data-stu-id="a08b0-111">Manager</span></span>|<span data-ttu-id="a08b0-112">Assistant</span><span class="sxs-lookup"><span data-stu-id="a08b0-112">Assistant</span></span>|<span data-ttu-id="a08b0-113">Department</span><span class="sxs-lookup"><span data-stu-id="a08b0-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="a08b0-114">Ursprünglicher Datenbankzustand bei Abfrage durch User1 und User2.</span><span class="sxs-lookup"><span data-stu-id="a08b0-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="a08b0-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="a08b0-115">Alfreds</span></span>|<span data-ttu-id="a08b0-116">Maria</span><span class="sxs-lookup"><span data-stu-id="a08b0-116">Maria</span></span>|<span data-ttu-id="a08b0-117">Sales</span><span class="sxs-lookup"><span data-stu-id="a08b0-117">Sales</span></span>|  
|<span data-ttu-id="a08b0-118">User1 bereitet sich auf die Übergabe dieser Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="a08b0-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="a08b0-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="a08b0-119">Alfred</span></span>||<span data-ttu-id="a08b0-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="a08b0-120">Marketing</span></span>|  
|<span data-ttu-id="a08b0-121">User2 hat diese Änderungen bereits übergeben.</span><span class="sxs-lookup"><span data-stu-id="a08b0-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="a08b0-122">Mary</span><span class="sxs-lookup"><span data-stu-id="a08b0-122">Mary</span></span>|<span data-ttu-id="a08b0-123">Dienst</span><span class="sxs-lookup"><span data-stu-id="a08b0-123">Service</span></span>|  
  
 <span data-ttu-id="a08b0-124">User1 entscheidet sich, diesen Konflikt zu beheben, indem die neueren Datenbankwerte die aktuellen Werte im Objektmodell überschreiben.</span><span class="sxs-lookup"><span data-stu-id="a08b0-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="a08b0-125">Wenn User1 den Konflikt durch Verwendung von <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> behebt, entspricht das Ergebnis in der Datenbank der folgenden Tabelle:</span><span class="sxs-lookup"><span data-stu-id="a08b0-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="a08b0-126">Manager</span><span class="sxs-lookup"><span data-stu-id="a08b0-126">Manager</span></span>|<span data-ttu-id="a08b0-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="a08b0-127">Assistant</span></span>|<span data-ttu-id="a08b0-128">Department</span><span class="sxs-lookup"><span data-stu-id="a08b0-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="a08b0-129">Neuer Zustand nach Konfliktlösung.</span><span class="sxs-lookup"><span data-stu-id="a08b0-129">New state after conflict resolution.</span></span>|<span data-ttu-id="a08b0-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="a08b0-130">Alfreds</span></span><br /><br /> <span data-ttu-id="a08b0-131">(Original)</span><span class="sxs-lookup"><span data-stu-id="a08b0-131">(original)</span></span>|<span data-ttu-id="a08b0-132">Mary</span><span class="sxs-lookup"><span data-stu-id="a08b0-132">Mary</span></span><br /><br /> <span data-ttu-id="a08b0-133">(von User2)</span><span class="sxs-lookup"><span data-stu-id="a08b0-133">(from User2)</span></span>|<span data-ttu-id="a08b0-134">Dienst</span><span class="sxs-lookup"><span data-stu-id="a08b0-134">Service</span></span><br /><br /> <span data-ttu-id="a08b0-135">(von User2)</span><span class="sxs-lookup"><span data-stu-id="a08b0-135">(from User2)</span></span>|  
  
 <span data-ttu-id="a08b0-136">Im folgenden Beispielcode wird gezeigt, wie die aktuellen Werte im Objektmodell mit den Datenbankwerten überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a08b0-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="a08b0-137">(Keine Inspektion oder benutzerdefinierte Behandlung einzelner Memberkonflikte.)</span><span class="sxs-lookup"><span data-stu-id="a08b0-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a08b0-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a08b0-138">See also</span></span>

- [<span data-ttu-id="a08b0-139">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="a08b0-139">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
