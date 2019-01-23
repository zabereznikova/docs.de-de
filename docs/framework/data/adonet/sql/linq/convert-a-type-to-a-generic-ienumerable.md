---
title: Konvertieren eines Typs in eine generische "IEnumerable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: d1f4c1c4a561c893b5846e6ae0b08b2d78c3589d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509596"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="310c8-102">Konvertieren eines Typs in eine generische "IEnumerable"</span><span class="sxs-lookup"><span data-stu-id="310c8-102">Convert a Type to a Generic IEnumerable</span></span>
<span data-ttu-id="310c8-103">Verwenden Sie <xref:System.Linq.Enumerable.AsEnumerable%2A>, um das als generische `IEnumerable` eingegebene Argument zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="310c8-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="310c8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="310c8-104">Example</span></span>  
 <span data-ttu-id="310c8-105">In diesem Beispiel würde [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (mit der generischen Standard-`Query`) versuchen, die Abfrage in SQL zu konvertieren und auf dem Server auszuführen.</span><span class="sxs-lookup"><span data-stu-id="310c8-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="310c8-106">Die `where`-Klausel verweist jedoch auf eine benutzerdefinierte clientseitige Methode (`isValidProduct`), die nicht in SQL konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="310c8-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="310c8-107">Die Lösung erfordert das Definieren der clientseitigen generischen <xref:System.Collections.Generic.IEnumerable%601>-Implementierung von `where`, um das generische <xref:System.Linq.IQueryable%601> zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="310c8-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="310c8-108">Rufen Sie hierzu den <xref:System.Linq.Enumerable.AsEnumerable%2A>-Operator auf.</span><span class="sxs-lookup"><span data-stu-id="310c8-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="310c8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="310c8-109">See also</span></span>
- [<span data-ttu-id="310c8-110">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="310c8-110">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
