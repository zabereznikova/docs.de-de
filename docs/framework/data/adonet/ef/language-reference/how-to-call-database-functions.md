---
title: "Gewusst wie: Aufrufen von Datenbankfunktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Aufrufen von Datenbankfunktionen
Die <xref:System.Data.Objects.SqlClient.SqlFunctions>\-Klasse enthält Methoden, mit denen SQL Server\-Funktionen in LINQ to Entities\-Abfragen verwendet werden können.  Beim Verwenden von <xref:System.Data.Objects.SqlClient.SqlFunctions>\-Methoden in LINQ to Entities\-Abfragen werden die entsprechenden Datenbankfunktionen in der Datenbank ausgeführt.  
  
> [!NOTE]
>  Datenbankfunktionen, die eine Berechnung für einen Satz von Werten ausführen und einen einzelnen Wert \(auch bekannt als aggregierte Datenbankfunktionen\) zurückgeben, können direkt aufgerufen werden.  Andere kanonische Funktionen können nur als Teil einer LINQ to Entities\-Abfrage aufgerufen werden.  Zum direkten Aufrufen einer Aggregatfunktion muss eine <xref:System.Data.Objects.ObjectQuery%601> an die Funktion übergeben werden.  Weitere Informationen finden Sie unten im zweiten Beispiel.  
  
> [!NOTE]
>  Die Methoden in der <xref:System.Data.Objects.SqlClient.SqlFunctions>\-Klasse sind spezifisch für SQL Server\-Funktionen.  Ähnliche Klassen, die Datenbankfunktionen verfügbar machen, sind möglicherweise über andere Anbieter verfügbar.  
  
## Beispiel  
 Im folgenden Beispiel wird das [AdventureWorks Sales Model](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) verwendet.  Im Beispiel wird eine LINQ to Entities\-Abfrage ausgeführt, die die <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A>\-Methode zur Rückgabe aller Kontakte verwendet, deren Nachname mit "Si" beginnt:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## Beispiel  
 Im folgenden Beispiel wird das [AdventureWorks Sales Model](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) verwendet.  Im Beispiel wird die aggregierte <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>\-Methode direkt aufgerufen.  Eine <xref:System.Data.Objects.ObjectQuery%601> wird an die Funktion übergeben, durch die sie aufgerufen werden kann, ohne Teil einer LINQ to Entities\-Abfrage sein zu müssen.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## Siehe auch  
 [Aufrufen von Funktionen in LINQ to Entities\-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)   
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)