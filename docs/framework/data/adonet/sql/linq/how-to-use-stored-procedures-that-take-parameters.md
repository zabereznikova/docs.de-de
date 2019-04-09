---
title: 'Vorgehensweise: Verwenden von gespeicherten Prozeduren, die Parameter annehmen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: 8dd463c895efcddfe288fe1dc8571981872d9d80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181765"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="fbd98-102">Vorgehensweise: Verwenden von gespeicherten Prozeduren, die Parameter annehmen</span><span class="sxs-lookup"><span data-stu-id="fbd98-102">How to: Use Stored Procedures that Take Parameters</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fbd98-103">Ordnet die Output-Parameter, um Parameter zu verweisen, und für Werttypen wird den Parameter als auf NULL festlegbar deklariert.</span><span class="sxs-lookup"><span data-stu-id="fbd98-103">maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="fbd98-104">Ein Beispiel dafür, wie Eingabeparameter in einer Abfrage verwenden, die ein Rowset zurückgibt, finden Sie [Vorgehensweise: Zurückgeben von Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="fbd98-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbd98-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbd98-105">Example</span></span>  
 <span data-ttu-id="fbd98-106">Im folgenden Beispiel wird ein einzelner Eingabeparameter (die Kunden-ID) angenommen, und es wird ein Ausgabeparameter (der Gesamtumsatz mit diesem Kunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fbd98-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="fbd98-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbd98-107">Example</span></span>  
 <span data-ttu-id="fbd98-108">Sie würden diese gespeicherte Prozedur wie folgt aufrufen:</span><span class="sxs-lookup"><span data-stu-id="fbd98-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="fbd98-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbd98-109">See also</span></span>

- [<span data-ttu-id="fbd98-110">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="fbd98-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [<span data-ttu-id="fbd98-111">Herunterladen von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="fbd98-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="fbd98-112">Verwenden von auf NULL festlegbaren Typen</span><span class="sxs-lookup"><span data-stu-id="fbd98-112">Using Nullable Types</span></span>](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="fbd98-113">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="fbd98-113">Nullable Value Types</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
