---
title: "Beispiele für die methodenbasierte Abfragesyntax: Konvertierung"
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
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a76ebf99e0f8abe7d0ab3052a05c813402f665b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="1513f-102">Beispiele für die methodenbasierte Abfragesyntax: Konvertierung</span><span class="sxs-lookup"><span data-stu-id="1513f-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="1513f-103">In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> und <xref:System.Linq.Enumerable.ToList%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) mit der methodenbasierten Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="1513f-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="1513f-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="1513f-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="1513f-105">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="1513f-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="1513f-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="1513f-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="1513f-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1513f-107">Example</span></span>  
 <span data-ttu-id="1513f-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.ToArray%2A>-Methode verwendet, um eine Sequenz unmittelbar in ein Array auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="1513f-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="1513f-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="1513f-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="1513f-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1513f-110">Example</span></span>  
 <span data-ttu-id="1513f-111">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.ToDictionary%2A>-Methode verwendet, um eine Sequenz und einen zugehörigen Schlüsselausdruck unmittelbar in ein Wörterbuch umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="1513f-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="1513f-112">ToList</span><span class="sxs-lookup"><span data-stu-id="1513f-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="1513f-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1513f-113">Example</span></span>  
 <span data-ttu-id="1513f-114">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.ToList%2A>-Methode verwendet, um eine Sequenz unmittelbar in eine <xref:System.Collections.Generic.List%601> umzuwandeln, wobei `T` vom Typ <xref:System.Data.DataRow> ist.</span><span class="sxs-lookup"><span data-stu-id="1513f-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="1513f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1513f-115">See Also</span></span>  
 [<span data-ttu-id="1513f-116">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="1513f-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
