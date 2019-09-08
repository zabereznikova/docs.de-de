---
title: Sortieren von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: 21fa2f9e1dc2f255fe94f2420ba90a809ab5b05e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792660"
---
# <a name="sort-elements-in-a-sequence"></a>Sortieren von Elementen in einer Sequenz
Verwenden Sie den <xref:System.Linq.Enumerable.OrderBy%2A>-Operator, um eine Sequenz nach einem oder mehreren Schlüsseln zu sortieren.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]ist so konzipiert, dass die Reihenfolge `string`von einfachen primitiven Typen wie, `int`usw. unterstützt wird. Sortierungen für komplexe, mehrwertige Klassen, z. B. anonyme Typen, werden nicht unterstützt. Außerdem werden keine `byte`-Datentypen unterstützt.  
  
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
 Im folgenden Beispiel werden die Bestel `EmployeeID 1` Lungen `ShipCountry`von nach und dann von der höchsten zur niedrigsten Fracht sortiert.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](query-examples.md)
- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](downloading-sample-databases.md)
