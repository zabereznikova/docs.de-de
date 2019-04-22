---
title: Berechnen der Summe von Werten in einer numerischen Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: 2f66b996a0e688205d61f5fca476c0335616ee38
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143571"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a>Berechnen der Summe von Werten in einer numerischen Sequenz
Verwenden Sie den <xref:System.Linq.Enumerable.Sum%2A>-Operator, um die Summe numerischer Werte in einer Sequenz zu berechnen.  
  
 Beachten Sie die folgenden Merkmale des `Sum`-Operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:  
  
-   Der `Sum`-Operator für Standardabfragen führt bei einer leeren Sequenz oder bei einer aus Nullen bestehenden Sequenz zum Ergebnis NULL. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bleibt die SQL-Semantik unverändert. Aus diesem Grund ergibt `Sum` bei einer leeren Sequenz oder bei einer aus Nullen bestehenden Sequenz den Wert NULL an Stelle von 0.  
  
-   SQL-Einschränkungen für Zwischenergebnisse gelten in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für Summen. Summe der 32-Bit-Ganzzahlmengen wird nicht mit 64-Bit-Ergebnisse berechnet und kann ein Überlauf auftreten, für die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Übersetzung `Sum`. Dies kann ggf. auch eintreten, wenn die standardmäßige Implementierung des Abfrageoperators bei der entsprechenden Sequenz im Arbeitsspeicher nicht zu einem Überlauf führt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die gesamte Fracht zu allen Bestellungen in der Tabelle `Order` ermittelt.  
  
 Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `64942.6900`.  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Gesamtzahl von bestellen Einheiten für alle Produkte ermittelt.  
  
 Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `780`.  
  
 Beachten Sie, dass Sie `short`-Typen (z. B. `UnitsOnOrder`) verwenden müssen, da `Sum` nicht über einen Überlauf für diese Typen verfügt.  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a>Siehe auch

- [Aggregatabfragen](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)
- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
