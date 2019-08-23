---
title: LINQ to SQL-Abfragen
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 534da029664af0babc3dff6226ff095b7222c34d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915834"
---
# <a name="linq-to-sql-queries"></a>LINQ to SQL-Abfragen
Sie definieren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfragen, indem Sie die gleiche Syntax wie in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] verwenden. Der einzige Unterschied besteht darin, dass die in Abfragen referenzierten Objekte den Elementen in einer Datenbank zugeordnet werden. Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server. Ihre Anwendung verwendet die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-API, um die Abfrageausführung anzufordern. Der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anbieter wandelt dann die Abfrage in SQL-Text um und übergibt die Ausführung an den ADO-Anbieter. Der ADO-Anbieter gibt Abfrageergebnisse als `DataReader` zurück. Der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anbieter übersetzt die ADO-Ergebnisse in <xref:System.Linq.IQueryable> eine Auflistung von Benutzer Objekten.  
  
> [!NOTE]
> Die meisten Methoden und Operatoren für .NET Framework integrierten Typen haben direkte Übersetzungen in SQL. Jene, die [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] nicht übersetzen kann, generieren Laufzeitausnahmen. Weitere Informationen finden Sie unter [SQL-CLR-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 Die folgende Tabelle zeigt Ähnlichkeiten und Unterschiede zwischen den Abfrageelementen [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]-Abfrageelementen und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrageelementen.  
  
|Element|LINQ-Abfrage|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage|  
|----------|----------------|----------------------------------------------------------------------|  
|Rückgabetyp der lokalen Variablen, die die Abfrage (für Abfragen, die Sequenzen zurückgeben) enthält|Generisches `IEnumerable`|Generisches `IQueryable`|  
|Angeben der Datenquelle|Verwendet die `From` -Klausel (Visual Basic `from` )C#oder die ()-Klausel.|Gleiche Voraussetzung|  
|Filtern|Verwendet die `Where` / -Klausel`where` .|Gleiche Voraussetzung|  
|Gruppieren|Verwendet die `Group…By` / -Klausel`groupby` .|Gleiche Voraussetzung|  
|Auswählen (Projizieren)|Verwendet die `Select` / -Klausel`select` .|Gleiche Voraussetzung|  
|Verzögerte und unmittelbare Ausführung|Siehe [Einführung in LINQ-AbfragenC#()](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) .|Gleiche Voraussetzung|  
|Implementieren von Joins|Verwendet die `Join` / -Klausel`join` .|`Join` Kann die / <xref:System.Data.Linq.Mapping.AssociationAttribute> -Klausel verwenden, aber effektiver das-Attribut verwendet. `join` Weitere Informationen finden Sie unter [Beziehungs übergreifende Abfragen](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Remoteausführung und lokale Ausführung||Weitere Informationen finden [Sie unter Remote im Vergleich zu Lokale Ausführung](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md).|  
|Streamingabfragen und gepufferte Abfragen|Nicht anwendbar auf ein lokales Arbeitsspeicherszenario||  
  
## <a name="see-also"></a>Siehe auch

- [Introduction to LINQ Queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Grundlegende LINQ-Abfragevorgänge](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Typbeziehungen in LINQ-Abfragevorgängen](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
