---
title: 'Vorgehensweise: Auflösen von Parallelitätskonflikten durch Überschreiben von Datenbankwerten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: 7b8d7cf8ab2335c064062ed3ab4072d81e8042fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189117"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="9c37f-102">Vorgehensweise: Auflösen von Parallelitätskonflikten durch Überschreiben von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="9c37f-102">How to: Resolve Conflicts by Overwriting Database Values</span></span>
<span data-ttu-id="9c37f-103">Wenn Sie Unterschiede zwischen den erwarteten und den tatsächlichen Datenbankwerten abstimmen möchten, bevor Sie versuchen, Ihre Änderungen erneut zu übergeben, können Sie die Datenbankwerte mithilfe von <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9c37f-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="9c37f-104">Weitere Informationen finden Sie unter [optimistische Parallelität: Übersicht über die](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9c37f-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c37f-105">In allen Fällen wird der Datensatz auf dem Client erst durch Abrufen der geänderten Daten aus der Datenbank aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9c37f-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="9c37f-106">Diese Aktion stellt sicher, dass der nächste Updateversuch nicht bei den gleichen Parallelitätsprüfungen fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="9c37f-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c37f-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c37f-107">Example</span></span>  
 <span data-ttu-id="9c37f-108">In diesem Szenario wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn User1 versucht, Änderungen zu übergeben, da User2 zwischenzeitlich die Assistant-Spalte und die Department-Spalte geändert hat.</span><span class="sxs-lookup"><span data-stu-id="9c37f-108">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="9c37f-109">Die folgende Tabelle zeigt die Situation.</span><span class="sxs-lookup"><span data-stu-id="9c37f-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="9c37f-110">Manager</span><span class="sxs-lookup"><span data-stu-id="9c37f-110">Manager</span></span>|<span data-ttu-id="9c37f-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="9c37f-111">Assistant</span></span>|<span data-ttu-id="9c37f-112">Department</span><span class="sxs-lookup"><span data-stu-id="9c37f-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="9c37f-113">Ursprünglicher Datenbankzustand bei Abfrage durch User1 und User2.</span><span class="sxs-lookup"><span data-stu-id="9c37f-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="9c37f-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="9c37f-114">Alfreds</span></span>|<span data-ttu-id="9c37f-115">Maria</span><span class="sxs-lookup"><span data-stu-id="9c37f-115">Maria</span></span>|<span data-ttu-id="9c37f-116">Sales</span><span class="sxs-lookup"><span data-stu-id="9c37f-116">Sales</span></span>|  
|<span data-ttu-id="9c37f-117">User1 bereitet sich auf die Übergabe dieser Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="9c37f-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="9c37f-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="9c37f-118">Alfred</span></span>||<span data-ttu-id="9c37f-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="9c37f-119">Marketing</span></span>|  
|<span data-ttu-id="9c37f-120">User2 hat diese Änderungen bereits übergeben.</span><span class="sxs-lookup"><span data-stu-id="9c37f-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="9c37f-121">Mary</span><span class="sxs-lookup"><span data-stu-id="9c37f-121">Mary</span></span>|<span data-ttu-id="9c37f-122">Dienst</span><span class="sxs-lookup"><span data-stu-id="9c37f-122">Service</span></span>|  
  
 <span data-ttu-id="9c37f-123">User1 entscheidet sich, diesen Konflikt durch das Überschreiben von Datenbankwerten mit den aktuellen Clientmemberwerten zu lösen.</span><span class="sxs-lookup"><span data-stu-id="9c37f-123">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="9c37f-124">Wenn User1 den Konflikt durch Verwendung von <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> behebt, entspricht das Ergebnis in der Datenbank der folgenden Tabelle:</span><span class="sxs-lookup"><span data-stu-id="9c37f-124">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="9c37f-125">Manager</span><span class="sxs-lookup"><span data-stu-id="9c37f-125">Manager</span></span>|<span data-ttu-id="9c37f-126">Assistant</span><span class="sxs-lookup"><span data-stu-id="9c37f-126">Assistant</span></span>|<span data-ttu-id="9c37f-127">Department</span><span class="sxs-lookup"><span data-stu-id="9c37f-127">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="9c37f-128">Neuer Zustand nach Konfliktlösung.</span><span class="sxs-lookup"><span data-stu-id="9c37f-128">New state after conflict resolution.</span></span>|<span data-ttu-id="9c37f-129">Alfred</span><span class="sxs-lookup"><span data-stu-id="9c37f-129">Alfred</span></span><br /><br /> <span data-ttu-id="9c37f-130">(von User1)</span><span class="sxs-lookup"><span data-stu-id="9c37f-130">(from User1)</span></span>|<span data-ttu-id="9c37f-131">Maria</span><span class="sxs-lookup"><span data-stu-id="9c37f-131">Maria</span></span><br /><br /> <span data-ttu-id="9c37f-132">(Original)</span><span class="sxs-lookup"><span data-stu-id="9c37f-132">(original)</span></span>|<span data-ttu-id="9c37f-133">Marketing</span><span class="sxs-lookup"><span data-stu-id="9c37f-133">Marketing</span></span><br /><br /> <span data-ttu-id="9c37f-134">(von User1)</span><span class="sxs-lookup"><span data-stu-id="9c37f-134">(from User1)</span></span>|  
  
 <span data-ttu-id="9c37f-135">Im folgenden Beispielcode wird gezeigt, wie Datenbankwerte mit den aktuellen Clientmemberwerten überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9c37f-135">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="9c37f-136">(Keine Inspektion oder benutzerdefinierte Behandlung einzelner Memberkonflikte.)</span><span class="sxs-lookup"><span data-stu-id="9c37f-136">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9c37f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c37f-137">See also</span></span>

- [<span data-ttu-id="9c37f-138">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="9c37f-138">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
