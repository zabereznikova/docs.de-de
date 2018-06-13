---
title: 'Gewusst wie: Verwenden von gespeicherten Prozeduren, die Parameter annehmen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: d1c9337f59b8cf218b9d2ab8fe4cf21afd2da689
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353510"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="c3aa4-102">Gewusst wie: Verwenden von gespeicherten Prozeduren, die Parameter annehmen</span><span class="sxs-lookup"><span data-stu-id="c3aa4-102">How to: Use Stored Procedures that Take Parameters</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c3aa4-103"> ordnet Verweisparametern Ausgabeparameter zu, und für Werttypen wird der Parameter als auf NULL festlegbar deklariert.</span><span class="sxs-lookup"><span data-stu-id="c3aa4-103"> maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="c3aa4-104">Ein Beispiel dazu, wie ein input-Parameters in einer Abfrage verwenden, die ein Rowset zurückgibt, finden Sie unter [wie: Zurückgeben von Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="c3aa4-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3aa4-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3aa4-105">Example</span></span>  
 <span data-ttu-id="c3aa4-106">Im folgenden Beispiel wird ein einzelner Eingabeparameter (die Kunden-ID) angenommen, und es wird ein Ausgabeparameter (der Gesamtumsatz mit diesem Kunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c3aa4-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```  
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
  
## <a name="example"></a><span data-ttu-id="c3aa4-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3aa4-107">Example</span></span>  
 <span data-ttu-id="c3aa4-108">Sie würden diese gespeicherte Prozedur wie folgt aufrufen:</span><span class="sxs-lookup"><span data-stu-id="c3aa4-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c3aa4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3aa4-109">See Also</span></span>  
 [<span data-ttu-id="c3aa4-110">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c3aa4-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="c3aa4-111">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="c3aa4-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="c3aa4-112">Verwenden von Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="c3aa4-112">Using Nullable Types</span></span>](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [<span data-ttu-id="c3aa4-113">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="c3aa4-113">Nullable Value Types</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
