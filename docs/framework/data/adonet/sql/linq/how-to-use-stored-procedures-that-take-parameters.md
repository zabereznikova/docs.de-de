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
# <a name="how-to-use-stored-procedures-that-take-parameters"></a>Vorgehensweise: Verwenden von gespeicherten Prozeduren, die Parameter annehmen

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ordnet Verweisparametern Ausgabeparameter zu, und für Werttypen wird der Parameter als auf NULL festlegbar deklariert.  
  
 Ein Beispiel für die Verwendung eines Eingabe Parameters in einer Abfrage, die ein Rowset zurückgibt, finden Sie unter Gewusst [wie: Zurückgeben von Rowsets](how-to-return-rowsets.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird ein einzelner Eingabeparameter (die Kunden-ID) angenommen, und es wird ein Ausgabeparameter (der Gesamtumsatz mit diesem Kunden) zurückgegeben.  
  
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
  
## <a name="example"></a>Beispiel  

 Sie würden diese gespeicherte Prozedur wie folgt aufrufen:  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Gespeicherte Prozeduren](stored-procedures.md)
- [Herunterladen von Beispieldatenbanken](downloading-sample-databases.md)
- [Auf NULL festleg Bare Werttypen (c#)](../../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
- [Auf NULL festlegbare Werttypen (Visual Basic)](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
