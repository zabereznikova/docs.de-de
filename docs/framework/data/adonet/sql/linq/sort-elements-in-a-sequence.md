---
title: Sortieren von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: b594e756b099aa94e1043fd4256da3eff46d0d95
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155756"
---
# <a name="sort-elements-in-a-sequence"></a>Sortieren von Elementen in einer Sequenz

Verwenden Sie den <xref:System.Linq.Enumerable.OrderBy%2A>-Operator, um eine Sequenz nach einem oder mehreren Schlüsseln zu sortieren.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist so konzipiert, dass die Reihenfolge von einfachen primitiven Typen wie `string` , usw. unterstützt wird `int` . Sortierungen für komplexe, mehrwertige Klassen, z. B. anonyme Typen, werden nicht unterstützt. Außerdem werden keine `byte`-Datentypen unterstützt.  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel sortiert `Employees` nach dem Einstellungsdatum.  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel verwendet `where`, um `Orders`, die nach `London` ausgeliefert wurden, nach Fracht zu sortieren.  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird `Products` absteigend nach Einzelpreis sortiert.  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird ein zusammengesetztes `OrderBy` verwendet, um `Customers` nach Ort und dann nach Kontaktnamen zu sortieren.  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel werden die Bestellungen von `EmployeeID 1` nach `ShipCountry` und dann von der höchsten zur niedrigsten Fracht sortiert.  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel kombiniert die Operatoren <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> und <xref:System.Linq.Enumerable.GroupBy%2A>, um jene `Products` zu ermitteln, die in den einzelnen Kategorien die höchsten Einzelpreise aufweisen. Anschließend wird die Gruppe nach Kategorie-ID sortiert.  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 Wenn Sie die vorherige Abfrage mit der Beispieldatenbank Northwind ausführen, sehen die Ergebnisse wie folgt aus:  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfrage Beispiele](query-examples.md)
- [Herunterladen von Beispieldatenbanken](downloading-sample-databases.md)
