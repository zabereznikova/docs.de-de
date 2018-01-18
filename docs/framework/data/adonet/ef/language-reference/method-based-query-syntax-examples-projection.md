---
title: "Beispiele für die methodenbasierte Abfragesyntax: Projektion"
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
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 908fc30cf504c370a748b58343dd34c1316f632a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="f987f-102">Beispiele für die methodenbasierte Abfragesyntax: Projektion</span><span class="sxs-lookup"><span data-stu-id="f987f-102">Method-Based Query Syntax Examples: Projection</span></span>
<span data-ttu-id="f987f-103">In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.Select%2A> und <xref:System.Linq.Enumerable.SelectMany%2A> methodenbasierten der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) mit der methodenbasierten Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="f987f-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methodsto query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="f987f-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="f987f-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f987f-105">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="f987f-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="f987f-106">Auswählen</span><span class="sxs-lookup"><span data-stu-id="f987f-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="f987f-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f987f-107">Example</span></span>  
 <span data-ttu-id="f987f-108">Im folgenden Beispiel wird die <xref:System.Linq.Queryable.Select%2A>-Methode verwendet, um die `Product.Name`-Eigenschaft und die `Product.ProductID`-Eigenschaft auf eine Abfolge anonymer Typen zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="f987f-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="f987f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f987f-109">Example</span></span>  
 <span data-ttu-id="f987f-110">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Select%2A>-Methode verwendet, um eine Sequenz zurückzugeben, die nur aus Produktnamen besteht.</span><span class="sxs-lookup"><span data-stu-id="f987f-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="f987f-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="f987f-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="f987f-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f987f-112">Example</span></span>  
 <span data-ttu-id="f987f-113">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>-Methode verwendet, um alle Aufträge auszuwählen, bei denen `TotalDue` kleiner als 500,00 ist.</span><span class="sxs-lookup"><span data-stu-id="f987f-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="f987f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f987f-114">Example</span></span>  
 <span data-ttu-id="f987f-115">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>-Methode verwendet, um alle Aufträge auszuwählen, die am 1. Oktober 2002 oder später eingegangen sind.</span><span class="sxs-lookup"><span data-stu-id="f987f-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="f987f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f987f-116">See Also</span></span>  
 [<span data-ttu-id="f987f-117">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="f987f-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
