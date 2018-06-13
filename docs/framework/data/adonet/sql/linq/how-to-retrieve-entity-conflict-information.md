---
title: 'Gewusst wie: Abrufen von Entitätskonfliktinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: cabfae568396fa34e6090027032f310cdc05c507
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353194"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="f1f31-102">Gewusst wie: Abrufen von Entitätskonfliktinformationen</span><span class="sxs-lookup"><span data-stu-id="f1f31-102">How to: Retrieve Entity Conflict Information</span></span>
<span data-ttu-id="f1f31-103">Sie können Objekte der <xref:System.Data.Linq.ObjectChangeConflict>-Klasse verwenden, um Informationen über von <xref:System.Data.Linq.ChangeConflictException>-Ausnahmen erkannte Konflikte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f1f31-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="f1f31-104">Weitere Informationen finden Sie unter [vollständige Parallelität: Übersicht über](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f1f31-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1f31-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1f31-105">Example</span></span>  
 <span data-ttu-id="f1f31-106">Im folgenden Beispiel wird eine Liste akkumulierter Konflikte durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="f1f31-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f1f31-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1f31-107">See Also</span></span>  
 [<span data-ttu-id="f1f31-108">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="f1f31-108">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
