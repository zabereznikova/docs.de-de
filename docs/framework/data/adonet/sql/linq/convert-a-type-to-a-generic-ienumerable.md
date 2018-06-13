---
title: Konvertieren eines Typs in eine generische "IEnumerable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: e1d8036dd7ef4e1f59e2af46ac101135c39ef0c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360438"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="31137-102">Konvertieren eines Typs in eine generische "IEnumerable"</span><span class="sxs-lookup"><span data-stu-id="31137-102">Convert a Type to a Generic IEnumerable</span></span>
<span data-ttu-id="31137-103">Verwenden Sie <xref:System.Linq.Enumerable.AsEnumerable%2A>, um das als generische `IEnumerable` eingegebene Argument zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="31137-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31137-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31137-104">Example</span></span>  
 <span data-ttu-id="31137-105">In diesem Beispiel würde [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (mit der generischen Standard-`Query`) versuchen, die Abfrage in SQL zu konvertieren und auf dem Server auszuführen.</span><span class="sxs-lookup"><span data-stu-id="31137-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="31137-106">Die `where`-Klausel verweist jedoch auf eine benutzerdefinierte clientseitige Methode (`isValidProduct`), die nicht in SQL konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="31137-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="31137-107">Die Lösung erfordert das Definieren der clientseitigen generischen <xref:System.Collections.Generic.IEnumerable%601>-Implementierung von `where`, um das generische <xref:System.Linq.IQueryable%601> zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="31137-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="31137-108">Rufen Sie hierzu den <xref:System.Linq.Enumerable.AsEnumerable%2A>-Operator auf.</span><span class="sxs-lookup"><span data-stu-id="31137-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="31137-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31137-109">See Also</span></span>  
 [<span data-ttu-id="31137-110">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="31137-110">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
