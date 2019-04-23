---
title: 'Vorgehensweise: Abrufen von Memberkonfliktinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: fae1513e7a7ead98318d907b220b7510758c9ffe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115088"
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="53c8a-102">Vorgehensweise: Abrufen von Memberkonfliktinformationen</span><span class="sxs-lookup"><span data-stu-id="53c8a-102">How to: Retrieve Member Conflict Information</span></span>
<span data-ttu-id="53c8a-103">Sie können die <xref:System.Data.Linq.MemberChangeConflict>-Klasse verwenden, um Informationen über einzelne kollidierende Member abzurufen.</span><span class="sxs-lookup"><span data-stu-id="53c8a-103">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="53c8a-104">In diesem gleichen Kontext können Sie für jeden Member für eine benutzerdefinierte Behandlung des Konflikts sorgen.</span><span class="sxs-lookup"><span data-stu-id="53c8a-104">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="53c8a-105">Weitere Informationen finden Sie unter [optimistische Parallelität: Übersicht über die](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="53c8a-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53c8a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53c8a-106">Example</span></span>  
 <span data-ttu-id="53c8a-107">Der folgende Code wechselt durch die <xref:System.Data.Linq.ObjectChangeConflict>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="53c8a-107">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="53c8a-108">Für jedes Objekt durchläuft er dann die <xref:System.Data.Linq.MemberChangeConflict>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="53c8a-108">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53c8a-109">Schließen Sie <xref:System.Reflection> ein, um <xref:System.Data.Linq.MemberChangeConflict.Member%2A>-Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="53c8a-109">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="53c8a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53c8a-110">See also</span></span>

- [<span data-ttu-id="53c8a-111">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="53c8a-111">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
