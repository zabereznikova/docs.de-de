---
title: 'Vorgehensweise: Auflösen von Parallelitätskonflikten durch Überschreiben von Datenbankwerten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: 1dc112350451bde28d27c63961733b96f6fc84be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191709"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="c54ee-102">Vorgehensweise: Auflösen von Parallelitätskonflikten durch Überschreiben von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="c54ee-102">How to: Resolve Conflicts by Overwriting Database Values</span></span>

<span data-ttu-id="c54ee-103">Wenn Sie Unterschiede zwischen den erwarteten und den tatsächlichen Datenbankwerten abstimmen möchten, bevor Sie versuchen, Ihre Änderungen erneut zu übergeben, können Sie die Datenbankwerte mithilfe von <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c54ee-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="c54ee-104">Weitere Informationen finden Sie unter vollständige Parallelität [: Übersicht](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c54ee-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c54ee-105">In allen Fällen wird der Datensatz auf dem Client erst durch Abrufen der geänderten Daten aus der Datenbank aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c54ee-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="c54ee-106">Diese Aktion stellt sicher, dass der nächste Updateversuch nicht bei den gleichen Parallelitätsprüfungen fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c54ee-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c54ee-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c54ee-107">Example</span></span>  

 <span data-ttu-id="c54ee-108">In diesem Szenario wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn User1 versucht, Änderungen zu übergeben, da User2 zwischenzeitlich die Assistant-Spalte und die Department-Spalte geändert hat.</span><span class="sxs-lookup"><span data-stu-id="c54ee-108">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="c54ee-109">Die folgende Tabelle zeigt die Situation.</span><span class="sxs-lookup"><span data-stu-id="c54ee-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="c54ee-110">Manager</span><span class="sxs-lookup"><span data-stu-id="c54ee-110">Manager</span></span>|<span data-ttu-id="c54ee-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="c54ee-111">Assistant</span></span>|<span data-ttu-id="c54ee-112">Department</span><span class="sxs-lookup"><span data-stu-id="c54ee-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="c54ee-113">Ursprünglicher Datenbankzustand bei Abfrage durch User1 und User2.</span><span class="sxs-lookup"><span data-stu-id="c54ee-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="c54ee-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="c54ee-114">Alfreds</span></span>|<span data-ttu-id="c54ee-115">Maria</span><span class="sxs-lookup"><span data-stu-id="c54ee-115">Maria</span></span>|<span data-ttu-id="c54ee-116">Sales</span><span class="sxs-lookup"><span data-stu-id="c54ee-116">Sales</span></span>|  
|<span data-ttu-id="c54ee-117">User1 bereitet sich auf die Übergabe dieser Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="c54ee-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="c54ee-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="c54ee-118">Alfred</span></span>||<span data-ttu-id="c54ee-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="c54ee-119">Marketing</span></span>|  
|<span data-ttu-id="c54ee-120">User2 hat diese Änderungen bereits übergeben.</span><span class="sxs-lookup"><span data-stu-id="c54ee-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="c54ee-121">Mary</span><span class="sxs-lookup"><span data-stu-id="c54ee-121">Mary</span></span>|<span data-ttu-id="c54ee-122">Dienst</span><span class="sxs-lookup"><span data-stu-id="c54ee-122">Service</span></span>|  
  
 <span data-ttu-id="c54ee-123">User1 entscheidet sich, diesen Konflikt durch das Überschreiben von Datenbankwerten mit den aktuellen Clientmemberwerten zu lösen.</span><span class="sxs-lookup"><span data-stu-id="c54ee-123">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="c54ee-124">Wenn User1 den Konflikt durch Verwendung von <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> behebt, entspricht das Ergebnis in der Datenbank der folgenden Tabelle:</span><span class="sxs-lookup"><span data-stu-id="c54ee-124">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="c54ee-125">Manager</span><span class="sxs-lookup"><span data-stu-id="c54ee-125">Manager</span></span>|<span data-ttu-id="c54ee-126">Assistant</span><span class="sxs-lookup"><span data-stu-id="c54ee-126">Assistant</span></span>|<span data-ttu-id="c54ee-127">Department</span><span class="sxs-lookup"><span data-stu-id="c54ee-127">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="c54ee-128">Neuer Zustand nach Konfliktlösung.</span><span class="sxs-lookup"><span data-stu-id="c54ee-128">New state after conflict resolution.</span></span>|<span data-ttu-id="c54ee-129">Alfred</span><span class="sxs-lookup"><span data-stu-id="c54ee-129">Alfred</span></span><br /><br /> <span data-ttu-id="c54ee-130">(von User1)</span><span class="sxs-lookup"><span data-stu-id="c54ee-130">(from User1)</span></span>|<span data-ttu-id="c54ee-131">Maria</span><span class="sxs-lookup"><span data-stu-id="c54ee-131">Maria</span></span><br /><br /> <span data-ttu-id="c54ee-132">(Original)</span><span class="sxs-lookup"><span data-stu-id="c54ee-132">(original)</span></span>|<span data-ttu-id="c54ee-133">Marketing</span><span class="sxs-lookup"><span data-stu-id="c54ee-133">Marketing</span></span><br /><br /> <span data-ttu-id="c54ee-134">(von User1)</span><span class="sxs-lookup"><span data-stu-id="c54ee-134">(from User1)</span></span>|  
  
 <span data-ttu-id="c54ee-135">Im folgenden Beispielcode wird gezeigt, wie Datenbankwerte mit den aktuellen Clientmemberwerten überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c54ee-135">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="c54ee-136">(Keine Inspektion oder benutzerdefinierte Behandlung einzelner Memberkonflikte.)</span><span class="sxs-lookup"><span data-stu-id="c54ee-136">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c54ee-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c54ee-137">See also</span></span>

- [<span data-ttu-id="c54ee-138">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="c54ee-138">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
