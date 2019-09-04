---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Partitionierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
ms.openlocfilehash: 42c562e7665a53053f125c17d073eb437574939f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250120"
---
# <a name="method-based-query-syntax-examples-partitioning"></a><span data-ttu-id="339fe-102">Beispiele für die methodenbasierte Abfragesyntax: Partitionierung</span><span class="sxs-lookup"><span data-stu-id="339fe-102">Method-Based Query Syntax Examples: Partitioning</span></span>
<span data-ttu-id="339fe-103">In den Beispielen in diesem Thema wird gezeigt, wie <xref:System.Linq.Enumerable.Skip%2A>die Methoden <xref:System.Linq.Enumerable.Take%2A> , und verwendet werden, um das [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mithilfe von Abfrage Ausdruckssyntax abzufragen.</span><span class="sxs-lookup"><span data-stu-id="339fe-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="339fe-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="339fe-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="339fe-105">In den Beispielen in diesem Thema werden die `using` folgenden / `Imports` -Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="339fe-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="339fe-106">Skip</span><span class="sxs-lookup"><span data-stu-id="339fe-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="339fe-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="339fe-107">Example</span></span>  
 <span data-ttu-id="339fe-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Skip%2A>-Methode verwendet, um, mit Ausnahme der ersten fünf Kontakte, alle Kontakte der Contact-Tabelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="339fe-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="339fe-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="339fe-109">Example</span></span>  
 <span data-ttu-id="339fe-110">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Skip%2A>-Methode verwendet, um, mit Ausnahme der ersten beiden Adressen, alle Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="339fe-110">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="339fe-111">Take</span><span class="sxs-lookup"><span data-stu-id="339fe-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="339fe-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="339fe-112">Example</span></span>  
 <span data-ttu-id="339fe-113">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Take%2A>-Methode verwendet, um nur die ersten fünf Kontakte aus der Contact-Tabelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="339fe-113">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="339fe-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="339fe-114">Example</span></span>  
 <span data-ttu-id="339fe-115">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Take%2A>-Methode verwendet, um die ersten drei Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="339fe-115">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="339fe-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="339fe-116">See also</span></span>

- [<span data-ttu-id="339fe-117">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="339fe-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
