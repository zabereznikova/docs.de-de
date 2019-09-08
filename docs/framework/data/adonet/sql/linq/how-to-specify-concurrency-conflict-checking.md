---
title: 'Vorgehensweise: Angeben von Parallelitätskonfliktüberprüfungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: fd3db5eb5dc9b74d8ea33af56dd522cf2f3fecdb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781587"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="c428b-102">Vorgehensweise: Angeben von Parallelitätskonfliktüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="c428b-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="c428b-103">Sie können festlegen, welche Datenbankspalten auf Parallelitätskonflikte geprüft werden, wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c428b-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="c428b-104">Weitere Informationen finden Sie unter [Vorgehensweise: Geben Sie an, welche Member auf Parallelitäts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)Konflikte getestet werden.</span><span class="sxs-lookup"><span data-stu-id="c428b-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c428b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c428b-105">Example</span></span>  
 <span data-ttu-id="c428b-106">Der folgende Code gibt an, dass der `HomePage`-Member nie während der Updateprüfungen getestet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="c428b-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="c428b-107">Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="c428b-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c428b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c428b-108">See also</span></span>

- [<span data-ttu-id="c428b-109">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="c428b-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c428b-110">Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="c428b-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
