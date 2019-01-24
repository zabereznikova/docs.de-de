---
title: Formulieren von Projektionen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 9b32ee4c7745fda482561311dc116e0e38b49ab7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599152"
---
# <a name="formulate-projections"></a>Formulieren von Projektionen
Die folgenden Beispiele zeigen die `select` -Anweisung in C# und `Select` -Anweisung in Visual Basic kann kombiniert werden, mit anderen Funktionen, um Abfrageprojektionen zu bilden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in C#) um eine Sequenz mit Kontaktnamen für `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in C#) und *anonyme Typen* gibt eine Sequenz mit Kontaktnamen und Telefonnummern für `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in C#) und *anonyme Typen* um eine Sequenz mit Namen und Telefonnummern für Mitarbeiter. Die `FirstName` und `LastName` Felder werden in einem einzelnen Feld kombiniert (`Name`), und die `HomePhone` Feld wird umbenannt in `Phone` in der resultierenden Sequenz.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in C#) und *anonyme Typen* um eine Sequenz aller `ProductID`s und einen berechneten Wert namens `HalfPrice`. Dieser Wert wird auf den `UnitPrice`, geteilt durch 2, festgelegt.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in C#) und ein *bedingungsanweisung* um eine Sequenz mit Produktnamen und produktverfügbarkeit zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Visual Basic `Select` Klausel (`select` -Klausel in C#) und ein *bekannten Typ* (Name), um eine Sequenz mit den Namen der Mitarbeiter zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `Select` und `Where` in Visual Basic (`select` und `where` in C#) zum Zurückgeben einer *gefilterte Sequenz* mit Kontaktnamen von Kunden in London.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Select` -Klausel in Visual Basic (`select` -Klausel in C#) und *anonyme Typen* zurückzugebenden eine *geformte Teilmenge* von Daten über Kunden.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden geschachtelte Abfragen verwendet, um die folgenden Ergebnisse zurückzugeben:  
  
-   Eine Sequenz aller Bestellungen und der entsprechenden `OrderID`s.  
  
-   Eine Untersequenz der Elemente in der Bestellung, für die es einen Rabatt gibt.  
  
-   Der gesparte Betrag, wenn die Lieferkosten nicht eingeschlossen werden.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>Siehe auch
- [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
