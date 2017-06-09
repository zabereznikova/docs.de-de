---
title: "LINQ to SQL-Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# LINQ to SQL-Abfragen
Sie definieren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Abfragen, indem Sie die gleiche Syntax wie in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] verwenden.  Der einzige Unterschied besteht darin, dass die in Abfragen referenzierten Objekte den Elementen in einer Datenbank zugeordnet werden.  Weitere Informationen finden Sie unter [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die Sie in entsprechende SQL\-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server. Ihre Anwendung verwendet die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-API, um die Abfrageausführung anzufordern.  Der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Anbieter wandelt dann die Abfrage in SQL\-Text um und übergibt die Ausführung an den ADO\-Anbieter. Der ADO\-Anbieter gibt Abfrageergebnisse als `DataReader` zurück.  Der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Anbieter übersetzt die ADO\-Ergebnisse zu einer <xref:System.Linq.IQueryable>\-Auflistung von Benutzerobjekten.  
  
> [!NOTE]
>  Die meisten Methoden und Operatoren in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]\-internen Datentypen verfügen über direkte Übersetzungen zu SQL.  Jene, die [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] nicht übersetzen kann, generieren Laufzeitausnahmen.  Weitere Informationen finden Sie unter [SQL CLR\-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 Die folgende Tabelle zeigt Ähnlichkeiten und Unterschiede zwischen den Abfrageelementen [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]\-Abfrageelementen und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Abfrageelementen.  
  
|Element|LINQ\-Abfrage|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Abfrage|  
|-------------|-------------------|-------------------------------------------------------------------------|  
|Rückgabetyp der lokalen Variablen, die die Abfrage \(für Abfragen, die Sequenzen zurückgeben\) enthält|Generisches `IEnumerable`|Generisches `IQueryable`|  
|Angeben der Datenquelle|Verwendet die `From`\-Klausel \([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) oder die `from`\-Klausel \(C\#\)|Gleiche Voraussetzung|  
|Filtern|Verwendet die `Where`\/`where`\-Klausel.|Gleiche Voraussetzung|  
|Gruppierung|Verwendet die `Group…By`\/`groupby`\-Klausel.|Gleiche Voraussetzung|  
|Auswählen \(Projizieren\)|Verwendet die `Select`\/`select`\-Klausel.|Gleiche Voraussetzung|  
|Verzögerte und unmittelbare Ausführung|Siehe [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)|Gleiche Voraussetzung|  
|Implementieren von Joins|Verwendet die `Join`\/`join`\-Klausel.|Kann die `Join`\/`join`\-Klausel verwenden, effektiver ist jedoch das <xref:System.Data.Linq.Mapping.AssociationAttribute>\-Attribut.  Weitere Informationen finden Sie unter [Beziehungsübergreifende Abfragen](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Remoteausführung und lokale Ausführung||Weitere Informationen finden Sie unter [Remoteausführung im Vergleich zur lokalen Ausführung](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md).|  
|Streamingabfragen und gepufferte Abfragen|Nicht anwendbar auf ein lokales Arbeitsspeicherszenario||  
  
## Siehe auch  
 [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)   
 [Basic LINQ Query Operations](../Topic/Basic%20LINQ%20Query%20Operations%20\(C%23\).md)   
 [Type Relationships in LINQ Query Operations](../Topic/Type%20Relationships%20in%20LINQ%20Query%20Operations%20\(C%23\).md)   
 [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)