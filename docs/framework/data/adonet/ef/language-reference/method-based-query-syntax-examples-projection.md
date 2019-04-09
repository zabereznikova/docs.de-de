---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Projection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: a38fce33fe34bf6485d0d5fcef4f194f4c2470b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194993"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="f78ca-102">Beispiele für die methodenbasierte Abfragesyntax: Projection</span><span class="sxs-lookup"><span data-stu-id="f78ca-102">Method-Based Query Syntax Examples: Projection</span></span>
<span data-ttu-id="f78ca-103">In diesem Thema wird gezeigt, wie mit der <xref:System.Linq.Enumerable.Select%2A> und <xref:System.Linq.Enumerable.SelectMany%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mit der methodenbasierten Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="f78ca-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="f78ca-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="f78ca-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f78ca-105">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="f78ca-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="f78ca-106">Auswählen</span><span class="sxs-lookup"><span data-stu-id="f78ca-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="f78ca-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f78ca-107">Example</span></span>  
 <span data-ttu-id="f78ca-108">Im folgenden Beispiel wird die <xref:System.Linq.Queryable.Select%2A>-Methode verwendet, um die `Product.Name`-Eigenschaft und die `Product.ProductID`-Eigenschaft auf eine Abfolge anonymer Typen zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="f78ca-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="f78ca-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f78ca-109">Example</span></span>  
 <span data-ttu-id="f78ca-110">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Select%2A>-Methode verwendet, um eine Sequenz zurückzugeben, die nur aus Produktnamen besteht.</span><span class="sxs-lookup"><span data-stu-id="f78ca-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="f78ca-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="f78ca-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="f78ca-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f78ca-112">Example</span></span>  
 <span data-ttu-id="f78ca-113">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>-Methode verwendet, um alle Aufträge auszuwählen, bei denen `TotalDue` kleiner als 500,00 ist.</span><span class="sxs-lookup"><span data-stu-id="f78ca-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="f78ca-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f78ca-114">Example</span></span>  
 <span data-ttu-id="f78ca-115">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>-Methode verwendet, um alle Aufträge auszuwählen, die am 1. Oktober 2002 oder später eingegangen sind.</span><span class="sxs-lookup"><span data-stu-id="f78ca-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="f78ca-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f78ca-116">See also</span></span>

- [<span data-ttu-id="f78ca-117">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="f78ca-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
