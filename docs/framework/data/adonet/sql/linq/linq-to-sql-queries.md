---
title: LINQ to SQL-Abfragen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 533786ffe1fa39928f90d94bbb0d80584bf85b8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-queries"></a>LINQ to SQL-Abfragen
Sie definieren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfragen, indem Sie die gleiche Syntax wie in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] verwenden. Der einzige Unterschied besteht darin, dass die in Abfragen referenzierten Objekte den Elementen in einer Datenbank zugeordnet werden. Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server. Ihre Anwendung verwendet die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-API, um die Abfrageausführung anzufordern. Der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anbieter wandelt dann die Abfrage in SQL-Text um und übergibt die Ausführung an den ADO-Anbieter. Der ADO-Anbieter gibt Abfrageergebnisse als `DataReader` zurück. Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anbieter übersetzt die ADO-Ergebnisse in eine <xref:System.Linq.IQueryable> Auflistung von Benutzerobjekten.  
  
> [!NOTE]
>  Die meisten Methoden und Operatoren in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]-internen Datentypen verfügen über direkte Übersetzungen zu SQL. Jene, die [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] nicht übersetzen kann, generieren Laufzeitausnahmen. Weitere Informationen finden Sie unter [SQL-CLR-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 Die folgende Tabelle zeigt Ähnlichkeiten und Unterschiede zwischen den Abfrageelementen [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]-Abfrageelementen und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrageelementen.  
  
|Element|LINQ-Abfrage|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage|  
|----------|----------------|----------------------------------------------------------------------|  
|Rückgabetyp der lokalen Variablen, die die Abfrage (für Abfragen, die Sequenzen zurückgeben) enthält|Generisches `IEnumerable`|Generisches `IQueryable`|  
|Angeben der Datenquelle|Verwendet die `From` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) oder `from` -Klausel (c#)|Gleiche Voraussetzung|  
|Filtern|Verwendet die `Where` / `where` Klausel|Gleiche Voraussetzung|  
|Gruppieren|Verwendet die `Group…By` / `groupby` Klausel|Gleiche Voraussetzung|  
|Auswählen (Projizieren)|Verwendet die `Select` / `select` Klausel|Gleiche Voraussetzung|  
|Verzögerte und unmittelbare Ausführung|Finden Sie unter [Einführung in LINQ-Abfragen (c#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Gleiche Voraussetzung|  
|Implementieren von Joins|Verwendet die `Join` / `join` Klausel|Können die `Join` / `join` -Klausel, effektiver ist jedoch die <xref:System.Data.Linq.Mapping.AssociationAttribute> Attribut. Weitere Informationen finden Sie unter [Beziehungsübergreifendes](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Remoteausführung und lokale Ausführung||Weitere Informationen finden Sie unter [Remoteausführung. Lokale Ausführung](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md).|  
|Streamingabfragen und gepufferte Abfragen|Nicht anwendbar auf ein lokales Arbeitsspeicherszenario||  
  
## <a name="see-also"></a>Siehe auch  
 [Introduction to LINQ Queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 [Grundlegende LINQ-Abfragevorgänge](~/docs/csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)  
 [Typbeziehungen in LINQ-Abfragevorgängen](~/docs/csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)  
 [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
