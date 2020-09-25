---
title: Zurückgeben oder Überspringen von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81a31acd-e0f1-4bca-9a12-fa1ad5752374
ms.openlocfilehash: 1a36d3c8457374183148599bf8160d14847cbf3e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200419"
---
# <a name="return-or-skip-elements-in-a-sequence"></a>Zurückgeben oder Überspringen von Elementen in einer Sequenz

Verwenden Sie den <xref:System.Linq.Queryable.Take%2A>-Operator, um eine bestimmte Anzahl von Elementen in einer Sequenz zurückzugeben und den Rest zu überspringen.  
  
 Verwenden Sie den <xref:System.Linq.Queryable.Skip%2A>-Operator um eine bestimmte Anzahl von Elementen in einer Sequenz zu überspringen und den Rest zurückzugeben.  
  
> [!NOTE]
> <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> weisen bestimmte Einschränkungen auf, wenn sie für Abfragen in SQL Server 2000 verwendet werden. Weitere Informationen finden Sie im Eintrag "überspringen und Entfernen von Ausnahmen in SQL Server 2000" in der [Problem](troubleshooting.md)Behandlung.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt <xref:System.Linq.Queryable.Skip%2A> mithilfe einer Unterabfrage mit der SQL- `NOT EXISTS` Klausel. Diese Übersetzung weist die folgenden Einschränkungen auf:  
  
- Das Argument muss ein Satz sein. Multisets werden nicht unterstützt, auch dann nicht, wenn diese geordnet sind.  
  
- Die erzeugte Abfrage kann wesentlich komplexer sein als die Abfrage, die für die Basisabfrage erstellt wurde, auf die <xref:System.Linq.Queryable.Skip%2A> angewendet wird. Diese Komplexität kann zu einer Abnahme der Leistung oder sogar zu einer Zeitüberschreitung führen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird `Take` verwendet, um die ersten fünf eingestellten `Employees` auszuwählen. Beachten Sie, dass die Auflistung zuerst nach `HireDate` sortiert wird.  
  
 [!code-csharp[DLinqQueryExamples#16](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#16)]
 [!code-vb[DLinqQueryExamples#16](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#16)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird <xref:System.Linq.Queryable.Skip%2A> verwendet, um alle außer den zehn teuersten `Products` auszuwählen.  
  
 [!code-csharp[DLinqQueryExamples#17](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#17)]
 [!code-vb[DLinqQueryExamples#17](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#17)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel werden die <xref:System.Linq.Queryable.Skip%2A>-Methode und die <xref:System.Linq.Queryable.Take%2A>-Methode kombiniert, um die ersten 50 Datensätze zu überspringen und dann die nächsten zehn zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#18](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#18)]
 [!code-vb[DLinqQueryExamples#18](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#18)]  
  
 Die <xref:System.Linq.Queryable.Take%2A>-Operation und die <xref:System.Linq.Queryable.Skip%2A>-Operation sind nur bei geordneten Sätzen gut definiert. Die Semantik für ungeordnete Sätze oder Multisets ist nicht definiert.  
  
 Aufgrund der Sortierungseinschränkungen in SQL versucht [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], die Sortierung des Arguments des <xref:System.Linq.Queryable.Take%2A>-Operators oder des <xref:System.Linq.Queryable.Skip%2A>-Operators auf das Operatorergebnis zu verlagern.  
  
> [!NOTE]
> Die Übersetzung unterscheidet sich für SQL Server 2000 und SQL Server 2005. Wenn Sie die Verwendung <xref:System.Linq.Queryable.Skip%2A> von mit einer Abfrage einer beliebigen Komplexität planen, verwenden Sie SQL Server 2005.  
  
 Beachten Sie die folgende [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfrage für SQL Server 2000:  
  
 [!code-csharp[DLinqQueryExamples#19](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#19)]
 [!code-vb[DLinqQueryExamples#19](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#19)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verschiebt die Bestellung im SQL-Code wie folgt an das Ende:  
  
```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 Wenn <xref:System.Linq.Queryable.Take%2A> und <xref:System.Linq.Queryable.Skip%2A> verkettet werden, muss die angegebene Sortierung konsistent sein. Andernfalls sind die Ergebnisse nicht definiert.  
  
 Für nicht negative, konstante, ganzzahlige Argumente auf Grundlage der SQL-Spezifikation sind <xref:System.Linq.Queryable.Take%2A> und <xref:System.Linq.Queryable.Skip%2A> klar definiert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfrage Beispiele](query-examples.md)
- [Übersetzen von Standardabfrageoperatoren](standard-query-operator-translation.md)
