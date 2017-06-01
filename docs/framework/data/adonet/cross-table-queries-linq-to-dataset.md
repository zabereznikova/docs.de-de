---
title: "Abfragen f&#252;r mehrere Tabellen (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Abfragen f&#252;r mehrere Tabellen (LINQ to DataSet)
Zusätzlich zum Abfragen einer einzelnen Tabelle können Sie in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] auch tabellenübergreifende Abfragen ausführen. Dies geschieht mithilfe eines *Joins*.  Bei einem Join werden Objekte in einer Datenquelle mit Objekten in einer anderen Datenquelle, die über ein gemeinsames Attribut \(wie Produkt oder Kontakt\-ID\) verfügen, miteinander verknüpft.  In der objektorientierten Programmierung sind Beziehungen zwischen Objekten relativ einfach zu navigieren, da jedes Objekt einen Member hat, der auf ein anderes Objekt verweist. In externen Datenbanktabellen ist die Navigation zwischen den Beziehungen etwas komplizierter.  Datenbanktabellen enthalten keine integrierten Beziehungen. In diesen Fällen kann der JOIN\-Vorgang verwendet werden, um Elemente aus den einzelnen Quellen zu verknüpfen.  Wenn Sie z. B. zwei Tabellen haben, die Produktinformationen und Vertriebsinformationen enthalten, könnten Sie mittels einer JOIN\-Operation Vertriebsinformationen und Produkte für ein und denselben Auftrag miteinander verknüpfen.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] Framework stellt die beiden Joinoperatoren <xref:System.Linq.Enumerable.Join%2A> und <xref:System.Linq.Enumerable.GroupJoin%2A> bereit. Diese Operatoren führen *Gleichheitsjoins* aus, d. h., sie verknüpfen zwei Datenquellen nur dann, wenn deren Schlüssel gleich sind.  \(Im Gegensatz dazu unterstützt [!INCLUDE[tsql](../../../../includes/tsql-md.md)] auch andere Joinoperatoren als `equals`, wie z. B. den `less than`\-Operator.\)  
  
 In der Terminologie relationaler Datenbanken implementiert <xref:System.Linq.Enumerable.Join%2A> einen inneren Join.  Eine innerer Join ist eine Joinart, bei der nur diejenigen Objekte zurückgegeben werden, für die es im anderen Dataset ein passendes Gegenüber gibt.  
  
 Die <xref:System.Linq.Enumerable.GroupJoin%2A>\-Operatoren haben in der Terminologie für relationale Datenbanken keine direkte Entsprechung, sie implementieren ein Superset von inneren Joins und linken äußeren Joins. Ein linker äußerer Join ist ein Join, der jedes Element der ersten \(linken\) Auflistung zurückgibt, selbst wenn keine zugeordneten Elemente in der zweiten Auflistung vorhanden sind.  
  
 Weitere Informationen zu Joins finden Sie unter [Join Operations](../../../../ocs/visual-basic/programming-guide/concepts/linq/join-operations.md).  
  
## Beispiel  
 Im folgenden Beispiel werden die Tabellen `SalesOrderHeader` und `SalesOrderDetail` aus der \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Beispieldatenbank auf herkömmliche Art und Weise miteinander verknüpft, um Onlinebestellungen aus dem Monat August abzurufen.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## Siehe auch  
 [Abfragen von 'DataSets'](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [Abfragen für eine einzelne Tabelle](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)   
 [Abfragen von typisierten DataSets](../../../../docs/framework/data/adonet/querying-typed-datasets.md)   
 [Join Operations](../../../../ocs/visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [LINQ to DataSet\-Beispiele](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)