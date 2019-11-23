---
title: 'Gewusst wie: Verwenden von gespeicherten Prozeduren, die mehreren Ergebnisformen zugeordnet sind'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 065e866ec5937c4af31c0b1563a7582cb4112eba
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003269"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a>Gewusst wie: Verwenden von gespeicherten Prozeduren, die mehreren Ergebnisformen zugeordnet sind
Wenn eine gespeicherte Prozedur mehrere Ergebnisformen zurückgeben kann, lässt sich der Rückgabetyp nicht auf eine einzige Projektionsform festlegen. Obwohl [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] alle möglichen Projektions Typen generieren kann, ist es nicht möglich, die Reihenfolge zu kennen, in der Sie zurückgegeben werden.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Gespeicherte Prozeduren](stored-procedures.md)
