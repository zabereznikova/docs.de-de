---
title: 'Gewusst wie: Verwenden von gespeicherten Prozeduren, die Parameter annehmen'
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
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 505c99b262f4762d5965789688236b22e74bdaeb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="6d514-102">Gewusst wie: Verwenden von gespeicherten Prozeduren, die Parameter annehmen</span><span class="sxs-lookup"><span data-stu-id="6d514-102">How to: Use Stored Procedures that Take Parameters</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6d514-103"> ordnet Verweisparametern Ausgabeparameter zu, und für Werttypen wird der Parameter als auf NULL festlegbar deklariert.</span><span class="sxs-lookup"><span data-stu-id="6d514-103"> maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="6d514-104">Ein Beispiel dazu, wie ein input-Parameters in einer Abfrage verwenden, die ein Rowset zurückgibt, finden Sie unter [wie: Zurückgeben von Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="6d514-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d514-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d514-105">Example</span></span>  
 <span data-ttu-id="6d514-106">Im folgenden Beispiel wird ein einzelner Eingabeparameter (die Kunden-ID) angenommen, und es wird ein Ausgabeparameter (der Gesamtumsatz mit diesem Kunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6d514-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="6d514-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d514-107">Example</span></span>  
 <span data-ttu-id="6d514-108">Sie würden diese gespeicherte Prozedur wie folgt aufrufen:</span><span class="sxs-lookup"><span data-stu-id="6d514-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6d514-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d514-109">See Also</span></span>  
 [<span data-ttu-id="6d514-110">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6d514-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="6d514-111">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="6d514-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="6d514-112">Verwenden von Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="6d514-112">Using Nullable Types</span></span>](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [<span data-ttu-id="6d514-113">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="6d514-113">Nullable Value Types</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
