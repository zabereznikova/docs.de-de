---
title: 'Beispiele für die Abfrageausdruckssyntax: Projection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 079926c5-e6b5-4fb9-b4cf-9c63886dd626
ms.openlocfilehash: 9c10c334ae2a10df1f75384ce042781b6f1bd43a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614413"
---
# <a name="query-expression-syntax-examples-projection"></a><span data-ttu-id="bd070-102">Beispiele für die Abfrageausdruckssyntax: Projection</span><span class="sxs-lookup"><span data-stu-id="bd070-102">Query Expression Syntax Examples: Projection</span></span>
<span data-ttu-id="bd070-103">In die Beispielen in diesem Thema wird gezeigt, wie mit der `Select` Methode und die `From … From …` Schlüsselwörter zum Abfragen der [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mithilfe der Abfrageausdruckssyntax Abfragen.</span><span class="sxs-lookup"><span data-stu-id="bd070-103">The examples in this topic demonstrate how to use the `Select` method and the `From … From …` keywords to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="bd070-104">`From … From …` ist die abfragebasierte Entsprechung der `SelectMany`-Methode.</span><span class="sxs-lookup"><span data-stu-id="bd070-104">`From … From …` is the query based equivalent of the `SelectMany` method.</span></span> <span data-ttu-id="bd070-105">Für das in den Beispielen verwendete AdventureWorks Sales-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der AdventureWorks-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="bd070-105">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="bd070-106">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="bd070-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="bd070-107">Auswählen</span><span class="sxs-lookup"><span data-stu-id="bd070-107">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="bd070-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd070-108">Example</span></span>  
 <span data-ttu-id="bd070-109">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Select%2A>-Methode verwendet, um alle Zeilen der Tabelle `Product` zurückzugeben und die Produktnamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd070-109">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="bd070-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd070-110">Example</span></span>  
 <span data-ttu-id="bd070-111">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Select%2A> verwendet, um eine Sequenz zurückzugeben, die nur aus Produktnamen besteht.</span><span class="sxs-lookup"><span data-stu-id="bd070-111">The following example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2)]  
  
### <a name="example"></a><span data-ttu-id="bd070-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd070-112">Example</span></span>  
 <span data-ttu-id="bd070-113">Im folgenden Beispiel wird die <xref:System.Linq.Queryable.Select%2A>-Methode verwendet, um die `Product.Name`-Eigenschaft und die `Product.ProductID`-Eigenschaft auf eine Abfolge anonymer Typen zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="bd070-113">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes)]  
  
## <a name="from--from--selectmany"></a><span data-ttu-id="bd070-114">Von...</span><span class="sxs-lookup"><span data-stu-id="bd070-114">From …</span></span> <span data-ttu-id="bd070-115">Von...</span><span class="sxs-lookup"><span data-stu-id="bd070-115">From …</span></span> <span data-ttu-id="bd070-116">(SelectMany)</span><span class="sxs-lookup"><span data-stu-id="bd070-116">(SelectMany)</span></span>  
  
### <a name="example"></a><span data-ttu-id="bd070-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd070-117">Example</span></span>  
 <span data-ttu-id="bd070-118">Im folgenden Beispiel wird `From … From …` (das Äquivalent der <xref:System.Linq.Enumerable.SelectMany%2A>-Methode) verwendet, um alle Aufträge auszuwählen, bei denen `TotalDue` kleiner als 500,00 ist.</span><span class="sxs-lookup"><span data-stu-id="bd070-118">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="bd070-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd070-119">Example</span></span>  
 <span data-ttu-id="bd070-120">Im folgenden Beispiel wird `From … From …` (das Äquivalent der <xref:System.Linq.Enumerable.SelectMany%2A>-Methode) verwendet, um alle Aufträge auszuwählen, bei denen die Bestellung am 1. Oktober 2002 oder später eingegangen ist.</span><span class="sxs-lookup"><span data-stu-id="bd070-120">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="bd070-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd070-121">Example</span></span>  
 <span data-ttu-id="bd070-122">Im folgenden Beispiel wird `From … From …` (das Äquivalent der <xref:System.Linq.Enumerable.SelectMany%2A>-Methode) verwendet, um alle Aufträge auszuwählen, bei denen die Bestellsumme größer als 10000,00 ist. Mithilfe der `From`-Zuweisung wird vermieden, dass die Summe zweimal angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="bd070-122">The following example uses a `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="bd070-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd070-123">See also</span></span>

- [<span data-ttu-id="bd070-124">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="bd070-124">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
