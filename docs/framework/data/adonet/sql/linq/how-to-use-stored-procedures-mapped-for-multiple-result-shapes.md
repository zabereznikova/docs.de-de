---
title: 'Vorgehensweise: Verwenden von gespeicherten Prozeduren, die mehreren Ergebnisformen zugeordnet sind'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 26cc30790da26949fba889106d060cdef89013a3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185001"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a>Vorgehensweise: Verwenden von gespeicherten Prozeduren, die mehreren Ergebnisformen zugeordnet sind

Wenn eine gespeicherte Prozedur mehrere Ergebnisformen zurückgeben kann, lässt sich der Rückgabetyp nicht auf eine einzige Projektionsform festlegen. Obwohl [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] alle möglichen Projektions Typen generieren kann, ist die Reihenfolge, in der Sie zurückgegeben werden, nicht bekannt.  
  
 Vergleichen Sie dieses Szenario mit gespeicherten Prozeduren, die sequenziell mehrere Ergebnisformen erzeugen. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von gespeicherten Prozeduren, die sequenziellen Ergebnis Formen zugeordnet](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)sind.  
  
 Das <xref:System.Data.Linq.Mapping.ResultTypeAttribute>-Attribut wird auf gespeicherte Prozeduren angewendet, die mehrere Ergebnistypen zurückgeben, um den Typsatz anzugeben, den die Prozedur zurückgeben kann.  
  
## <a name="example"></a>Beispiel  

 Im folgenden SQL-Codebeispiel hängt die Ergebnisform von der Eingabe ab (`shape =1` oder `shape = 2`). Es ist nicht bekannt, welche Projektion zuerst zurückgegeben wird.  
  
``` sql
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a>Beispiel  

 Um die gespeicherte Prozedur auszuführen, wird in etwa der folgende Code verwendet.  
  
> [!NOTE]
> Sie müssen mithilfe Ihrer Kenntnisse über die gespeicherte Prozedur das <xref:System.Data.Linq.IMultipleResults.GetResult%2A>-Muster verwenden, um einen Enumerator mit dem richtigen Typ zu erhalten.  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Gespeicherte Prozeduren](stored-procedures.md)
