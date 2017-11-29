---
title: "Zurückgeben der Schnittmenge von zwei Sequenzen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4ff65c310323f7505f00dc4a768869cac8226d25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="90b06-102">Zurückgeben der Schnittmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="90b06-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="90b06-103">Verwenden Sie den <xref:System.Linq.Queryable.Intersect%2A>-Operator, um die Schnittmenge von zwei Sequenzen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="90b06-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90b06-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90b06-104">Example</span></span>  
 <span data-ttu-id="90b06-105">In diesem Beispiel wird <xref:System.Linq.Queryable.Intersect%2A> verwendet, um eine Sequenz aller Länder zurückzugeben, in denen `Customers` (Kunden) und `Employees` (Mitarbeiter) leben.</span><span class="sxs-lookup"><span data-stu-id="90b06-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="90b06-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Intersect%2A>-Operation nur für Sätze gut definiert.</span><span class="sxs-lookup"><span data-stu-id="90b06-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="90b06-107">Die Semantik für Multisets ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="90b06-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b06-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90b06-108">See Also</span></span>  
 [<span data-ttu-id="90b06-109">Beispiele für Abfragen</span><span class="sxs-lookup"><span data-stu-id="90b06-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="90b06-110">Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="90b06-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
