---
title: "Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren"
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
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ac0e595140c11039d5a30f0e1f40c75e4a898002
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="ec264-102">Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren</span><span class="sxs-lookup"><span data-stu-id="ec264-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="ec264-103">In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.First%2A> -Methode und die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) mit der methodenbasierten Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="ec264-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="ec264-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="ec264-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ec264-105">Im Beispiel in diesem Thema wird Folgendes `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="ec264-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="ec264-106">First</span><span class="sxs-lookup"><span data-stu-id="ec264-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="ec264-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec264-107">Example</span></span>  
 <span data-ttu-id="ec264-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.First%2A>-Methode verwendet, um die erste E-Mail-Adresse zu suchen, die mit "caroline" beginnt.</span><span class="sxs-lookup"><span data-stu-id="ec264-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first e-mail address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="ec264-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec264-109">See Also</span></span>  
 [<span data-ttu-id="ec264-110">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ec264-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
