---
title: 'Vorgehensweise: Angeben, wann Parallelitätsausnahmen ausgelöst werden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: c0f41d23264bbe5c9130cb5a0b03686331bc92b1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781618"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a><span data-ttu-id="e5cfb-102">Vorgehensweise: Angeben, wann Parallelitätsausnahmen ausgelöst werden</span><span class="sxs-lookup"><span data-stu-id="e5cfb-102">How to: Specify When Concurrency Exceptions are Thrown</span></span>
<span data-ttu-id="e5cfb-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn Objekte aufgrund von Konflikten bei der vollständigen Parallelität nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e5cfb-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when objects do not update because of optimistic concurrency conflicts.</span></span> <span data-ttu-id="e5cfb-104">Weitere Informationen finden [Sie unter optimistische Parallelität: Übersicht](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e5cfb-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="e5cfb-105">Bevor Sie die Änderungen an die Datenbank übergeben, können Sie angeben, wann Parallelitätsausnahmen ausgelöst werden sollen:</span><span class="sxs-lookup"><span data-stu-id="e5cfb-105">Before you submit your changes to the database, you can specify when concurrency exceptions should be thrown:</span></span>  
  
- <span data-ttu-id="e5cfb-106">Auslösen der Ausnahme beim ersten Fehler (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span><span class="sxs-lookup"><span data-stu-id="e5cfb-106">Throw the exception at the first failure (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span></span>  
  
- <span data-ttu-id="e5cfb-107">Beenden aller Updateversuche, Sammeln aller Fehler und Melden aller Fehler in der Ausnahme (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span><span class="sxs-lookup"><span data-stu-id="e5cfb-107">Finish all update tries, accumulate all failures, and report the accumulated failures in the exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span></span>  
  
 <span data-ttu-id="e5cfb-108">Bei Auslösung ermöglicht die <xref:System.Data.Linq.ChangeConflictException>-Ausnahme den Zugriff auf eine <xref:System.Data.Linq.ChangeConflictCollection>-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e5cfb-108">When thrown, the <xref:System.Data.Linq.ChangeConflictException> exception provides access to a <xref:System.Data.Linq.ChangeConflictCollection> collection.</span></span> <span data-ttu-id="e5cfb-109">Diese Auflistung enthält Details zu jedem Konflikt (mit Zuweisung zu einem bestimmten fehlgeschlagenen Updateversuch), einschließlich des Zugriffs auf die <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e5cfb-109">This collection provides details for each conflict (mapped to a single failed update try), including access to the <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> collection.</span></span> <span data-ttu-id="e5cfb-110">Jeder Memberkonflikt im Update wird einem Member zugewiesen, der die Parallelitätsprüfung nicht bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="e5cfb-110">Each member conflict maps to a single member in the update that failed the concurrency check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5cfb-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5cfb-111">Example</span></span>  
 <span data-ttu-id="e5cfb-112">Der folgende Code zeigt Beispiele für beide Werte.</span><span class="sxs-lookup"><span data-stu-id="e5cfb-112">The following code shows examples of both values.</span></span>  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e5cfb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5cfb-113">See also</span></span>

- [<span data-ttu-id="e5cfb-114">Vorgehensweise: Verwalten von Änderungs Konflikten</span><span class="sxs-lookup"><span data-stu-id="e5cfb-114">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="e5cfb-115">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="e5cfb-115">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
