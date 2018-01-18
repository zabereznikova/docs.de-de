---
title: "Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen"
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
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 120cc6d08d02fd33510903242c44feae3f8ec5c0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="9f9f8-102">Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="9f9f8-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="9f9f8-103">Verwenden Sie den <xref:System.Linq.Queryable.Except%2A>-Operator, um die Satzdifferenz zwischen zwei Sequenzen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="9f9f8-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f9f8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f9f8-104">Example</span></span>  
 <span data-ttu-id="9f9f8-105">In diesem Beispiel wird <xref:System.Linq.Queryable.Except%2A> verwendet, um eine Sequenz aller Länder zurückzugeben, in denen `Customers` (Kunden), aber keine `Employees` (Mitarbeiter) leben.</span><span class="sxs-lookup"><span data-stu-id="9f9f8-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="9f9f8-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Except%2A>-Operation nur für Sätze gut definiert.</span><span class="sxs-lookup"><span data-stu-id="9f9f8-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="9f9f8-107">Die Semantik für Multisets ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="9f9f8-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f9f8-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f9f8-108">See Also</span></span>  
 [<span data-ttu-id="9f9f8-109">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="9f9f8-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="9f9f8-110">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="9f9f8-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
