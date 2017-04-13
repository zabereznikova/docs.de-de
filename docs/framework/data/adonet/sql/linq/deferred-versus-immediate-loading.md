---
title: "Verz&#246;gertes und unmittelbares Laden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Verz&#246;gertes und unmittelbares Laden
Wenn Sie eine Abfrage für ein Objekt durchführen, wird nur das angeforderte Objekt abgerufen.  Die *verwandten* Objekte werden nicht automatisch zum gleichen Zeitpunkt abgerufen.  \(Weitere Informationen finden Sie unter [Beziehungsübergreifende Abfragen](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).\) Für Sie ist nicht erkennbar, dass verwandte Objekte nicht bereits geladen sind, da der Versuch, auf diese Objekte zuzugreifen, eine Abfrage erzeugt, die diese Objekte abruft.  
  
 Sie möchten beispielsweise eine bestimmte Gruppe von Bestellungen abrufen und anschließend bestimmten Kunden eine Benachrichtigung per E\-Mail senden.  Sie müssen nicht notwendigerweise zunächst alle Kundendaten zu jeder Bestellung abrufen.  Sie können mithilfe von verzögertem Laden weitere Informationen erst dann abrufen, wenn Sie diese benötigen.  Betrachten Sie das folgende Beispiel:  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 Das Gegenteil könnte auch zutreffen.  Möglicherweise verwenden Sie eine Anwendung, die Kunden\- und Bestelldaten gleichzeitig anzeigen muss.  Sie wissen, dass Sie beide Datensätze benötigen.  Sie wissen, dass die Anwendung Bestellinformationen für jeden Kunden benötigt, sobald Sie die Ergebnisse abrufen.  Sie möchten nicht einzelne Abfragen zu den Bestellungen jedes einzelnen Kunden übergeben.  Sie möchten stattdessen die Bestelldaten zusammen mit den Kunden abrufen.  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 Sie können auch Kunden und Bestellungen in einer Abfrage zusammenfassen, indem Sie diese produktübergreifend gestalten und alle erforderlichen Daten in Form einer großen Projektion abrufen.  Diese Ergebnisse sind jedoch keine Entitäten.  \(Weitere Informationen finden Sie unter [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).\)  Entitäten sind Objekte, die Sie verändern können. Bei diesen Ergebnissen handelt es sich jedoch um Projektionen, die nicht verändert und erhalten werden können.  Darüber hinaus würden Sie eine Menge redundanter Daten abrufen, da sich die Kunden bei jeder Bestellung in der optimierten gemeinsamen Abfrage wiederholen.  
  
 Sie benötigen stattdessen eine Möglichkeit, verwandte Objekte zur gleichen Zeit abzurufen.  Dieser Satz ist ein isolierter Bereich eines Graphen, sodass Sie niemals mehr oder weniger Daten als benötigt abrufen.  Zu diesem Zweck stellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für das sofortige Laden einer Region Ihres Objektmodells <xref:System.Data.Linq.DataLoadOptions> zur Verfügung.  Die Methoden umfassen:  
  
-   Die <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>\-Methode zum sofortigen Laden von Daten zum Hauptziel.  
  
-   Die <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>\-Methode zum Filtern abgerufener Objekte nach einer bestimmten Beziehung.  
  
## Siehe auch  
 [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)