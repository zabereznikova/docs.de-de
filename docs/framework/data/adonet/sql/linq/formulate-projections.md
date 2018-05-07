---
title: Formulieren von Projektionen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: f554007bd8c9e69f6a8dc475c122d3fbdfc43a4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="formulate-projections"></a>Formulieren von Projektionen
Das folgende Beispiel zeigt wie die `select` -Anweisung in c# und `Select` -Anweisung in Visual Basic kann zusammen mit anderen Funktionen, um Abfrageprojektionen zu bilden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in c#) um eine Sequenz mit Kontaktnamen von zurückzugeben `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in c#) und *anonyme Typen* gibt eine Sequenz von Kontaktnamen und Telefonnummern für `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in c#) und *anonyme Typen* gibt eine Sequenz von Namen und Telefonnummern für Mitarbeiter. Die `FirstName` und `LastName` Felder werden in einem einzelnen Feld kombiniert (`Name`), und die `HomePhone` Feld wird umbenannt, um `Phone` in der resultierenden Sequenz.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in c#) und *anonyme Typen* zurückzugebenden eine Sequenz aller `ProductID`s und einen berechneten Wert namens `HalfPrice`. Dieser Wert wird auf den `UnitPrice`, geteilt durch 2, festgelegt.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Select` -Klausel in Visual Basic (`select` -Klausel in c#) und ein *bedingungsanweisung* um eine Sequenz von Produktnamen und produktverfügbarkeit zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Visual Basic `Select` -Klausel (`select` -Klausel in c#) und ein *bekannten Typ* (Name), um eine Sequenz mit den Namen der Mitarbeiter zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `Select` und `Where` in Visual Basic (`select` und `where` in c#) zum Zurückgeben einer *gefilterte Sequenz* mit Kontaktnamen von Kunden in London.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Select` -Klausel in Visual Basic (`select` -Klausel in c#) und *anonyme Typen* zurückzugebenden eine *geformte Teilmenge* der Daten über Kunden.  
  
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
 [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
