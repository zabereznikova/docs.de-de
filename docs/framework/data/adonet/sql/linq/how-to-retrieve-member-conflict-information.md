---
title: 'Vorgehensweise: Abrufen von Memberkonfliktinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 9d63b0b2c7d513d9f4db526b88a7c4e852637343
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928634"
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="94a9b-102">Vorgehensweise: Abrufen von Memberkonfliktinformationen</span><span class="sxs-lookup"><span data-stu-id="94a9b-102">How to: Retrieve Member Conflict Information</span></span>
<span data-ttu-id="94a9b-103">Sie können die <xref:System.Data.Linq.MemberChangeConflict>-Klasse verwenden, um Informationen über einzelne kollidierende Member abzurufen.</span><span class="sxs-lookup"><span data-stu-id="94a9b-103">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="94a9b-104">In diesem gleichen Kontext können Sie für jeden Member für eine benutzerdefinierte Behandlung des Konflikts sorgen.</span><span class="sxs-lookup"><span data-stu-id="94a9b-104">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="94a9b-105">Weitere Informationen finden [Sie unter optimistische Parallelität: Übersicht](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="94a9b-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="94a9b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94a9b-106">Example</span></span>  
 <span data-ttu-id="94a9b-107">Der folgende Code wechselt durch die <xref:System.Data.Linq.ObjectChangeConflict>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="94a9b-107">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="94a9b-108">Für jedes Objekt durchläuft er dann die <xref:System.Data.Linq.MemberChangeConflict>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="94a9b-108">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94a9b-109">Schließen Sie <xref:System.Reflection> ein, um <xref:System.Data.Linq.MemberChangeConflict.Member%2A>-Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="94a9b-109">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="94a9b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94a9b-110">See also</span></span>

- [<span data-ttu-id="94a9b-111">Vorgehensweise: Verwalten von Änderungs Konflikten</span><span class="sxs-lookup"><span data-stu-id="94a9b-111">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
