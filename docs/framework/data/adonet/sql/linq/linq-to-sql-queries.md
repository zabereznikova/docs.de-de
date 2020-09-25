---
title: LINQ to SQL-Abfragen
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: c49644a866a6e245c6be1f9a8e8f95d003fd0191
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175225"
---
# <a name="linq-to-sql-queries"></a>LINQ to SQL-Abfragen

Sie definieren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfragen, indem Sie die gleiche Syntax wie in LINQ verwenden. Der einzige Unterschied besteht darin, dass die in Abfragen referenzierten Objekte den Elementen in einer Datenbank zugeordnet werden. Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server. Ihre Anwendung verwendet die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-API, um die Abfrageausführung anzufordern. Der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anbieter wandelt dann die Abfrage in SQL-Text um und übergibt die Ausführung an den ADO-Anbieter. Der ADO-Anbieter gibt Abfrageergebnisse als `DataReader` zurück. Der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anbieter übersetzt die ADO-Ergebnisse in eine Auflistung <xref:System.Linq.IQueryable> von Benutzer Objekten.  
  
> [!NOTE]
> Die meisten Methoden und Operatoren für .NET Framework integrierten Typen haben direkte Übersetzungen in SQL. Die, die LINQ nicht übersetzen kann, generieren Lauf Zeit Ausnahmen. Weitere Informationen finden Sie unter [SQL-CLR-Typzuordnung](sql-clr-type-mapping.md).  
  
 Die folgende Tabelle zeigt die Ähnlichkeiten und Unterschiede zwischen LINQ-und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfrage Elementen.  
  
|Element|LINQ-Abfrage|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage|  
|----------|----------------|----------------------------------------------------------------------|  
|Rückgabetyp der lokalen Variablen, die die Abfrage (für Abfragen, die Sequenzen zurückgeben) enthält|Generisches `IEnumerable`|Generisches `IQueryable`|  
|Angeben der Datenquelle|Verwendet die- `From` Klausel (Visual Basic) oder die- `from` Klausel (c#).|identisch|  
|Filtern|Verwendet die- `Where` / `where` Klausel.|identisch|  
|Gruppierung|Verwendet die- `Group…By` / `groupby` Klausel.|identisch|  
|Auswählen (Projizieren)|Verwendet die- `Select` / `select` Klausel.|identisch|  
|Verzögerte und unmittelbare Ausführung|Weitere Informationen finden [Sie unter Einführung in LINQ-Abfragen (c#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|identisch|  
|Implementieren von Joins|Verwendet die- `Join` / `join` Klausel.|Kann die- `Join` / `join` Klausel verwenden, aber effektiver das- <xref:System.Data.Linq.Mapping.AssociationAttribute> Attribut verwendet. Weitere Informationen finden Sie unter [Beziehungs übergreifende Abfragen](querying-across-relationships.md).|  
|Remoteausführung und lokale Ausführung||Weitere Informationen finden Sie unter [Remote Ausführung im Vergleich zur lokalen Ausführung](remote-vs-local-execution.md).|  
|Streamingabfragen und gepufferte Abfragen|Nicht anwendbar auf ein lokales Arbeitsspeicherszenario||  
  
## <a name="see-also"></a>Siehe auch

- [Introduction to LINQ Queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Grundlegende LINQ-Abfragevorgänge](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Typbeziehungen in LINQ-Abfragevorgängen](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Abfragekonzepte](query-concepts.md)
