---
title: "Zurückgeben des ersten Elements in einer Sequenz"
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
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bbdfe78f15490ce2c6722c83a4615ca29cbc5863
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="48e91-102">Zurückgeben des ersten Elements in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="48e91-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="48e91-103">Verwenden Sie den <xref:System.Linq.Enumerable.First%2A>-Operator, um das erste Element in einer Sequenz zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="48e91-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="48e91-104">Abfragen, die <xref:System.Linq.Enumerable.First%2A> verwenden, werden sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="48e91-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="48e91-105"> unterstützt den <xref:System.Linq.Enumerable.Last%2A>-Operator nicht.</span><span class="sxs-lookup"><span data-stu-id="48e91-105"> does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48e91-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48e91-106">Example</span></span>  
 <span data-ttu-id="48e91-107">Im folgenden Code wird der erste `Shipper` (Spediteur) in einer Tabelle gesucht:</span><span class="sxs-lookup"><span data-stu-id="48e91-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="48e91-108">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lauten die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="48e91-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="48e91-109">`ID = 1, Company = Speedy Express`</span><span class="sxs-lookup"><span data-stu-id="48e91-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="48e91-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48e91-110">Example</span></span>  
 <span data-ttu-id="48e91-111">Der folgende Code ermittelt den einzigen `Customer` (Kunden) mit `CustomerID`-BONAP.</span><span class="sxs-lookup"><span data-stu-id="48e91-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="48e91-112">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lauten die Ergebnisse `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="48e91-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="48e91-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48e91-113">See Also</span></span>  
 [<span data-ttu-id="48e91-114">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="48e91-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="48e91-115">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="48e91-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
