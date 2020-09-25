---
title: 'Vorgehensweise: Verwenden von gespeicherten Prozeduren, die Parameter annehmen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: a54e2ee553629179022b68658d44cbcb02ab590f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184962"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="e91d3-102">Vorgehensweise: Verwenden von gespeicherten Prozeduren, die Parameter annehmen</span><span class="sxs-lookup"><span data-stu-id="e91d3-102">How to: Use Stored Procedures that Take Parameters</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="e91d3-103">ordnet Verweisparametern Ausgabeparameter zu, und für Werttypen wird der Parameter als auf NULL festlegbar deklariert.</span><span class="sxs-lookup"><span data-stu-id="e91d3-103">maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="e91d3-104">Ein Beispiel für die Verwendung eines Eingabe Parameters in einer Abfrage, die ein Rowset zurückgibt, finden Sie unter Gewusst [wie: Zurückgeben von Rowsets](how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="e91d3-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e91d3-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e91d3-105">Example</span></span>  

 <span data-ttu-id="e91d3-106">Im folgenden Beispiel wird ein einzelner Eingabeparameter (die Kunden-ID) angenommen, und es wird ein Ausgabeparameter (der Gesamtumsatz mit diesem Kunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e91d3-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```sql
CREATE PROCEDURE [dbo].[CustOrderTotal]
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="e91d3-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e91d3-107">Example</span></span>  

 <span data-ttu-id="e91d3-108">Sie würden diese gespeicherte Prozedur wie folgt aufrufen:</span><span class="sxs-lookup"><span data-stu-id="e91d3-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e91d3-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e91d3-109">See also</span></span>

- [<span data-ttu-id="e91d3-110">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e91d3-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="e91d3-111">Herunterladen von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="e91d3-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="e91d3-112">Auf NULL festleg Bare Werttypen (c#)</span><span class="sxs-lookup"><span data-stu-id="e91d3-112">Nullable Value Types (C#)</span></span>](../../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
- [<span data-ttu-id="e91d3-113">Auf NULL festlegbare Werttypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e91d3-113">Nullable Value Types (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
