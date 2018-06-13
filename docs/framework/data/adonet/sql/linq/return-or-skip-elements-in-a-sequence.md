---
title: Zurückgeben oder Überspringen von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81a31acd-e0f1-4bca-9a12-fa1ad5752374
ms.openlocfilehash: 228de9f3b92d45866c98976be08b84988a2db8d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359877"
---
# <a name="return-or-skip-elements-in-a-sequence"></a>Zurückgeben oder Überspringen von Elementen in einer Sequenz
Verwenden Sie den <xref:System.Linq.Queryable.Take%2A>-Operator, um eine bestimmte Anzahl von Elementen in einer Sequenz zurückzugeben und den Rest zu überspringen.  
  
 Verwenden Sie den <xref:System.Linq.Queryable.Skip%2A>-Operator um eine bestimmte Anzahl von Elementen in einer Sequenz zu überspringen und den Rest zurückzugeben.  
  
> [!NOTE]
>  <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> weisen bestimmte Einschränkungen auf, wenn sie für Abfragen in SQL Server 2000 verwendet werden. Weitere Informationen finden Sie unter dem Eintrag "Überspringen und Behandeln von Ausnahmen in SQLServer 2000" in [Problembehandlung](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt <xref:System.Linq.Queryable.Skip%2A> mithilfe einer Unterabfrage mit dem SQL- `NOT EXISTS` Klausel. Diese Übersetzung weist die folgenden Einschränkungen auf:  
  
-   Das Argument muss ein Satz sein. Multisets werden nicht unterstützt, auch dann nicht, wenn diese geordnet sind.  
  
-   Die erzeugte Abfrage kann wesentlich komplexer sein als die Abfrage, die für die Basisabfrage erstellt wurde, auf die <xref:System.Linq.Queryable.Skip%2A> angewendet wird. Diese Komplexität kann zu einer Abnahme der Leistung oder sogar zu einer Zeitüberschreitung führen.  
  
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
>  Die Übersetzung weicht für [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] und [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)] ab. Wenn Sie planen, <xref:System.Linq.Queryable.Skip%2A> mit einer komplexeren Abfrage einzusetzen, verwenden Sie [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].  
  
 Beachten Sie die folgende [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage für [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]:  
  
 [!code-csharp[DLinqQueryExamples#19](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#19)]
 [!code-vb[DLinqQueryExamples#19](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#19)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verschiebt die Bestellung im SQL-Code wie folgt an das Ende:  
  
```  
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
  
## <a name="see-also"></a>Siehe auch  
 [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Übersetzen von Standardabfrageoperatoren](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
